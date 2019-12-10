# 查询OBS同步状态<a name="modelarts_04_0032"></a>

## 示例代码<a name="section35881040102516"></a>

用户可以使用该接口查询OBS数据同步状态。示例代码如下：

```
from modelarts import config
from modelarts.client.api import *
client = config.create_client(context="default")
dasApi = DataAnnotationsApi(client)
dasApi.sync_obs_status( project_id = "cc0f0990a56f*****41c85e79cc511c9", data_annotation_id = "282")
```

## 参数说明<a name="section0599140112517"></a>

**表 1**  参数说明

<a name="table160254042515"></a>
<table><thead align="left"><tr id="row141641202511"><th class="cellrowborder" valign="top" width="23.54%" id="mcps1.2.4.1.1"><p id="p11941182519"><a name="p11941182519"></a><a name="p11941182519"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.2"><p id="p611141142510"><a name="p611141142510"></a><a name="p611141142510"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="54.400000000000006%" id="mcps1.2.4.1.3"><p id="p917419250"><a name="p917419250"></a><a name="p917419250"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row811541192518"><td class="cellrowborder" valign="top" width="23.54%" headers="mcps1.2.4.1.1 "><p id="p3514192815463"><a name="p3514192815463"></a><a name="p3514192815463"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.2 "><p id="p1014418254"><a name="p1014418254"></a><a name="p1014418254"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1421441152511"><a name="p1421441152511"></a><a name="p1421441152511"></a>用户项目ID。获取项目ID的操作指导请参见<a href="查看项目ID.md">查看项目ID</a>。</p>
</td>
</tr>
<tr id="row18274192519"><td class="cellrowborder" valign="top" width="23.54%" headers="mcps1.2.4.1.1 "><p id="p2280108135810"><a name="p2280108135810"></a><a name="p2280108135810"></a>data_annotation_id</p>
</td>
<td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.2 "><p id="p5830446517014"><a name="p5830446517014"></a><a name="p5830446517014"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p2504119917014"><a name="p2504119917014"></a><a name="p2504119917014"></a>人工标注作业ID。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  sync\_obs\_status返回参数说明

<a name="table55928961173927"></a>
<table><thead align="left"><tr id="row40618446173927"><th class="cellrowborder" valign="top" width="21%" id="mcps1.2.5.1.1"><p id="p1631242217407"><a name="p1631242217407"></a><a name="p1631242217407"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.21%" id="mcps1.2.5.1.2"><p id="p4623781817407"><a name="p4623781817407"></a><a name="p4623781817407"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.69%" id="mcps1.2.5.1.3"><p id="p5427574117407"><a name="p5427574117407"></a><a name="p5427574117407"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="53.1%" id="mcps1.2.5.1.4"><p id="p3425893817407"><a name="p3425893817407"></a><a name="p3425893817407"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2067616225120"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.1 "><p id="p61635236103529"><a name="p61635236103529"></a><a name="p61635236103529"></a>is_success</p>
</td>
<td class="cellrowborder" valign="top" width="12.21%" headers="mcps1.2.5.1.2 "><p id="p26398204103529"><a name="p26398204103529"></a><a name="p26398204103529"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.69%" headers="mcps1.2.5.1.3 "><p id="p57879756103529"><a name="p57879756103529"></a><a name="p57879756103529"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="53.1%" headers="mcps1.2.5.1.4 "><p id="p57748669103529"><a name="p57748669103529"></a><a name="p57748669103529"></a>请求是否成功。</p>
</td>
</tr>
<tr id="row11062410173927"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.1 "><p id="p29459863"><a name="p29459863"></a><a name="p29459863"></a>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="12.21%" headers="mcps1.2.5.1.2 "><p id="p452712527397"><a name="p452712527397"></a><a name="p452712527397"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.69%" headers="mcps1.2.5.1.3 "><p id="p37438696"><a name="p37438696"></a><a name="p37438696"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.1%" headers="mcps1.2.5.1.4 "><p id="p1713625211221"><a name="p1713625211221"></a><a name="p1713625211221"></a>调用失败时的错误码，具体请参见<a href="公共参数.md#section29446341644">错误码说明</a>。</p>
<p id="zh-cn_topic_0087142444_p1765688919540"><a name="zh-cn_topic_0087142444_p1765688919540"></a><a name="zh-cn_topic_0087142444_p1765688919540"></a>调用成功时无此字段。</p>
</td>
</tr>
<tr id="row52351653173927"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.1 "><p id="p17366021"><a name="p17366021"></a><a name="p17366021"></a>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="12.21%" headers="mcps1.2.5.1.2 "><p id="p252755263915"><a name="p252755263915"></a><a name="p252755263915"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.69%" headers="mcps1.2.5.1.3 "><p id="p64470493"><a name="p64470493"></a><a name="p64470493"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.1%" headers="mcps1.2.5.1.4 "><p id="p1749719179616"><a name="p1749719179616"></a><a name="p1749719179616"></a>调用失败时的错误信息。</p>
<p id="zh-cn_topic_0087142444_p5470566619540"><a name="zh-cn_topic_0087142444_p5470566619540"></a><a name="zh-cn_topic_0087142444_p5470566619540"></a>调用成功时无此字段。</p>
</td>
</tr>
<tr id="row6521135122311"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.1 "><p id="p152814911553"><a name="p152814911553"></a><a name="p152814911553"></a>sync_status</p>
</td>
<td class="cellrowborder" valign="top" width="12.21%" headers="mcps1.2.5.1.2 "><p id="p62864985518"><a name="p62864985518"></a><a name="p62864985518"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.69%" headers="mcps1.2.5.1.3 "><p id="p1826174910553"><a name="p1826174910553"></a><a name="p1826174910553"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="53.1%" headers="mcps1.2.5.1.4 "><p id="p1524249135520"><a name="p1524249135520"></a><a name="p1524249135520"></a>同步状态码，具体请参见<a href="#table149536404533">表3</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  同步状态码

<a name="table149536404533"></a>
<table><thead align="left"><tr id="row14953840105316"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0105159288_p10118881153428"><a name="zh-cn_topic_0105159288_p10118881153428"></a><a name="zh-cn_topic_0105159288_p10118881153428"></a>状态值</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0105159288_p14323003153428"><a name="zh-cn_topic_0105159288_p14323003153428"></a><a name="zh-cn_topic_0105159288_p14323003153428"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row59533406534"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p595317407533"><a name="p595317407533"></a><a name="p595317407533"></a>0</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p7955124018531"><a name="p7955124018531"></a><a name="p7955124018531"></a>未开始同步。</p>
</td>
</tr>
<tr id="row89558407537"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p15955840205316"><a name="p15955840205316"></a><a name="p15955840205316"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p169559407534"><a name="p169559407534"></a><a name="p169559407534"></a>同步成功。</p>
</td>
</tr>
<tr id="row8955194045313"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p18955440115314"><a name="p18955440115314"></a><a name="p18955440115314"></a>2</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1595514401531"><a name="p1595514401531"></a><a name="p1595514401531"></a>同步失败。</p>
</td>
</tr>
<tr id="row1195516407538"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p295511409533"><a name="p295511409533"></a><a name="p295511409533"></a>3</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p2028533795714"><a name="p2028533795714"></a><a name="p2028533795714"></a>正在同步中。</p>
</td>
</tr>
</tbody>
</table>

