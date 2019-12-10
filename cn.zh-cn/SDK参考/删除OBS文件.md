# 删除OBS文件<a name="modelarts_04_0017"></a>

## 示例代码<a name="section35881040102516"></a>

用户可以使用该接口删除OBS文件。示例代码如下：

```
from modelarts import config
from modelarts.client import *
client = config.create_client(context="default")
datasetapi = DatasetApi(client)
resp = datasetapi.delete_file_from_obs(project_id="cbfb9585c5854926a411a3f5a984fc09", dataset_id="062ef90a-da4d-4af4-82ba-1523da57e78e", delete_files_spec={"deleted_url": ["README.md"]})
```

## 参数说明<a name="section0599140112517"></a>

**表 1**  参数说明

<a name="table1427122192918"></a>
<table><thead align="left"><tr id="row10299223299"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p19121533162912"><a name="p19121533162912"></a><a name="p19121533162912"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.18%" id="mcps1.2.5.1.2"><p id="p1812363372920"><a name="p1812363372920"></a><a name="p1812363372920"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="14.299999999999999%" id="mcps1.2.5.1.3"><p id="p21241133112918"><a name="p21241133112918"></a><a name="p21241133112918"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.519999999999996%" id="mcps1.2.5.1.4"><p id="p1812615330294"><a name="p1812615330294"></a><a name="p1812615330294"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1229142210294"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p121291133132913"><a name="p121291133132913"></a><a name="p121291133132913"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="16.18%" headers="mcps1.2.5.1.2 "><p id="p0130163312298"><a name="p0130163312298"></a><a name="p0130163312298"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.299999999999999%" headers="mcps1.2.5.1.3 "><p id="p1913233372918"><a name="p1913233372918"></a><a name="p1913233372918"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.519999999999996%" headers="mcps1.2.5.1.4 "><p id="p4972959911831"><a name="p4972959911831"></a><a name="p4972959911831"></a>用户项目ID。获取项目ID的操作指导请参见<a href="查看项目ID.md">查看项目ID</a>。</p>
</td>
</tr>
<tr id="row1267615214142"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p6636262275"><a name="p6636262275"></a><a name="p6636262275"></a>dataset_id</p>
</td>
<td class="cellrowborder" valign="top" width="16.18%" headers="mcps1.2.5.1.2 "><p id="p116372618278"><a name="p116372618278"></a><a name="p116372618278"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.299999999999999%" headers="mcps1.2.5.1.3 "><p id="p146319268278"><a name="p146319268278"></a><a name="p146319268278"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.519999999999996%" headers="mcps1.2.5.1.4 "><p id="p186362619277"><a name="p186362619277"></a><a name="p186362619277"></a>需要发布新版本的数据集ID。</p>
</td>
</tr>
<tr id="row966052131414"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p139149565311"><a name="p139149565311"></a><a name="p139149565311"></a>delete_files_spec</p>
</td>
<td class="cellrowborder" valign="top" width="16.18%" headers="mcps1.2.5.1.2 "><p id="p109145517533"><a name="p109145517533"></a><a name="p109145517533"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.299999999999999%" headers="mcps1.2.5.1.3 "><p id="p12914753531"><a name="p12914753531"></a><a name="p12914753531"></a>Dict</p>
</td>
<td class="cellrowborder" valign="top" width="44.519999999999996%" headers="mcps1.2.5.1.4 "><p id="p89141552539"><a name="p89141552539"></a><a name="p89141552539"></a>请求body。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  delete\_files\_spec参数说明

