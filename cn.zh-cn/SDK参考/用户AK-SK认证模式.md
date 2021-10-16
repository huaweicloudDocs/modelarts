# 用户AK-SK认证模式<a name="modelarts_04_0155"></a>

本模式支持[OBS管理](OBS管理概述.md)、[训练管理](创建训练作业.md)、[模型管理](导入模型.md)、[服务管理](服务管理概述.md)模块的鉴权。

## 示例代码<a name="zh-cn_topic_0173871416_section1139662914522"></a>

```
from modelarts.session import Session
session = Session(access_key='***',secret_key='***', project_id='***', region_name='***')
```

其中，各参数说明如下：

-   “access\_key“和“secret\_key“获取方式请参见[获取访问密钥](https://support.huaweicloud.com/prepare-modelarts/modelarts_08_0008.html)。
-   “project\_id“即项目ID。获取方式请参见[查看项目ID](查看项目ID.md)。
-   “region\_name“即区域ID。获取方式请参见[获取区域ID](https://support.huaweicloud.com/api-iam/iam_17_0002.html)。

