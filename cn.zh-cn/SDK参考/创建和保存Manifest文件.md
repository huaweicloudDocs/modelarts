# 创建和保存Manifest文件<a name="modelarts_04_0352"></a>

需要先创建包含Manifest信息的对象，然后保存。Manifest信息请见[表2](解析Manifest文件.md#zh-cn_topic_0170904391_table970151471612)。路径支持本地和OBS，如果是OBS，需要Session信息。

```
manifest_info.save(path, session=None, save_mode="w")
```

## 示例代码<a name="section1130916814189"></a>

在保存Manifest文件之前需要先创建包含Manifest信息的对象，包括Sample样本信息及其标签信息Annotation，然后将诺干个样本组成Manifest。保存的时候调用save接口，将session信息传入，即可保存到指定路径。

```
from modelarts.dataset.format.manifest.annotation import Annotation
from modelarts.dataset.format.manifest import Manifest
from modelarts.dataset.format.manifest.sample import Sample
from modelarts.session import Session

size = 0
sample_list = []
for i in range(19):
    size = size + 1
    source = "s3://obs-path/examples/image-classification/data/image_" + str(i) + ".jpg"
    usage = "TRAIN"
    inference_loc = "s3://obs-path/examples/image-classification/data/image_" + str(i) + ".txt"
    annotations_list = []

    for j in range(1):
        annotation_type = "modelarts/image_classification"
        if 0 == i % 2:
            annotation_name = "Cat"
        else:
            annotation_name = "Dog"
        annotation_creation_time = "2019-02-20 08:23:06"
        annotation_format = "manifest"
        annotation_property = {"color": "black"}
        annotation_confidence = 0.8
        annotated_by = "human"
        annotations_list.append(
            Annotation(name=annotation_name, type=annotation_type,
                       confidence=annotation_confidence,
                       creation_time=annotation_creation_time,
                       annotated_by=annotated_by, annotation_format=annotation_format,
                       annotation_property=annotation_property))
    sample_list.append(
        Sample(source=source, usage=usage, annotations=annotations_list, inference_loc=inference_loc))
manifest_info = Manifest(samples=sample_list, size=size)

path = "obs://your-obs-bucket/manifest/V001.manifest"
session = Session()
manifest_info.save(path, session=session, save_mode="a")

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
<tbody><tr id="row1685321016244"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.2.5.1.1 "><p id="p11832822194818"><a name="p11832822194818"></a><a name="p11832822194818"></a>path</p>
</td>
<td class="cellrowborder" valign="top" width="8.77%" headers="mcps1.2.5.1.2 "><p id="p184616124511"><a name="p184616124511"></a><a name="p184616124511"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.04%" headers="mcps1.2.5.1.3 "><p id="p385418296158"><a name="p385418296158"></a><a name="p385418296158"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.72%" headers="mcps1.2.5.1.4 "><p id="p5601639154814"><a name="p5601639154814"></a><a name="p5601639154814"></a>manifest文件保存路径。</p>
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

