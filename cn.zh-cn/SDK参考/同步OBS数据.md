# 同步OBS数据<a name="modelarts_04_0031"></a>

## 示例代码<a name="section35881040102516"></a>

用户可以使用该接口同步OBS数据。示例代码如下：

```
from modelarts import config
from modelarts.client.api import *
client = config.create_client(context="default")
dasApi = DataAnnotationsApi(client)
dasApi.sync_obs( project_id = "cc0f0990a56f*****41c85e79cc511c9", data_annotation_id = "282")
```

## 参数说明<a name="section0599140112517"></a>

**表 1**  参数说明

<a name="table160254042515"></a>
<table><thead align="left"><tr id="row141641202511"><th class="cellrowborder" valign="top" width="26.33%" id="mcps1.2.4.1.1"><p id="p11941182519"><a name="p11941182519"></a><a name="p11941182519"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20.1%" id="mcps1.2.4.1.2"><p id="p611141142510"><a name="p611141142510"></a><a name="p611141142510"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="53.56999999999999%" id="mcps1.2.4.1.3"><p id="p917419250"><a name="p917419250"></a><a name="p917419250"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row811541192518"><td class="cellrowborder" valign="top" width="26.33%" headers="mcps1.2.4.1.1 "><p id="p3514192815463"><a name="p3514192815463"></a><a name="p3514192815463"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="20.1%" headers="mcps1.2.4.1.2 "><p id="p1014418254"><a name="p1014418254"></a><a name="p1014418254"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.56999999999999%" headers="mcps1.2.4.1.3 "><p id="p1421441152511"><a name="p1421441152511"></a><a name="p1421441152511"></a>用户项目ID。获取项目ID的操作指导请参见<a href="查看项目ID.md">查看项目ID</a>。</p>
</td>
</tr>
<tr id="row18274192519"><td class="cellrowborder" valign="top" width="26.33%" headers="mcps1.2.4.1.1 "><p id="p2280108135810"><a name="p2280108135810"></a><a name="p2280108135810"></a>data_annotation_id</p>
</td>
<td class="cellrowborder" valign="top" width="20.1%" headers="mcps1.2.4.1.2 "><p id="p5830446517014"><a name="p5830446517014"></a><a name="p5830446517014"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.56999999999999%" headers="mcps1.2.4.1.3 "><p id="p2504119917014"><a name="p2504119917014"></a><a name="p2504119917014"></a>人工标注作业ID。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  sync\_obs返回参数说明

<a name="table55928961173927"></a>
<table><thead align="left"><tr id="row40618446173927"><th class="cellrowborder" valign="top" width="17.96%" id="mcps1.2.5.1.1"><p id="p1631242217407"><a name="p1631242217407"></a><a name="p1631242217407"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.220000000000002%" id="mcps1.2.5.1.2"><p id="p4623781817407"><a name="p4623781817407"></a><a name="p4623781817407"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.55%" id="mcps1.2.5.1.3"><p id="p5427574117407"><a name="p5427574117407"></a><a name="p5427574117407"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="53.269999999999996%" id="mcps1.2.5.1.4"><p id="p3425893817407"><a name="p3425893817407"></a><a name="p3425893817407"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row184441517131213"><td class="cellrowborder" valign="top" width="17.96%" headers="mcps1.2.5.1.1 "><p id="p61635236103529"><a name="p61635236103529"></a><a name="p61635236103529"></a>is_success</p>
</td>
<td class="cellrowborder" valign="top" width="16.220000000000002%" headers="mcps1.2.5.1.2 "><p id="p26398204103529"><a name="p26398204103529"></a><a name="p26398204103529"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.55%" headers="mcps1.2.5.1.3 "><p id="p57879756103529"><a name="p57879756103529"></a><a name="p57879756103529"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.5.1.4 "><p id="p57748669103529"><a name="p57748669103529"></a><a name="p57748669103529"></a>请求是否成功。</p>
</td>
</tr>
<tr id="row11062410173927"><td class="cellrowborder" valign="top" width="17.96%" headers="mcps1.2.5.1.1 "><p id="p29459863"><a name="p29459863"></a><a name="p29459863"></a>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="16.220000000000002%" headers="mcps1.2.5.1.2 "><p id="p452712527397"><a name="p452712527397"></a><a name="p452712527397"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.55%" headers="mcps1.2.5.1.3 "><p id="p37438696"><a name="p37438696"></a><a name="p37438696"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.5.1.4 "><p id="p33021548172217"><a name="p33021548172217"></a><a name="p33021548172217"></a>调用失败时的错误码，具体请参见<a href="公共参数.md#section29446341644">错误码说明</a>。</p>
<p id="zh-cn_topic_0087142444_p1765688919540"><a name="zh-cn_topic_0087142444_p1765688919540"></a><a name="zh-cn_topic_0087142444_p1765688919540"></a>调用成功时无此字段。</p>
</td>
</tr>
<tr id="row52351653173927"><td class="cellrowborder" valign="top" width="17.96%" headers="mcps1.2.5.1.1 "><p id="p17366021"><a name="p17366021"></a><a name="p17366021"></a>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="16.220000000000002%" headers="mcps1.2.5.1.2 "><p id="p252755263915"><a name="p252755263915"></a><a name="p252755263915"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.55%" headers="mcps1.2.5.1.3 "><p id="p64470493"><a name="p64470493"></a><a name="p64470493"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.5.1.4 "><p id="p16927141313613"><a name="p16927141313613"></a><a name="p16927141313613"></a>调用失败时的错误信息。</p>
<p id="zh-cn_topic_0087142444_p5470566619540"><a name="zh-cn_topic_0087142444_p5470566619540"></a><a name="zh-cn_topic_0087142444_p5470566619540"></a>调用成功时无此字段。</p>
</td>
</tr>
</tbody>
</table>

