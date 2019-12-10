# 用户AK-SK认证模式<a name="modelarts_04_0155"></a>

本模式支持[OBS管理](OBS管理概述.md)、[作业管理](创建训练作业.md)、[模型管理](导入模型.md)、[服务管理](服务管理概述.md)模块的鉴权。

## 示例代码<a name="zh-cn_topic_0173871416_section1139662914522"></a>

-   AK/SK获取方式请参见[认证鉴权](https://support.huaweicloud.com/api-modelarts/modelarts_03_0004.html)。
-   示例代码：

    ```
    from modelarts.session import Session
    session = Session(access_key='***',secret_key='***', project_id='***', region_name='***')
    ```


