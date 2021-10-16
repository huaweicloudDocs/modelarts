# 从OBS下载文件夹<a name="modelarts_04_0221"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>当单个文件大小超过5GB时，无法使用此方式下载此文件。但是此文件夹下其他小于5GB的文件可下载成功。

## 示例代码<a name="zh-cn_topic_0173848863_section20261580353"></a>

在ModelArts notebook平台中，Session鉴权无需输入鉴权参数。其它平台的Session鉴权请参考[Session鉴权](Session鉴权.md)。

```
from modelarts.session import Session
session = Session()
session.obs.download_dir(src_obs_dir="obs://bucket-name/dir1/", dst_local_dir="/home/ma-user/")
```

示例代码执行后，OBS源文件夹“dir1“被下载至本地“/home/ma-user/dir1/“。

## 参数说明<a name="zh-cn_topic_0173848863_section78291820269"></a>

**表 1**  请求参数说明

<a name="zh-cn_topic_0173848863_table155461191218"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173848863_row254817912212"><th class="cellrowborder" valign="top" width="20.75%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0173848863_p12549899214"><a name="zh-cn_topic_0173848863_p12549899214"></a><a name="zh-cn_topic_0173848863_p12549899214"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="11.99%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0173848863_p3552101193813"><a name="zh-cn_topic_0173848863_p3552101193813"></a><a name="zh-cn_topic_0173848863_p3552101193813"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.320000000000002%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0173848863_p1755169172118"><a name="zh-cn_topic_0173848863_p1755169172118"></a><a name="zh-cn_topic_0173848863_p1755169172118"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="53.94%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0173848863_p55521998211"><a name="zh-cn_topic_0173848863_p55521998211"></a><a name="zh-cn_topic_0173848863_p55521998211"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173848863_row8893215413"><td class="cellrowborder" valign="top" width="20.75%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0173848863_p6891421842"><a name="zh-cn_topic_0173848863_p6891421842"></a><a name="zh-cn_topic_0173848863_p6891421842"></a>session</p>
</td>
<td class="cellrowborder" valign="top" width="11.99%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173848863_p68972047"><a name="zh-cn_topic_0173848863_p68972047"></a><a name="zh-cn_topic_0173848863_p68972047"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.320000000000002%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173848863_p158912219419"><a name="zh-cn_topic_0173848863_p158912219419"></a><a name="zh-cn_topic_0173848863_p158912219419"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="53.94%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0173848863_p1689152543"><a name="zh-cn_topic_0173848863_p1689152543"></a><a name="zh-cn_topic_0173848863_p1689152543"></a>会话对象。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173848863_row1530181931"><td class="cellrowborder" valign="top" width="20.75%" headers="mcps1.2.5.1.1 "><p id="p1315881682013"><a name="p1315881682013"></a><a name="p1315881682013"></a>src_obs_dir</p>
</td>
<td class="cellrowborder" valign="top" width="11.99%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173848863_p6675978319"><a name="zh-cn_topic_0173848863_p6675978319"></a><a name="zh-cn_topic_0173848863_p6675978319"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.320000000000002%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173848863_p46751171339"><a name="zh-cn_topic_0173848863_p46751171339"></a><a name="zh-cn_topic_0173848863_p46751171339"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.94%" headers="mcps1.2.5.1.4 "><p id="p19233184612200"><a name="p19233184612200"></a><a name="p19233184612200"></a>下载的源OBS文件夹，必须以<span class="filepath" id="filepath416152032116"><a name="filepath416152032116"></a><a name="filepath416152032116"></a>“obs://”</span>作为前缀，文件夹后缀必须以"/"结尾。当下载的文件夹下有文件夹且内容为空时，对应路径下不产生对应空文件夹。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173848863_row167932713277"><td class="cellrowborder" valign="top" width="20.75%" headers="mcps1.2.5.1.1 "><p id="p36098872111"><a name="p36098872111"></a><a name="p36098872111"></a>dst_local_dir</p>
</td>
<td class="cellrowborder" valign="top" width="11.99%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173848863_p77948710279"><a name="zh-cn_topic_0173848863_p77948710279"></a><a name="zh-cn_topic_0173848863_p77948710279"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.320000000000002%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173848863_p3794167192716"><a name="zh-cn_topic_0173848863_p3794167192716"></a><a name="zh-cn_topic_0173848863_p3794167192716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.94%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0173848863_p1479417112711"><a name="zh-cn_topic_0173848863_p1479417112711"></a><a name="zh-cn_topic_0173848863_p1479417112711"></a>下载的目标本地文件夹，下载的目标本地文件夹后缀必须以<span class="filepath" id="filepath12232102862116"><a name="filepath12232102862116"></a><a name="filepath12232102862116"></a>“/”</span>结尾。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  失败响应参数说明

<a name="zh-cn_topic_0173848863_table55928961173927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173848863_row40618446173927"><th class="cellrowborder" valign="top" width="25.490000000000002%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0173848863_p1631242217407"><a name="zh-cn_topic_0173848863_p1631242217407"></a><a name="zh-cn_topic_0173848863_p1631242217407"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="23.72%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0173848863_p5427574117407"><a name="zh-cn_topic_0173848863_p5427574117407"></a><a name="zh-cn_topic_0173848863_p5427574117407"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.79%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0173848863_p12364118914"><a name="zh-cn_topic_0173848863_p12364118914"></a><a name="zh-cn_topic_0173848863_p12364118914"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173848863_row11062410173927"><td class="cellrowborder" valign="top" width="25.490000000000002%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173848863_p688954611624"><a name="zh-cn_topic_0173848863_p688954611624"></a><a name="zh-cn_topic_0173848863_p688954611624"></a>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="23.72%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173848863_p3804851211624"><a name="zh-cn_topic_0173848863_p3804851211624"></a><a name="zh-cn_topic_0173848863_p3804851211624"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173848863_p156551524172412"><a name="zh-cn_topic_0173848863_p156551524172412"></a><a name="zh-cn_topic_0173848863_p156551524172412"></a>调用失败时的错误码。</p>
<p id="zh-cn_topic_0173848863_p6203060911624"><a name="zh-cn_topic_0173848863_p6203060911624"></a><a name="zh-cn_topic_0173848863_p6203060911624"></a>调用成功时无此字段。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173848863_row52351653173927"><td class="cellrowborder" valign="top" width="25.490000000000002%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173848863_p4368550411624"><a name="zh-cn_topic_0173848863_p4368550411624"></a><a name="zh-cn_topic_0173848863_p4368550411624"></a>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="23.72%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173848863_p6574380911624"><a name="zh-cn_topic_0173848863_p6574380911624"></a><a name="zh-cn_topic_0173848863_p6574380911624"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173848863_p1277593619"><a name="zh-cn_topic_0173848863_p1277593619"></a><a name="zh-cn_topic_0173848863_p1277593619"></a>调用失败时的错误信息。</p>
<p id="zh-cn_topic_0173848863_p2364831411624"><a name="zh-cn_topic_0173848863_p2364831411624"></a><a name="zh-cn_topic_0173848863_p2364831411624"></a>调用成功时无此字段。</p>
</td>
</tr>
</tbody>
</table>

