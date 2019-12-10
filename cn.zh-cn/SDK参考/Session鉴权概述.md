# Session鉴权概述<a name="modelarts_04_0123"></a>

Session模块的主要作用是实现与华为云资源的鉴权，并初始化ModelArts SDK Client、OBS Client。当成功建立Session后，您可以直接调用ModelArts的SDK接口。

当前ModelArts Notebook开发环境不需要session鉴权，可以直接使用。示例代码如下：

```
from modelarts.session import Session
session = Session()
```

对于其它开发环境下使用ModelArts SDK时，session鉴权方式请参考以下三种认证方式。

-   [用户名密码认证模式](用户名密码认证模式.md)： 支持[OBS管理](OBS管理概述.md)、[作业管理](创建训练作业.md)、[模型管理](导入模型.md)、[服务管理](服务管理概述.md)的鉴权。
-   [用户AK-SK认证模式](用户AK-SK认证模式.md)： 支持[OBS管理](OBS管理概述.md)、[作业管理](创建训练作业.md)、[模型管理](导入模型.md)、[服务管理](服务管理概述.md)的鉴权。
-   [配置config.json认证模式](配置config-json认证模式.md)：支持SDK所有模块的鉴权。

