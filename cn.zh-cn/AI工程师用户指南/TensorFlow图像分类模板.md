# TensorFlow图像分类模板<a name="modelarts_23_0160"></a>

## 简介<a name="section106016181004"></a>

搭载TensorFlow1.8引擎，运行环境为“python2.7”，适合导入以“SavedModel“格式保存的TensorFlow图像分类模型。该模板使用平台预置的图像处理模式，模式详情参见[预置图像处理模式](预置图像处理模式.md)，推理时向模型输入一张“key“为“images“的待处理图片，所以需确保您的模型能处理“key“为“images“的输入。使用该模板导入模型时请选择到包含模型文件的“model“目录。

## 模板输入<a name="section575513501891"></a>

存储在OBS上的TensorFlow模型包，确保您使用的OBS目录与ModelArts在同一区域。模型包的要求请参见[模型包示例](#section12918237401)。

## 对应的输入输出模式<a name="section19490845206"></a>

[预置图像处理模式](预置图像处理模式.md)，不可覆盖，即创建模型时不支持选择其他输入输出模式。

## 模型包规范<a name="section1680842614523"></a>

-   模型包必须存储在OBS中，且必须以“model“命名。“model“文件夹下面放置模型文件、模型推理代码。
-   模型推理代码文件不是必选文件，如果有，其文件名必须为“customize\_service.py“，“model“文件夹下有且只能有1个推理代码文件，模型推理代码编写请参见[模型推理代码编写说明](模型推理代码编写说明.md)。

-   使用模板导入的模型包结构如下所示：

    ```
    model/
    │
    ├── 模型文件                 //必选，不同的框架，其模型文件格式不同，详细可参考模型包示例。
    ├── 自定义Python包           //可选，用户自有的Python包，在模型推理代码中可以直接引用。
    ├── customize_service.py  //可选，模型推理代码，文件名称必须为“customize_service.py”，否则不视为推理代码。
    ```


## 模型包示例<a name="section12918237401"></a>

**TensorFlow模型包结构**

发布该模型时只需要指定到“model“目录。

```
OBS桶/目录名
|── model    必选，文件夹名称必须为“model”，用于放置模型相关文件。
    ├── <<自定义python包>>    可选，用户自有的Python包，在模型推理代码中可以直接引用。
    ├── saved_model.pb        必选，protocol buffer格式文件，包含该模型的图描述。
    ├── variables             对“*.pb”模型主文件而言必选。文件夹名称必须为“variables”，包含模型的权重偏差等信息。
        ├── variables.index                   必选
        ├── variables.data-00000-of-00001     必选
    ├──customize_service.py   可选，模型推理代码，文件名称必须为“customize_service.py”, 有且只有1个推理代码文件。“customize_service.py”依赖的“py”文件可以直接放“model”目录下。
```

