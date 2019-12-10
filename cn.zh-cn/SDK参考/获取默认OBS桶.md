# 获取默认OBS桶<a name="modelarts_04_0213"></a>

获取默认桶名为“modelarts-\{region\_name\}-\{project\_id-md5\}“的OBS桶； 若该OBS桶不存在，则默认新建。

## 示例代码<a name="zh-cn_topic_0173854964_section20261580353"></a>

```
from modelarts.session import Session
session = Session()
bucket_name = session.default_bucket()
```

## 参数说明<a name="zh-cn_topic_0173854964_section19871227372"></a>

**表 1**  请求参数说明

<a name="zh-cn_topic_0173854964_table155461191218"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173854964_row254817912212"><th class="cellrowborder" valign="top" width="19.87%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0173854964_p12549899214"><a name="zh-cn_topic_0173854964_p12549899214"></a><a name="zh-cn_topic_0173854964_p12549899214"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13.540000000000003%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0173854964_p3552101193813"><a name="zh-cn_topic_0173854964_p3552101193813"></a><a name="zh-cn_topic_0173854964_p3552101193813"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.400000000000002%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0173854964_p1755169172118"><a name="zh-cn_topic_0173854964_p1755169172118"></a><a name="zh-cn_topic_0173854964_p1755169172118"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="46.190000000000005%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0173854964_p55521998211"><a name="zh-cn_topic_0173854964_p55521998211"></a><a name="zh-cn_topic_0173854964_p55521998211"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173854964_row8893215413"><td class="cellrowborder" valign="top" width="19.87%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0173854964_p6891421842"><a name="zh-cn_topic_0173854964_p6891421842"></a><a name="zh-cn_topic_0173854964_p6891421842"></a>session</p>
</td>
<td class="cellrowborder" valign="top" width="13.540000000000003%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173854964_p68972047"><a name="zh-cn_topic_0173854964_p68972047"></a><a name="zh-cn_topic_0173854964_p68972047"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.400000000000002%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173854964_p158912219419"><a name="zh-cn_topic_0173854964_p158912219419"></a><a name="zh-cn_topic_0173854964_p158912219419"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="46.190000000000005%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0173854964_p1689152543"><a name="zh-cn_topic_0173854964_p1689152543"></a><a name="zh-cn_topic_0173854964_p1689152543"></a>会话对象。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  成功响应参数说明

<a name="zh-cn_topic_0173854964_table973120224596"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173854964_row2731522195910"><th class="cellrowborder" valign="top" width="24.91249124912491%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0173854964_p57306225598"><a name="zh-cn_topic_0173854964_p57306225598"></a><a name="zh-cn_topic_0173854964_p57306225598"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="24.21242124212421%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0173854964_p117308225593"><a name="zh-cn_topic_0173854964_p117308225593"></a><a name="zh-cn_topic_0173854964_p117308225593"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.87508750875088%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0173854964_p2730132255915"><a name="zh-cn_topic_0173854964_p2730132255915"></a><a name="zh-cn_topic_0173854964_p2730132255915"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173854964_row1873172215912"><td class="cellrowborder" valign="top" width="24.91249124912491%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173854964_p4731322145919"><a name="zh-cn_topic_0173854964_p4731322145919"></a><a name="zh-cn_topic_0173854964_p4731322145919"></a>bucket_name</p>
</td>
<td class="cellrowborder" valign="top" width="24.21242124212421%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173854964_p117311922115916"><a name="zh-cn_topic_0173854964_p117311922115916"></a><a name="zh-cn_topic_0173854964_p117311922115916"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.87508750875088%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173854964_p6731182225914"><a name="zh-cn_topic_0173854964_p6731182225914"></a><a name="zh-cn_topic_0173854964_p6731182225914"></a>OBS桶名。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  失败响应参数说明

<a name="zh-cn_topic_0173854964_table55928961173927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173854964_row40618446173927"><th class="cellrowborder" valign="top" width="25.490000000000002%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0173854964_p1631242217407"><a name="zh-cn_topic_0173854964_p1631242217407"></a><a name="zh-cn_topic_0173854964_p1631242217407"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="23.72%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0173854964_p5427574117407"><a name="zh-cn_topic_0173854964_p5427574117407"></a><a name="zh-cn_topic_0173854964_p5427574117407"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.79%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0173854964_p12364118914"><a name="zh-cn_topic_0173854964_p12364118914"></a><a name="zh-cn_topic_0173854964_p12364118914"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173854964_row11062410173927"><td class="cellrowborder" valign="top" width="25.490000000000002%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173854964_p688954611624"><a name="zh-cn_topic_0173854964_p688954611624"></a><a name="zh-cn_topic_0173854964_p688954611624"></a>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="23.72%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173854964_p3804851211624"><a name="zh-cn_topic_0173854964_p3804851211624"></a><a name="zh-cn_topic_0173854964_p3804851211624"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173854964_p156551524172412"><a name="zh-cn_topic_0173854964_p156551524172412"></a><a name="zh-cn_topic_0173854964_p156551524172412"></a>调用失败时的错误码。</p>
<p id="zh-cn_topic_0173854964_p6203060911624"><a name="zh-cn_topic_0173854964_p6203060911624"></a><a name="zh-cn_topic_0173854964_p6203060911624"></a>调用成功时无此字段。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173854964_row52351653173927"><td class="cellrowborder" valign="top" width="25.490000000000002%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173854964_p4368550411624"><a name="zh-cn_topic_0173854964_p4368550411624"></a><a name="zh-cn_topic_0173854964_p4368550411624"></a>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="23.72%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173854964_p6574380911624"><a name="zh-cn_topic_0173854964_p6574380911624"></a><a name="zh-cn_topic_0173854964_p6574380911624"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173854964_p1277593619"><a name="zh-cn_topic_0173854964_p1277593619"></a><a name="zh-cn_topic_0173854964_p1277593619"></a>调用失败时的错误信息。</p>
<p id="zh-cn_topic_0173854964_p2364831411624"><a name="zh-cn_topic_0173854964_p2364831411624"></a><a name="zh-cn_topic_0173854964_p2364831411624"></a>调用成功时无此字段。</p>
</td>
</tr>
</tbody>
</table>

