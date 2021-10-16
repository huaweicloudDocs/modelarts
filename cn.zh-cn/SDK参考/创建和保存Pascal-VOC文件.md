# 创建和保存Pascal VOC文件<a name="modelarts_04_0354"></a>

需要先创建包含Pascal VOC信息的对象，然后保存。Pascal VOC信息请见[表2](解析Pascal-VOC文件.md#zh-cn_topic_0170904391_table970151471612)。路径支持本地和OBS，如果是OBS，需要Session信息。

```
pascal_voc.save_xml(xml_file_path, save_mode='w', session=None)
```

## 示例代码<a name="section1130916814189"></a>

在保存Pascal VOC的XML文件之前需要先创建包含Pascal VOC信息的对象，包括voc object信息等。保存的时候调用save\_xml接口，将session信息传入，即可保存到指定路径。

```
from modelarts.dataset.format.voc.pascal_voc import PascalVoc
from modelarts.dataset.format.voc.voc_object import VocObject
from modelarts.session import Session

path = "obs://your-obs-bucket/voc/test2.xml"
size_list = [640, 321, 3]
file_name = "000000089955.jpg"
voc_object_tags = ["trafficlight", "trafficlight"]
voc_object_properties = [{"@modelarts:color": "#FFFFF0", "@modelarts:shortcut": "C",
                          "pose": "0", "truncated": "0", "difficult": "0",
                          "@modelarts:shape": "bndbox", "@modelarts:feature": [[347, 186], [382, 249]]},
                         {"@modelarts:color": "#FFFFE0", "@modelarts:shortcut": "D",
                          "pose": "0", "truncated": "0", "difficult": "0",
                          "@modelarts:shape": "bndbox", "@modelarts:feature": [[544, 50], [591, 149]]}]
voc_objects = []
for i in range(len(voc_object_tags)):
    object_tag = voc_object_tags[i]
    object_properties = voc_object_properties[i]
    voc_objects.append(VocObject(name=object_tag, properties=object_properties))

pascal_voc = PascalVoc(file_name=file_name, width=size_list[0], height=size_list[1], depth=size_list[2],
                       voc_objects=voc_objects)
session = Session()
pascal_voc.save_xml(path, session=session)

```

## 参数说明<a name="section6440103210204"></a>

**表 1**  请求参数

<a name="table5852141022412"></a>
<table><thead align="left"><tr id="row1385213107249"><th class="cellrowborder" valign="top" width="20.47%" id="mcps1.2.5.1.1"><p id="p5852161020240"><a name="p5852161020240"></a><a name="p5852161020240"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="8.77%" id="mcps1.2.5.1.2"><p id="p13852121020246"><a name="p13852121020246"></a><a name="p13852121020246"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="16.04%" id="mcps1.2.5.1.3"><p id="p885371052410"><a name="p885371052410"></a><a name="p885371052410"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="54.72%" id="mcps1.2.5.1.4"><p id="p885317103248"><a name="p885317103248"></a><a name="p885317103248"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1685321016244"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.2.5.1.1 "><p id="p11832822194818"><a name="p11832822194818"></a><a name="p11832822194818"></a>xml_file_path</p>
</td>
<td class="cellrowborder" valign="top" width="8.77%" headers="mcps1.2.5.1.2 "><p id="p184616124511"><a name="p184616124511"></a><a name="p184616124511"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.04%" headers="mcps1.2.5.1.3 "><p id="p385418296158"><a name="p385418296158"></a><a name="p385418296158"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.72%" headers="mcps1.2.5.1.4 "><p id="p5601639154814"><a name="p5601639154814"></a><a name="p5601639154814"></a>Pascal VOC格式的XML文件保存路径。</p>
</td>
</tr>
<tr id="row19852164442512"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.2.5.1.1 "><p id="p11852194432510"><a name="p11852194432510"></a><a name="p11852194432510"></a>session</p>
</td>
<td class="cellrowborder" valign="top" width="8.77%" headers="mcps1.2.5.1.2 "><p id="p785212449251"><a name="p785212449251"></a><a name="p785212449251"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.04%" headers="mcps1.2.5.1.3 "><p id="p1385214446255"><a name="p1385214446255"></a><a name="p1385214446255"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="54.72%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0160436006_p1689152543"><a name="zh-cn_topic_0160436006_p1689152543"></a><a name="zh-cn_topic_0160436006_p1689152543"></a>会话对象，初始化方法请参见<a href="Session鉴权概述.md">Session鉴权</a>。 当需要操作OBS时必填。</p>
</td>
</tr>
<tr id="row984681953615"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.2.5.1.1 "><p id="p1184714192367"><a name="p1184714192367"></a><a name="p1184714192367"></a>save_mode</p>
</td>
<td class="cellrowborder" valign="top" width="8.77%" headers="mcps1.2.5.1.2 "><p id="p18471319103615"><a name="p18471319103615"></a><a name="p18471319103615"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.04%" headers="mcps1.2.5.1.3 "><p id="p148471919163611"><a name="p148471919163611"></a><a name="p148471919163611"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.72%" headers="mcps1.2.5.1.4 "><p id="p1884741918361"><a name="p1884741918361"></a><a name="p1884741918361"></a>保存模式。默认为w，即重写模式，另外还支持a，为追加模式。</p>
</td>
</tr>
</tbody>
</table>