<a name="table35203141514"></a>
<table><thead align="left"><tr id="row16531131181517"><th class="cellrowborder" valign="top" width="24.07843137254902%" id="mcps1.2.5.1.1"><p id="p853631121510"><a name="p853631121510"></a><a name="p853631121510"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.098039215686274%" id="mcps1.2.5.1.2"><p id="p1253133131514"><a name="p1253133131514"></a><a name="p1253133131514"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.901960784313726%" id="mcps1.2.5.1.3"><p id="p3533314158"><a name="p3533314158"></a><a name="p3533314158"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.92156862745099%" id="mcps1.2.5.1.4"><p id="p35373171510"><a name="p35373171510"></a><a name="p35373171510"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row953431121517"><td class="cellrowborder" valign="top" width="24.07843137254902%" headers="mcps1.2.5.1.1 "><p id="p453123111154"><a name="p453123111154"></a><a name="p453123111154"></a>deleted_url</p>
</td>
<td class="cellrowborder" valign="top" width="17.098039215686274%" headers="mcps1.2.5.1.2 "><p id="p165313141515"><a name="p165313141515"></a><a name="p165313141515"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.901960784313726%" headers="mcps1.2.5.1.3 "><p id="p660220237174"><a name="p660220237174"></a><a name="p660220237174"></a>JSON Array</p>
</td>
<td class="cellrowborder" valign="top" width="42.92156862745099%" headers="mcps1.2.5.1.4 "><p id="p185383131510"><a name="p185383131510"></a><a name="p185383131510"></a>多个文件的URL组成的数组，[url1, url2, ...]。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  delete\_file\_from\_obs返回参数说明

<a name="table179502037135815"></a>
<table><thead align="left"><tr id="row11950173711581"><th class="cellrowborder" valign="top" width="24.22222222222222%" id="mcps1.2.4.1.1"><p id="p19950337115811"><a name="p19950337115811"></a><a name="p19950337115811"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.17171717171717%" id="mcps1.2.4.1.2"><p id="p1895033719584"><a name="p1895033719584"></a><a name="p1895033719584"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="58.60606060606061%" id="mcps1.2.4.1.3"><p id="p59501437125812"><a name="p59501437125812"></a><a name="p59501437125812"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row10950193755812"><td class="cellrowborder" valign="top" width="24.22222222222222%" headers="mcps1.2.4.1.1 "><p id="p13950113715816"><a name="p13950113715816"></a><a name="p13950113715816"></a>is_success</p>
</td>
<td class="cellrowborder" valign="top" width="17.17171717171717%" headers="mcps1.2.4.1.2 "><p id="p1095033716587"><a name="p1095033716587"></a><a name="p1095033716587"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="58.60606060606061%" headers="mcps1.2.4.1.3 "><p id="p2950183735818"><a name="p2950183735818"></a><a name="p2950183735818"></a>是否成功。</p>
</td>
</tr>
<tr id="row466982415915"><td class="cellrowborder" valign="top" width="24.22222222222222%" headers="mcps1.2.4.1.1 "><p id="p1566919246599"><a name="p1566919246599"></a><a name="p1566919246599"></a>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="17.17171717171717%" headers="mcps1.2.4.1.2 "><p id="p176691024155920"><a name="p176691024155920"></a><a name="p176691024155920"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="58.60606060606061%" headers="mcps1.2.4.1.3 "><p id="p071812541519"><a name="p071812541519"></a><a name="p071812541519"></a>调用失败时的错误码，具体请参见<a href="公共参数.md#section29446341644">错误码说明</a>。</p>
<p id="p6203060911624"><a name="p6203060911624"></a><a name="p6203060911624"></a>调用成功时无此字段。</p>
</td>
</tr>
<tr id="row20950337105814"><td class="cellrowborder" valign="top" width="24.22222222222222%" headers="mcps1.2.4.1.1 "><p id="p12966837205811"><a name="p12966837205811"></a><a name="p12966837205811"></a>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="17.17171717171717%" headers="mcps1.2.4.1.2 "><p id="p18966837115818"><a name="p18966837115818"></a><a name="p18966837115818"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="58.60606060606061%" headers="mcps1.2.4.1.3 "><p id="p7716529161210"><a name="p7716529161210"></a><a name="p7716529161210"></a>调用失败时的错误信息。</p>
<p id="p296619374586"><a name="p296619374586"></a><a name="p296619374586"></a>调用成功时无此字段。</p>
</td>
</tr>
</tbody>
</table>

