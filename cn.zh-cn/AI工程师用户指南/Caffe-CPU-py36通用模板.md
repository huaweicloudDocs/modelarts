# Caffe-CPU-py36通用模板<a name="modelarts_23_0169"></a>

## 简介<a name="section17644758143116"></a>

搭载Caffe1.0 CPU版 AI引擎，运行环境为“python3.6”，内置输入输出模式为未定义模式，请根据模型功能或业务场景重新选择合适的输入输出模式。使用该模板导入模型时请选择到包含模型文件的model目录。

## 模板输入<a name="section1287913116322"></a>

存储在OBS上的Caffe模型包，确保您使用的OBS目录与ModelArts在同一区域。模型包的要求请参见[模型包示例](#section164016197320)。

## 对应的输入输出模式<a name="section157592853210"></a>

[未定义模式](未定义模式.md)，可覆盖，即创建模型时支持选择其他输入输出模式。

## 模型包规范<a name="section856341533214"></a>

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


## 模型包示例<a name="section164016197320"></a>

**Caffe模型包结构**

发布该模型时只需要指定到“model“目录。

```
OBS桶/目录名
|── model    必选，文件夹名称必须为“model”，用于放置模型相关文件。
    |── <<自定义python包>>      可选，用户自有的Python包，在模型推理代码中可以直接引用。
    |── deploy.prototxt         必选，caffe模型保存文件，存有模型网络结构等信息。
    |── resnet.caffemodel       必选，caffe模型保存文件，存有权重变量等信息。
    |── customize_service.py    可选，模型推理代码，文件名称必须为“customize_service.py”, 有且只有1个推理代码文件。“customize_service.py”依赖的“py”文件可以直接放“model”目录下。
```

