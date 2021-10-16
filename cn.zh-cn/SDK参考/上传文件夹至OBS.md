# 上传文件夹至OBS<a name="modelarts_04_0219"></a>

## 示例代码<a name="section68941956195211"></a>

在ModelArts notebook平台中，Session鉴权无需输入鉴权参数。其它平台的Session鉴权请参考[Session鉴权](Session鉴权.md)。

```
from modelarts.session import Session
session = Session()
session.obs.upload_dir(src_local_dir='/home/ma-user/', dst_obs_dir='obs://bucket-name/dir1/')
```

示例代码执行后，本地源文件夹“/ma-user/“被上传至“bucket-name“桶的“dir1“文件夹下，路径为“obs://bucket-name/dir1/ma-user/“。其中，桶名称和文件夹的名称均可以按照业务需求自定义。

## 参数说明<a name="zh-cn_topic_0173848862_section520413412065"></a>

**表 1**  请求参数说明

<a name="zh-cn_topic_0173848862_table155461191218"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173848862_row254817912212"><th class="cellrowborder" valign="top" width="19.869999999999997%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0173848862_p12549899214"><a name="zh-cn_topic_0173848862_p12549899214"></a><a name="zh-cn_topic_0173848862_p12549899214"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="11.32%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0173848862_p3552101193813"><a name="zh-cn_topic_0173848862_p3552101193813"></a><a name="zh-cn_topic_0173848862_p3552101193813"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="14.32%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0173848862_p1755169172118"><a name="zh-cn_topic_0173848862_p1755169172118"></a><a name="zh-cn_topic_0173848862_p1755169172118"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="54.49%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0173848862_p55521998211"><a name="zh-cn_topic_0173848862_p55521998211"></a><a name="zh-cn_topic_0173848862_p55521998211"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173848862_row8893215413"><td class="cellrowborder" valign="top" width="19.869999999999997%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0173848862_p6891421842"><a name="zh-cn_topic_0173848862_p6891421842"></a><a name="zh-cn_topic_0173848862_p6891421842"></a>session</p>
</td>
<td class="cellrowborder" valign="top" width="11.32%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173848862_p68972047"><a name="zh-cn_topic_0173848862_p68972047"></a><a name="zh-cn_topic_0173848862_p68972047"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.32%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173848862_p158912219419"><a name="zh-cn_topic_0173848862_p158912219419"></a><a name="zh-cn_topic_0173848862_p158912219419"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="54.49%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0173848862_p1689152543"><a name="zh-cn_topic_0173848862_p1689152543"></a><a name="zh-cn_topic_0173848862_p1689152543"></a>会话对象。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173848862_row1530181931"><td class="cellrowborder" valign="top" width="19.869999999999997%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0173848862_p8675871731"><a name="zh-cn_topic_0173848862_p8675871731"></a><a name="zh-cn_topic_0173848862_p8675871731"></a>src_local_dir</p>
</td>
<td class="cellrowborder" valign="top" width="11.32%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173848862_p6675978319"><a name="zh-cn_topic_0173848862_p6675978319"></a><a name="zh-cn_topic_0173848862_p6675978319"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.32%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173848862_p46751171339"><a name="zh-cn_topic_0173848862_p46751171339"></a><a name="zh-cn_topic_0173848862_p46751171339"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.49%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0173848862_p467516712319"><a name="zh-cn_topic_0173848862_p467516712319"></a><a name="zh-cn_topic_0173848862_p467516712319"></a>本地需要上传的文件夹路径。</p>
<p id="p714155612517"><a name="p714155612517"></a><a name="p714155612517"></a>当上传的文件夹下内容为空或者该文件夹下包含多个文件夹且有文件夹下内容有空时，OBS对应路径下不产生该空文件夹。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173848862_row167932713277"><td class="cellrowborder" valign="top" width="19.869999999999997%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0173848862_p5794079274"><a name="zh-cn_topic_0173848862_p5794079274"></a><a name="zh-cn_topic_0173848862_p5794079274"></a>dst_obs_dir</p>
</td>
<td class="cellrowborder" valign="top" width="11.32%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173848862_p77948710279"><a name="zh-cn_topic_0173848862_p77948710279"></a><a name="zh-cn_topic_0173848862_p77948710279"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.32%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173848862_p3794167192716"><a name="zh-cn_topic_0173848862_p3794167192716"></a><a name="zh-cn_topic_0173848862_p3794167192716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.49%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0173848862_p461991742117"><a name="zh-cn_topic_0173848862_p461991742117"></a><a name="zh-cn_topic_0173848862_p461991742117"></a>上传的目标OBS桶地址，必须以<span class="filepath" id="filepath416152032116"><a name="filepath416152032116"></a><a name="filepath416152032116"></a>“obs://”</span>作为前缀，上传的目标文件夹后缀必须以<span class="filepath" id="filepath12232102862116"><a name="filepath12232102862116"></a><a name="filepath12232102862116"></a>“/”</span>结尾。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  失败响应参数说明

<a name="zh-cn_topic_0173848862_table55928961173927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173848862_row40618446173927"><th class="cellrowborder" valign="top" width="24.86%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0173848862_p1631242217407"><a name="zh-cn_topic_0173848862_p1631242217407"></a><a name="zh-cn_topic_0173848862_p1631242217407"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20.75%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0173848862_p5427574117407"><a name="zh-cn_topic_0173848862_p5427574117407"></a><a name="zh-cn_topic_0173848862_p5427574117407"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="54.39000000000001%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0173848862_p12364118914"><a name="zh-cn_topic_0173848862_p12364118914"></a><a name="zh-cn_topic_0173848862_p12364118914"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173848862_row11062410173927"><td class="cellrowborder" valign="top" width="24.86%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173848862_p688954611624"><a name="zh-cn_topic_0173848862_p688954611624"></a><a name="zh-cn_topic_0173848862_p688954611624"></a>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="20.75%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173848862_p3804851211624"><a name="zh-cn_topic_0173848862_p3804851211624"></a><a name="zh-cn_topic_0173848862_p3804851211624"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.39000000000001%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173848862_p156551524172412"><a name="zh-cn_topic_0173848862_p156551524172412"></a><a name="zh-cn_topic_0173848862_p156551524172412"></a>调用失败时的错误码。</p>
<p id="zh-cn_topic_0173848862_p6203060911624"><a name="zh-cn_topic_0173848862_p6203060911624"></a><a name="zh-cn_topic_0173848862_p6203060911624"></a>调用成功时无此字段。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173848862_row52351653173927"><td class="cellrowborder" valign="top" width="24.86%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173848862_p4368550411624"><a name="zh-cn_topic_0173848862_p4368550411624"></a><a name="zh-cn_topic_0173848862_p4368550411624"></a>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20.75%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173848862_p6574380911624"><a name="zh-cn_topic_0173848862_p6574380911624"></a><a name="zh-cn_topic_0173848862_p6574380911624"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.39000000000001%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173848862_p1277593619"><a name="zh-cn_topic_0173848862_p1277593619"></a><a name="zh-cn_topic_0173848862_p1277593619"></a>调用失败时的错误信息。</p>
<p id="zh-cn_topic_0173848862_p2364831411624"><a name="zh-cn_topic_0173848862_p2364831411624"></a><a name="zh-cn_topic_0173848862_p2364831411624"></a>调用成功时无此字段。</p>
</td>
</tr>
</tbody>
</table>

