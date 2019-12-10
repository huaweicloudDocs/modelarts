# 获取OBS Client<a name="modelarts_04_0214"></a>

## 示例代码<a name="zh-cn_topic_0173848866_section20261580353"></a>

获取OBS SDK client。示例代码如下：

```
from modelarts.session import Session
session = Session()
obs_client = session.get_obs_client()
```

获取“obs\_client“后， 可以对OBS进行全景操作，具体操作请参见[《对象存储服务SDK参考》](https://support.huaweicloud.com/sdk-python-devg-obs/zh-cn_topic_0119680901.html)。

