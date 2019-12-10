# Pyspark<a name="modelarts_23_0178"></a>

## 训练并保存模型<a name="section94641018111916"></a>

```
from pyspark.ml import Pipeline, PipelineModel
from pyspark.ml.linalg import Vectors
from pyspark.ml.classification import LogisticRegression

# 创建训练数据，此处通过tuples创建
# Prepare training data from a list of (label, features) tuples.
training = spark.createDataFrame([
    (1.0, Vectors.dense([0.0, 1.1, 0.1])),
    (0.0, Vectors.dense([2.0, 1.0, -1.0])),
    (0.0, Vectors.dense([2.0, 1.3, 1.0])),
    (1.0, Vectors.dense([0.0, 1.2, -0.5]))], ["label", "features"])

# 创建训练实例，此处使用逻辑回归算法进行训练
# Create a LogisticRegression instance. This instance is an Estimator.
lr = LogisticRegression(maxIter=10, regParam=0.01)

# 训练逻辑回归模型
# Learn a LogisticRegression model. This uses the parameters stored in lr.
model = lr.fit(training)

# 保存模型到本地目录
# Save model to local path.
model.save(sc, "/tmp/spark_model")
```

保存完模型后，需要上传到OBS目录才能发布。发布时需要带上“config.json“配置以及“customize\_service.py“，定义方式请参考[模型包规范介绍](模型包规范介绍.md)。

## 推理代码<a name="section6122193511917"></a>

```
# coding:utf-8
import collections
import json
import traceback

import model_service.log as log
from model_service.spark_model_service import SparkServingBaseService
from pyspark.ml.classification import LogisticRegression

logger = log.getLogger(__name__)


class user_Service(SparkServingBaseService):
    # 数据预处理
    def _preprocess(self, data):
        logger.info("Begin to handle data from user data...")
        # 读取数据
        req_json = json.loads(data, object_pairs_hook=collections.OrderedDict)
        try:
            # 将数据转换成spark dataframe格式
            predict_spdf = self.spark.createDataFrame(pd.DataFrame(req_json["data"]["req_data"]))
        except Exception as e:
            logger.error("check your request data does meet the requirements ?")
            logger.error(traceback.format_exc())
            raise Exception("check your request data does meet the requirements ?")
        return predict_spdf

    # 模型推理
    def _inference(self, data):
        try:
            # 加载模型文件
            predict_model = LogisticRegression.load(self.model_path)
            # 对数据进行推理
            prediction_result = predict_model.transform(data)
        return prediction_result

    # 数据后处理
    def _postprocess(self, pre_data):
        logger.info("Get new data to respond...")
        predict_str = pre_data.toPandas().to_json(orient='records')
        predict_result = json.loads(predict_str)
        return predict_result
```

