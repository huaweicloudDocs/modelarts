# SDK下载和安装<a name="modelarts_04_0004"></a>

## SDK下载<a name="section16657165520146"></a>

[下载ModelArts SDK软件包](https://cnnorth1-modelarts-sdk.obs.cn-north-1.myhuaweicloud.com/modelarts-latest-py2.py3-none-any.whl)，获取最新版本的ModelArts SDK软件包。

## SDK安装<a name="section536631020158"></a>

SDK下载完成后，您可以通过Python通用包管理工具pip进行安装，pip安装指导请参见[pip官网](https://pip.pypa.io/en/stable/installing/)。ModelArts SDK安装请您执行如下命令：

**pip install modelarts-latest-py2.py3-none-any.whl**

在安装SDK时会默认安装所需的依赖包，具体如下：

```
certifi >= 14.05.14
six >= 1.10
python_dateutil >= 2.5.3
setuptools >= 21.0.0
urllib3 >= 1.15.1
requests >= 2.19.1
esdk-obs-python == 3.0.5
Flask==1.0.2
Flask-Cors==3.0.4
gunicorn==19.8.1
mxnet-model-server==0.3
psutil==5.4.6
prometheus_client==0.3.1
```

如果在安装过程中报错提示您缺少相应的依赖包，请您按照报错提示执行如下命令进行安装，其中xxxx为依赖包的名称。

**pip install xxxx**

