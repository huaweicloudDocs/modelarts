# 在OBS中创建文件夹<a name="modelarts_04_0128"></a>

## 示例代码<a name="zh-cn_topic_0173848864_section20261580353"></a>

在OBS中创建文件夹。示例代码如下：

```
from modelarts.session import Session
session = Session()
session.create_directory(bucket="bucket_name",directory = "/dir1/dir2/")
```

## 参数说明<a name="zh-cn_topic_0173848864_section12298769610"></a>

**表 1**  请求参数说明

<a name="zh-cn_topic_0173848864_table155461191218"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173848864_row254817912212"><th class="cellrowborder" valign="top" width="25.630000000000003%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0173848864_p12549899214"><a name="zh-cn_topic_0173848864_p12549899214"></a><a name="zh-cn_topic_0173848864_p12549899214"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.410000000000002%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0173848864_p3552101193813"><a name="zh-cn_topic_0173848864_p3552101193813"></a><a name="zh-cn_topic_0173848864_p3552101193813"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="11.32%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0173848864_p1755169172118"><a name="zh-cn_topic_0173848864_p1755169172118"></a><a name="zh-cn_topic_0173848864_p1755169172118"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.64000000000001%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0173848864_p55521998211"><a name="zh-cn_topic_0173848864_p55521998211"></a><a name="zh-cn_topic_0173848864_p55521998211"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173848864_row1530181931"><td class="cellrowborder" valign="top" width="25.630000000000003%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0173848864_p8675871731"><a name="zh-cn_topic_0173848864_p8675871731"></a><a name="zh-cn_topic_0173848864_p8675871731"></a>bucket</p>
</td>
<td class="cellrowborder" valign="top" width="12.410000000000002%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173848864_p6675978319"><a name="zh-cn_topic_0173848864_p6675978319"></a><a name="zh-cn_topic_0173848864_p6675978319"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="11.32%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173848864_p46751171339"><a name="zh-cn_topic_0173848864_p46751171339"></a><a name="zh-cn_topic_0173848864_p46751171339"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.64000000000001%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0173848864_p467516712319"><a name="zh-cn_topic_0173848864_p467516712319"></a><a name="zh-cn_topic_0173848864_p467516712319"></a>OBS桶名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173848864_row1823612338105"><td class="cellrowborder" valign="top" width="25.630000000000003%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0173848864_p202361133171010"><a name="zh-cn_topic_0173848864_p202361133171010"></a><a name="zh-cn_topic_0173848864_p202361133171010"></a>directory</p>
</td>
<td class="cellrowborder" valign="top" width="12.410000000000002%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173848864_p323620334108"><a name="zh-cn_topic_0173848864_p323620334108"></a><a name="zh-cn_topic_0173848864_p323620334108"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="11.32%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173848864_p11236103314102"><a name="zh-cn_topic_0173848864_p11236103314102"></a><a name="zh-cn_topic_0173848864_p11236103314102"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.64000000000001%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0173848864_p1923683317105"><a name="zh-cn_topic_0173848864_p1923683317105"></a><a name="zh-cn_topic_0173848864_p1923683317105"></a>预创建的文件夹路径。格式为<span class="filepath" id="filepath670214255124"><a name="filepath670214255124"></a><a name="filepath670214255124"></a>“/dir1/dir2/”</span>，若dir1目录已存在，则在dir1目录下创建dir2目录；若dir1目录不存在，则创建目录/dir1/dir2/。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  失败响应参数说明

<a name="zh-cn_topic_0173848864_table55928961173927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173848864_row40618446173927"><th class="cellrowborder" valign="top" width="25.490000000000002%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0173848864_p1631242217407"><a name="zh-cn_topic_0173848864_p1631242217407"></a><a name="zh-cn_topic_0173848864_p1631242217407"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="23.72%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0173848864_p5427574117407"><a name="zh-cn_topic_0173848864_p5427574117407"></a><a name="zh-cn_topic_0173848864_p5427574117407"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.79%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0173848864_p12364118914"><a name="zh-cn_topic_0173848864_p12364118914"></a><a name="zh-cn_topic_0173848864_p12364118914"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173848864_row11062410173927"><td class="cellrowborder" valign="top" width="25.490000000000002%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173848864_p688954611624"><a name="zh-cn_topic_0173848864_p688954611624"></a><a name="zh-cn_topic_0173848864_p688954611624"></a>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="23.72%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173848864_p3804851211624"><a name="zh-cn_topic_0173848864_p3804851211624"></a><a name="zh-cn_topic_0173848864_p3804851211624"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173848864_p156551524172412"><a name="zh-cn_topic_0173848864_p156551524172412"></a><a name="zh-cn_topic_0173848864_p156551524172412"></a>调用失败时的错误码。</p>
<p id="zh-cn_topic_0173848864_p6203060911624"><a name="zh-cn_topic_0173848864_p6203060911624"></a><a name="zh-cn_topic_0173848864_p6203060911624"></a>调用成功时无此字段。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173848864_row52351653173927"><td class="cellrowborder" valign="top" width="25.490000000000002%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173848864_p4368550411624"><a name="zh-cn_topic_0173848864_p4368550411624"></a><a name="zh-cn_topic_0173848864_p4368550411624"></a>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="23.72%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173848864_p6574380911624"><a name="zh-cn_topic_0173848864_p6574380911624"></a><a name="zh-cn_topic_0173848864_p6574380911624"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173848864_p1277593619"><a name="zh-cn_topic_0173848864_p1277593619"></a><a name="zh-cn_topic_0173848864_p1277593619"></a>调用失败时的错误信息。</p>
<p id="zh-cn_topic_0173848864_p2364831411624"><a name="zh-cn_topic_0173848864_p2364831411624"></a><a name="zh-cn_topic_0173848864_p2364831411624"></a>调用成功时无此字段。</p>
</td>
</tr>
</tbody>
</table>

