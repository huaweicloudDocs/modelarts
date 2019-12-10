# 删除OBS桶<a name="modelarts_04_0129"></a>

## 示例代码<a name="zh-cn_topic_0173848865_section20261580353"></a>

删除OBS桶。示例代码如下：

```
from modelarts.session import Session
session = Session()
session.delete_bucket(bucket="bucket_name")
```

## 参数说明<a name="zh-cn_topic_0173848865_section185649437518"></a>

**表 1**  请求参数说明

<a name="zh-cn_topic_0173848865_table155461191218"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173848865_row254817912212"><th class="cellrowborder" valign="top" width="25.629999999999995%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0173848865_p12549899214"><a name="zh-cn_topic_0173848865_p12549899214"></a><a name="zh-cn_topic_0173848865_p12549899214"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.41%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0173848865_p3552101193813"><a name="zh-cn_topic_0173848865_p3552101193813"></a><a name="zh-cn_topic_0173848865_p3552101193813"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.76%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0173848865_p1755169172118"><a name="zh-cn_topic_0173848865_p1755169172118"></a><a name="zh-cn_topic_0173848865_p1755169172118"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.2%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0173848865_p55521998211"><a name="zh-cn_topic_0173848865_p55521998211"></a><a name="zh-cn_topic_0173848865_p55521998211"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173848865_row1530181931"><td class="cellrowborder" valign="top" width="25.629999999999995%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0173848865_p8675871731"><a name="zh-cn_topic_0173848865_p8675871731"></a><a name="zh-cn_topic_0173848865_p8675871731"></a>bucket</p>
</td>
<td class="cellrowborder" valign="top" width="12.41%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173848865_p6675978319"><a name="zh-cn_topic_0173848865_p6675978319"></a><a name="zh-cn_topic_0173848865_p6675978319"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.76%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173848865_p46751171339"><a name="zh-cn_topic_0173848865_p46751171339"></a><a name="zh-cn_topic_0173848865_p46751171339"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.2%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0173848865_p467516712319"><a name="zh-cn_topic_0173848865_p467516712319"></a><a name="zh-cn_topic_0173848865_p467516712319"></a>OBS桶名称。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  失败响应参数说明

<a name="zh-cn_topic_0173848865_table55928961173927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173848865_row40618446173927"><th class="cellrowborder" valign="top" width="25.490000000000002%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0173848865_p1631242217407"><a name="zh-cn_topic_0173848865_p1631242217407"></a><a name="zh-cn_topic_0173848865_p1631242217407"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="23.72%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0173848865_p5427574117407"><a name="zh-cn_topic_0173848865_p5427574117407"></a><a name="zh-cn_topic_0173848865_p5427574117407"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.79%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0173848865_p12364118914"><a name="zh-cn_topic_0173848865_p12364118914"></a><a name="zh-cn_topic_0173848865_p12364118914"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173848865_row11062410173927"><td class="cellrowborder" valign="top" width="25.490000000000002%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173848865_p688954611624"><a name="zh-cn_topic_0173848865_p688954611624"></a><a name="zh-cn_topic_0173848865_p688954611624"></a>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="23.72%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173848865_p3804851211624"><a name="zh-cn_topic_0173848865_p3804851211624"></a><a name="zh-cn_topic_0173848865_p3804851211624"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173848865_p156551524172412"><a name="zh-cn_topic_0173848865_p156551524172412"></a><a name="zh-cn_topic_0173848865_p156551524172412"></a>调用失败时的错误码。</p>
<p id="zh-cn_topic_0173848865_p6203060911624"><a name="zh-cn_topic_0173848865_p6203060911624"></a><a name="zh-cn_topic_0173848865_p6203060911624"></a>调用成功时无此字段。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173848865_row52351653173927"><td class="cellrowborder" valign="top" width="25.490000000000002%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173848865_p4368550411624"><a name="zh-cn_topic_0173848865_p4368550411624"></a><a name="zh-cn_topic_0173848865_p4368550411624"></a>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="23.72%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173848865_p6574380911624"><a name="zh-cn_topic_0173848865_p6574380911624"></a><a name="zh-cn_topic_0173848865_p6574380911624"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173848865_p1277593619"><a name="zh-cn_topic_0173848865_p1277593619"></a><a name="zh-cn_topic_0173848865_p1277593619"></a>调用失败时的错误信息。</p>
<p id="zh-cn_topic_0173848865_p2364831411624"><a name="zh-cn_topic_0173848865_p2364831411624"></a><a name="zh-cn_topic_0173848865_p2364831411624"></a>调用成功时无此字段。</p>
</td>
</tr>
</tbody>
</table>

