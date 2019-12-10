# MXNet<a name="modelarts_23_0174"></a>

## 训练并保存模型<a name="section94641018111916"></a>

```
import mxnet as mx
mnist = mx.test_utils.get_mnist()
ctx = mx.cpu()

batch_size = 64
train_iter = mx.io.NDArrayIter(mnist['train_data'], mnist['train_label'], batch_size, shuffle=True)
val_iter = mx.io.NDArrayIter(mnist['test_data'], mnist['test_label'], batch_size)

data = mx.sym.var('data')
# Flatten the data from 4-D shape into 2-D (batch_size, num_channel*width*height)
data = mx.sym.flatten(data=data)

fc1  = mx.sym.FullyConnected(data=data, num_hidden=5120)
act1 = mx.sym.Activation(data=fc1, act_type="relu")

dropout = mx.symbol.Dropout(act1, p = 0.2)

fc2  = mx.sym.FullyConnected(data=dropout, num_hidden=10)

mlp  = mx.sym.SoftmaxOutput(data=fc2, name='softmax')

checkpoint = mx.callback.do_checkpoint('./mxnet_model/mxnet_mnist')

import logging
logging.getLogger().setLevel(logging.DEBUG)  # logging to stdout
# create a trainable module on compute context
mlp_model = mx.mod.Module(symbol=mlp, context=ctx)
mlp_model.fit(train_iter,  # train data
              eval_data=val_iter,  # validation data
              optimizer='adam',  
              eval_metric=mx.metric.CrossEntropy(),  # report accuracy during training
              batch_end_callback = mx.callback.Speedometer(batch_size, 100), # output progress for each 100 data batches
              num_epoch=2,
              epoch_end_callback=checkpoint
             ) 
```

保存完模型后，将生成“./mxnet\_model/“目录，并且在此目录下生成“mxnet\_mnist-symbol.json“、“mxnet\_mnist-0001.params“、“mxnet\_mnist-0002.params“，每次迭代会生成相应的变量文件。这里我们选取mxnet\_mnist-0002.params作为部署服务所用的变量文件，重命名为mxnet\_mnist-0000.params。

## 推理代码<a name="section6122193511917"></a>

```
# -*- coding: utf-8 -*-  
# Copyright 2017 Amazon.com, Inc. or its affiliates. All Rights Reserved.
# Licensed under the Apache License, Version 2.0 (the "License").
# You may not use this file except in compliance with the License.
# A copy of the License is located at
#     http://www.apache.org/licenses/LICENSE-2.0
# or in the "license" file accompanying this file. This file is distributed
# on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either
# express or implied. See the License for the specific language governing
# permissions and limitations under the License.

"""`MXNetVisionService` defines a MXNet base vision service
"""
import mxnet as mx
import os

from mms.model_service.mxnet_model_service import MXNetBaseService
from mms.utils.mxnet import image, ndarray
from mms.log import get_logger

# 定义输入shape
INPUT_SHAPE=28

logger = get_logger()


class MXNetVisionService(MXNetBaseService):
    """MXNetVisionService defines a fundamental service for image classification task.
    In preprocess, input image buffer is read to NDArray and resized respect to input
    shape in signature.
    """
    def __init__(self, model_name, model_dir, manifest, gpu=None):

        self.model_name = model_name

       # CPU和GPU兼容处理，如果GPU可用就设置GPU否则设CPU
        try:
            _ = mx.nd.array([], ctx=mx.gpu())
            self.ctx = mx.gpu()
            logger.info("set context to gpu")
        except mx.MXNetError:
            self.ctx = mx.cpu()
            logger.info("set context to cpu")

        self._signature = manifest['Model']['Signature']

        # 定义输入shape
        self.data_shape = (1, 1, INPUT_SHAPE, INPUT_SHAPE)
        self._signature['inputs'] = [{
            # 定义输入data_name，需要和用户https接口输入保持一致
            'data_name': 'images',
            'data_shape': self.data_shape
        }]
        self.scale = []
        self.num_images = 0

        self.provide_data = [
            # 定义模型输入，需要和模型训练保持一致
            mx.io.DataDesc(name='data', shape=self.data_shape),
        ]

        # Load MXNet module
        epoch = 0
        try:
            param_filename = manifest['Model']['Parameters']
            epoch = int(param_filename[len(model_name) + 1:-len('.params')])
        except Exception as e:
            logging.info(
                'Failed to parse epoch from param file, setting epoch to 0')

        sym, arg_params, aux_params = mx.model.load_checkpoint(
            '%s/%s' % (model_dir, manifest['Model']['Symbol'][:-12]), epoch)

        ## process the arg_params
        self.symbol = sym
        self.mx_model = mx.mod.Module(
            context=self.ctx,
            symbol=sym,
            data_names=['data'],
            label_names=None)
        self.mx_model.bind(
            for_training=False,
            data_shapes=self.provide_data,
            label_shapes=None)
        self.mx_model.set_params(arg_params, aux_params, allow_missing=True)
        # Read synset file
        # If synset is not specified, check whether model archive contains synset file.
        archive_synset = os.path.join(model_dir, 'synset.txt')

        if os.path.isfile(archive_synset):
            synset = archive_synset
            self.labels = [line.strip() for line in open(synset).readlines()]
        # 定义类别标签变量 
        self.labels = [0,1,2,3,4,5,6,7,8,9]
    def _preprocess(self, data):
        img_list = []
        for idx, img in enumerate(data):
            input_shape = self.signature['inputs'][idx]['data_shape']
            [h, w] = input_shape[2:]
            # 转换输出图片为灰度图片
            img_arr = image.read(img, flag=0)
            # resize为模型输入shape
            img_arr = image.resize(img_arr, h, w)
            # 转换为NCHW
            img_arr = image.transform_shape(img_arr)
            img_list.append(img_arr)
        return img_list

    def _postprocess(self, data):
        # 输出最大置信度对应的类别
        return [ndarray.top_probability(d, self.labels, top=1) for d in data]
```

