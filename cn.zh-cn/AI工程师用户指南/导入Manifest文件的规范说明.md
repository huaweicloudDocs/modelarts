# 导入Manifest文件的规范说明<a name="modelarts_23_0009"></a>

Manifest文件中定义了标注对象和标注内容的对应关系。此导入方式是指导入数据集时，使用Manifest文件。选择导入Manifest文件时，可以从本地文件系统导入或者从OBS导入。当从OBS导入Manifest文件时，需确保当前用户具备Manifest文件所在OBS路径的权限。

Manifest文件描述的是原始文件和标注信息，可用于标注、训练、推理场景。Manifest文件中也可以只有原始文件信息，没有标注信息，如用于推理场景，或用于生成未标注的数据集。Manifest文件需满足如下要求：

-   Manifest文件使用UTF-8编码。文本分类的source数值可以包含中文，其他字段不建议使用中文。
-   Manifest文件使用json lines格式（jsonlines.org），一行一个json对象。

    ```
    {"source": "/path/to/image1.jpg", "annotation": … }
    {"source": "/path/to/image2.jpg", "annotation": … }
    {"source": "/path/to/image3.jpg", "annotation": … }
    ```

    为了说明方面，下面的Manifest例子格式化为多行的json对象。

-   Manifest文件可以由用户、第三方工具或ModelArts数据标注生成，其文件名没有特殊要求，可以为任意合法文件名。为了ModelArts系统内部使用方便，ModelArts数据标注功能生成的文件名由如下字符串组成：“DatasetName-VersionName.manifest“。例如，“animal-v201901231130304123.manifest“。

## 图片分类<a name="section260132417144"></a>

```
{
"source":
"s3://path/to/image1.jpg", 
"usage":
"TRAIN",
"id":"0162005993f8065ef47eefb59d1e4970",
    "annotation": [
        {
            "type": "modelarts/image_classification",
            "name": "cat",
            "property": {
                        "color":"white",
                        "kind":"Persian cat"
            },
            "hard":"true",
            "hard-coefficient":0.8,
            "annotated-by":"human",
            "creation-time":"2019-01-23 11:30:30"
        },
        {
            "type": "modelarts/image_classification",
            "name":"animal",
            "annotated-by":"modelarts/active-learning",
            "confidence": 0.8,
            "creation-time":"2019-01-23 11:30:30"
        }
],
"inference-loc":"/path/to/inference-output"
}
```

**表 1**  字段说明

<a name="table598984218223"></a>
<table><thead align="left"><tr id="row8990542102214"><th class="cellrowborder" valign="top" width="20.669999999999998%" id="mcps1.2.4.1.1"><p id="p199901342142215"><a name="p199901342142215"></a><a name="p199901342142215"></a>字段</p>
</th>
<th class="cellrowborder" valign="top" width="12.389999999999999%" id="mcps1.2.4.1.2"><p id="p4522982412"><a name="p4522982412"></a><a name="p4522982412"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="66.94%" id="mcps1.2.4.1.3"><p id="p799014426226"><a name="p799014426226"></a><a name="p799014426226"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row17990194217227"><td class="cellrowborder" valign="top" width="20.669999999999998%" headers="mcps1.2.4.1.1 "><p id="p1199018428221"><a name="p1199018428221"></a><a name="p1199018428221"></a>source</p>
</td>
<td class="cellrowborder" valign="top" width="12.389999999999999%" headers="mcps1.2.4.1.2 "><p id="p1951629182412"><a name="p1951629182412"></a><a name="p1951629182412"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="66.94%" headers="mcps1.2.4.1.3 "><p id="p199906424227"><a name="p199906424227"></a><a name="p199906424227"></a>被标注对象的URI。数据来源的类型及示例请参考<a href="#table9303122642318">表2</a>。</p>
</td>
</tr>
<tr id="row499019426228"><td class="cellrowborder" valign="top" width="20.669999999999998%" headers="mcps1.2.4.1.1 "><p id="p1999064282214"><a name="p1999064282214"></a><a name="p1999064282214"></a>usage</p>
</td>
<td class="cellrowborder" valign="top" width="12.389999999999999%" headers="mcps1.2.4.1.2 "><p id="p16532913240"><a name="p16532913240"></a><a name="p16532913240"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="66.94%" headers="mcps1.2.4.1.3 "><p id="p1892121372516"><a name="p1892121372516"></a><a name="p1892121372516"></a>默认为空，取值范围：</p>
<a name="ul2030152722610"></a><a name="ul2030152722610"></a><ul id="ul2030152722610"><li>TRAIN：指明该对象用于训练。</li><li>EVAL：指明该对象用于评估。</li><li>TEST：指明该对象用于测试。</li><li>INFERENCE：指明该对象用于推理。</li></ul>
<p id="p326411492619"><a name="p326411492619"></a><a name="p326411492619"></a>如果没有给出该字段，则使用者自行决定如何使用该对象。</p>
</td>
</tr>
<tr id="row19990184213229"><td class="cellrowborder" valign="top" width="20.669999999999998%" headers="mcps1.2.4.1.1 "><p id="p17990124215223"><a name="p17990124215223"></a><a name="p17990124215223"></a>annotation</p>
</td>
<td class="cellrowborder" valign="top" width="12.389999999999999%" headers="mcps1.2.4.1.2 "><p id="p145929132410"><a name="p145929132410"></a><a name="p145929132410"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="66.94%" headers="mcps1.2.4.1.3 "><p id="p146559504260"><a name="p146559504260"></a><a name="p146559504260"></a>如果不设置，则表示未标注对象。annotation值为一个对象列表，详细参数请参见<a href="#table48141825192716">表3</a>。</p>
</td>
</tr>
<tr id="row13990194212227"><td class="cellrowborder" valign="top" width="20.669999999999998%" headers="mcps1.2.4.1.1 "><p id="p15990194222210"><a name="p15990194222210"></a><a name="p15990194222210"></a>inference-loc</p>
</td>
<td class="cellrowborder" valign="top" width="12.389999999999999%" headers="mcps1.2.4.1.2 "><p id="p136162952419"><a name="p136162952419"></a><a name="p136162952419"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="66.94%" headers="mcps1.2.4.1.3 "><p id="p399054216229"><a name="p399054216229"></a><a name="p399054216229"></a>当此文件由推理服务生成时会有该字段，表示推理输出的结果文件位置。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  数据来源类型

<a name="table9303122642318"></a>
<table><thead align="left"><tr id="row1342326142319"><th class="cellrowborder" valign="top" width="35.36%" id="mcps1.2.3.1.1"><p id="p13421526182311"><a name="p13421526182311"></a><a name="p13421526182311"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="64.64%" id="mcps1.2.3.1.2"><p id="p134252616235"><a name="p134252616235"></a><a name="p134252616235"></a>示例</p>
</th>
</tr>
</thead>
<tbody><tr id="row193428267235"><td class="cellrowborder" valign="top" width="35.36%" headers="mcps1.2.3.1.1 "><p id="p153425266233"><a name="p153425266233"></a><a name="p153425266233"></a>OBS</p>
</td>
<td class="cellrowborder" valign="top" width="64.64%" headers="mcps1.2.3.1.2 "><p id="p1034212611233"><a name="p1034212611233"></a><a name="p1034212611233"></a>“source”:“s3://path-to-jpg”</p>
</td>
</tr>
<tr id="row20342162622318"><td class="cellrowborder" valign="top" width="35.36%" headers="mcps1.2.3.1.1 "><p id="p13421262238"><a name="p13421262238"></a><a name="p13421262238"></a>Content</p>
</td>
<td class="cellrowborder" valign="top" width="64.64%" headers="mcps1.2.3.1.2 "><p id="p183433260237"><a name="p183433260237"></a><a name="p183433260237"></a>“source”:“content://I love machine learning”</p>
</td>
</tr>
</tbody>
</table>

**表 3**  annotation对象说明

<a name="table48141825192716"></a>
<table><thead align="left"><tr id="row1981482542717"><th class="cellrowborder" valign="top" width="20.5%" id="mcps1.2.4.1.1"><p id="p1981582562715"><a name="p1981582562715"></a><a name="p1981582562715"></a>字段</p>
</th>
<th class="cellrowborder" valign="top" width="13.73%" id="mcps1.2.4.1.2"><p id="p948925314270"><a name="p948925314270"></a><a name="p948925314270"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="65.77%" id="mcps1.2.4.1.3"><p id="p28151325182714"><a name="p28151325182714"></a><a name="p28151325182714"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row138159258276"><td class="cellrowborder" valign="top" width="20.5%" headers="mcps1.2.4.1.1 "><p id="p1881572512270"><a name="p1881572512270"></a><a name="p1881572512270"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="13.73%" headers="mcps1.2.4.1.2 "><p id="p17489155313277"><a name="p17489155313277"></a><a name="p17489155313277"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="65.77%" headers="mcps1.2.4.1.3 "><p id="p15815162519271"><a name="p15815162519271"></a><a name="p15815162519271"></a>标签类型。取值范围为：</p>
<a name="ul1563483682816"></a><a name="ul1563483682816"></a><ul id="ul1563483682816"><li>image_classification：图像分类</li><li>text_classification：文本分类</li><li>text_entity：文本命名实体</li><li>object_detection：对象检测</li><li>audio_classification：声音分类</li><li>audio_content：声音内容</li><li>audio_segmentation：声音起止点</li></ul>
</td>
</tr>
<tr id="row3815182513278"><td class="cellrowborder" valign="top" width="20.5%" headers="mcps1.2.4.1.1 "><p id="p1581552592713"><a name="p1581552592713"></a><a name="p1581552592713"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="13.73%" headers="mcps1.2.4.1.2 "><p id="p448920536274"><a name="p448920536274"></a><a name="p448920536274"></a>是/否</p>
</td>
<td class="cellrowborder" valign="top" width="65.77%" headers="mcps1.2.4.1.3 "><p id="p18151725132712"><a name="p18151725132712"></a><a name="p18151725132712"></a>对于分类是必选字段，对于其他类型为可选字段，本示例为图片分类名称。</p>
</td>
</tr>
<tr id="row138151425132716"><td class="cellrowborder" valign="top" width="20.5%" headers="mcps1.2.4.1.1 "><p id="p1981532515275"><a name="p1981532515275"></a><a name="p1981532515275"></a>property</p>
</td>
<td class="cellrowborder" valign="top" width="13.73%" headers="mcps1.2.4.1.2 "><p id="p17489153192714"><a name="p17489153192714"></a><a name="p17489153192714"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="65.77%" headers="mcps1.2.4.1.3 "><p id="p186261048192918"><a name="p186261048192918"></a><a name="p186261048192918"></a>包含对标注的属性，例如本示例中猫有两个属性，颜色（color）和品种（kind）。</p>
</td>
</tr>
<tr id="row1881515255277"><td class="cellrowborder" valign="top" width="20.5%" headers="mcps1.2.4.1.1 "><p id="p48153254274"><a name="p48153254274"></a><a name="p48153254274"></a>hard</p>
</td>
<td class="cellrowborder" valign="top" width="13.73%" headers="mcps1.2.4.1.2 "><p id="p1448915319279"><a name="p1448915319279"></a><a name="p1448915319279"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="65.77%" headers="mcps1.2.4.1.3 "><p id="p16815122510274"><a name="p16815122510274"></a><a name="p16815122510274"></a>表示是否是难例。<span class="parmvalue" id="parmvalue10830142020302"><a name="parmvalue10830142020302"></a><a name="parmvalue10830142020302"></a>“True”</span>表示该标注是难例，<span class="parmvalue" id="parmvalue5566122310309"><a name="parmvalue5566122310309"></a><a name="parmvalue5566122310309"></a>“False”</span>表示该标注不是难例。</p>
</td>
</tr>
<tr id="row1381512253274"><td class="cellrowborder" valign="top" width="20.5%" headers="mcps1.2.4.1.1 "><p id="p881572512715"><a name="p881572512715"></a><a name="p881572512715"></a>annotated-by</p>
</td>
<td class="cellrowborder" valign="top" width="13.73%" headers="mcps1.2.4.1.2 "><p id="p64891653102712"><a name="p64891653102712"></a><a name="p64891653102712"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="65.77%" headers="mcps1.2.4.1.3 "><p id="p293361613213"><a name="p293361613213"></a><a name="p293361613213"></a>默认为<span class="parmvalue" id="parmvalue17933416133212"><a name="parmvalue17933416133212"></a><a name="parmvalue17933416133212"></a>“human”</span>，表示人工标注。</p>
<a name="ul20531920193215"></a><a name="ul20531920193215"></a>
</td>
</tr>
<tr id="row1581692512715"><td class="cellrowborder" valign="top" width="20.5%" headers="mcps1.2.4.1.1 "><p id="p681611253279"><a name="p681611253279"></a><a name="p681611253279"></a>creation-time</p>
</td>
<td class="cellrowborder" valign="top" width="13.73%" headers="mcps1.2.4.1.2 "><p id="p124891753202711"><a name="p124891753202711"></a><a name="p124891753202711"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="65.77%" headers="mcps1.2.4.1.3 "><p id="p48169253271"><a name="p48169253271"></a><a name="p48169253271"></a>创建该标注的时间。是用户写入标注的时间，不是Manifest生成时间。</p>
</td>
</tr>
<tr id="row4816825122716"><td class="cellrowborder" valign="top" width="20.5%" headers="mcps1.2.4.1.1 "><p id="p1081602572716"><a name="p1081602572716"></a><a name="p1081602572716"></a>confidence</p>
</td>
<td class="cellrowborder" valign="top" width="13.73%" headers="mcps1.2.4.1.2 "><p id="p1048955382710"><a name="p1048955382710"></a><a name="p1048955382710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="65.77%" headers="mcps1.2.4.1.3 "><p id="p5816102511278"><a name="p5816102511278"></a><a name="p5816102511278"></a>表示机器标注的置信度。范围为0～1。</p>
</td>
</tr>
</tbody>
</table>

## 文本分类<a name="section8593163192118"></a>

```
{
"source": "content://I like this product ", 
"id":"XGDVGS",
    "annotation": [
        {
            "type": "modelarts/text_classification",
            "name": " positive",
            "annotated-by": "human",
            "creation-time": "2019-01-23 11:30:30"
        } 
]
}
{
"source ": "content://I do not want to use it", 
    "annotation": [
        {
            "type": "modelarts/ text_classification",
            "name": " negative",
            "annotated-by": "human",
            "creation-time": "2019-01-23 11:30:30"
        } 
]
}
```

content字段是指被标注的文本（UTF-8编码，可以是中文），其他参数解释与[图片分类](#section260132417144)相同，请参见[表1](#table598984218223)。

## 文本命名实体<a name="section335761812211"></a>

```
{
    "source":"content://Michael Jordan is the most famous basketball player in the world.",
    "usage":"TRAIN",
    "annotation":[
        {
            "type":"modelarts/text_entity",
            "name":"Person",
            "property":{
                "@modelarts:start_index":0,
                "@modelarts:end_index":14
            },
            "annotated-by":"human",
            "creation-time":"2019-01-23 11:30:30"
        },
        {
            "type":"modelarts/text_entity",
            "name":"Category",
            "property":{
                "@modelarts:start_index":34,
                "@modelarts:end_index":44
            },
            "annotated-by":"human",
            "creation-time":"2019-01-23 11:30:30"
        }
    ]
}
```

“source“、“usage“、“annotation“等参数说明与[图片分类](#section260132417144)一致，详细说明请参见[表1](#table598984218223)。

其中，property的参数解释如[表4](#table8486339124912)所示。例如，当“"source":"content://Michael Jordan"“时，如果要提取“Michael“，则对应的“start\_index“为“0“，“end\_index“为“7“。

**表 4**  property参数说明

<a name="table8486339124912"></a>
<table><thead align="left"><tr id="row1487103944917"><th class="cellrowborder" valign="top" width="27.400000000000002%" id="mcps1.2.4.1.1"><p id="p10794105417495"><a name="p10794105417495"></a><a name="p10794105417495"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="17.14%" id="mcps1.2.4.1.2"><p id="p16794195464913"><a name="p16794195464913"></a><a name="p16794195464913"></a>数据类型</p>
</th>
<th class="cellrowborder" valign="top" width="55.46%" id="mcps1.2.4.1.3"><p id="p167947549495"><a name="p167947549495"></a><a name="p167947549495"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row174872039174914"><td class="cellrowborder" valign="top" width="27.400000000000002%" headers="mcps1.2.4.1.1 "><p id="p1794175434910"><a name="p1794175434910"></a><a name="p1794175434910"></a>@modelarts:start_index</p>
</td>
<td class="cellrowborder" valign="top" width="17.14%" headers="mcps1.2.4.1.2 "><p id="p5794155419493"><a name="p5794155419493"></a><a name="p5794155419493"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="55.46%" headers="mcps1.2.4.1.3 "><p id="p1979485419492"><a name="p1979485419492"></a><a name="p1979485419492"></a>文本的起始位置，值从0开始，包括start_index所指的字符。</p>
</td>
</tr>
<tr id="row54877393497"><td class="cellrowborder" valign="top" width="27.400000000000002%" headers="mcps1.2.4.1.1 "><p id="p27951154194919"><a name="p27951154194919"></a><a name="p27951154194919"></a>@modelarts:end_index</p>
</td>
<td class="cellrowborder" valign="top" width="17.14%" headers="mcps1.2.4.1.2 "><p id="p2795654174915"><a name="p2795654174915"></a><a name="p2795654174915"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="55.46%" headers="mcps1.2.4.1.3 "><p id="p8795185411497"><a name="p8795185411497"></a><a name="p8795185411497"></a>文本的结束位置，但不包括end_index所指的字符。</p>
</td>
</tr>
</tbody>
</table>

## 物体检测<a name="section1571582442114"></a>

```
{
"source":
"s3://path/to/image1.jpg", 
"usage":
"TRAIN",
    "annotation": [
        {
            "type":"modelarts/object_detection",
            "annotation-loc": "s3://path/to/annotation1.xml",
            "annotation-format":"PASCAL VOC",
            "annotated-by":"human",
            "creation-time":"2019-01-23 11:30:30"        
        }
]
}
```

-   “source“、“usage“、“annotation“等参数说明与[图片分类](#section260132417144)一致，详细说明请参见[表1](#table598984218223)。
-   “annotation-loc“：对于物体检测是必选字段，对于其他类型是可选字段，标注文件的存储路径。
-   “annotation-format“: 描述标注文件的格式，可选字段，默认为“PASCAL VOC“。目前只支持“PASCAL VOC“。

**表 5**  PASCAL VOC格式说明

<a name="table77167388472"></a>
<table><thead align="left"><tr id="row7716163814718"><th class="cellrowborder" valign="top" width="20.64793520647935%" id="mcps1.2.4.1.1"><p id="p19717173814479"><a name="p19717173814479"></a><a name="p19717173814479"></a>字段</p>
</th>
<th class="cellrowborder" valign="top" width="11.228877112288771%" id="mcps1.2.4.1.2"><p id="p539965784710"><a name="p539965784710"></a><a name="p539965784710"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="68.12318768123188%" id="mcps1.2.4.1.3"><p id="p1171718387470"><a name="p1171718387470"></a><a name="p1171718387470"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row17171038174719"><td class="cellrowborder" valign="top" width="20.64793520647935%" headers="mcps1.2.4.1.1 "><p id="p17717938184712"><a name="p17717938184712"></a><a name="p17717938184712"></a>folder</p>
</td>
<td class="cellrowborder" valign="top" width="11.228877112288771%" headers="mcps1.2.4.1.2 "><p id="p1840010576473"><a name="p1840010576473"></a><a name="p1840010576473"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="68.12318768123188%" headers="mcps1.2.4.1.3 "><p id="p1971710382475"><a name="p1971710382475"></a><a name="p1971710382475"></a>表示数据源所在目录。</p>
</td>
</tr>
<tr id="row6717193816479"><td class="cellrowborder" valign="top" width="20.64793520647935%" headers="mcps1.2.4.1.1 "><p id="p16717123874713"><a name="p16717123874713"></a><a name="p16717123874713"></a>filename</p>
</td>
<td class="cellrowborder" valign="top" width="11.228877112288771%" headers="mcps1.2.4.1.2 "><p id="p15400185784715"><a name="p15400185784715"></a><a name="p15400185784715"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="68.12318768123188%" headers="mcps1.2.4.1.3 "><p id="p19717123844715"><a name="p19717123844715"></a><a name="p19717123844715"></a>被标注文件的文件名。</p>
</td>
</tr>
<tr id="row1771715381471"><td class="cellrowborder" valign="top" width="20.64793520647935%" headers="mcps1.2.4.1.1 "><p id="p1471717386478"><a name="p1471717386478"></a><a name="p1471717386478"></a>size</p>
</td>
<td class="cellrowborder" valign="top" width="11.228877112288771%" headers="mcps1.2.4.1.2 "><p id="p17400155715476"><a name="p17400155715476"></a><a name="p17400155715476"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="68.12318768123188%" headers="mcps1.2.4.1.3 "><p id="p1060417161494"><a name="p1060417161494"></a><a name="p1060417161494"></a>表示图像的像素信息。</p>
<a name="ul4553182420494"></a><a name="ul4553182420494"></a><ul id="ul4553182420494"><li>width：必选字段，图片的宽度。</li><li>height：必选字段，图片的高度。</li><li>depth：必选字段，图片的通道数。</li></ul>
</td>
</tr>
<tr id="row2071720384474"><td class="cellrowborder" valign="top" width="20.64793520647935%" headers="mcps1.2.4.1.1 "><p id="p1471793854717"><a name="p1471793854717"></a><a name="p1471793854717"></a>segmented</p>
</td>
<td class="cellrowborder" valign="top" width="11.228877112288771%" headers="mcps1.2.4.1.2 "><p id="p1340055713477"><a name="p1340055713477"></a><a name="p1340055713477"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="68.12318768123188%" headers="mcps1.2.4.1.3 "><p id="p1871713386473"><a name="p1871713386473"></a><a name="p1871713386473"></a>表示是否用于分割。</p>
</td>
</tr>
<tr id="row772234211471"><td class="cellrowborder" valign="top" width="20.64793520647935%" headers="mcps1.2.4.1.1 "><p id="p18723134212474"><a name="p18723134212474"></a><a name="p18723134212474"></a>object</p>
</td>
<td class="cellrowborder" valign="top" width="11.228877112288771%" headers="mcps1.2.4.1.2 "><p id="p114001557104712"><a name="p114001557104712"></a><a name="p114001557104712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="68.12318768123188%" headers="mcps1.2.4.1.3 "><p id="p1272364284719"><a name="p1272364284719"></a><a name="p1272364284719"></a>表示物体检测信息，多个物体标注会有多个object体。</p>
<a name="ul486718312505"></a><a name="ul486718312505"></a><ul id="ul486718312505"><li>name：必选字段，标注内容的类别。</li><li>pose：必选字段，标注内容的拍摄角度。</li><li>truncated：必选字段，标注内容是否被截断（0表示完整）。</li><li>occluded：必选字段，标注内容是否被遮挡（0表示未遮挡）</li><li>difficult：必选字段，标注目标是否难以识别（0表示容易识别）。</li><li>confidence：可选字段，标注目标的置信度，取值范围0-1之间。</li><li>bndbox：必选字段，标注框的类型，可选值请参见<a href="#table1770752310500">表6</a>。</li></ul>
</td>
</tr>
</tbody>
</table>

**表 6**  标注框类型描述

<a name="table1770752310500"></a>
<table><thead align="left"><tr id="row1481202365017"><th class="cellrowborder" valign="top" width="23.077692230776922%" id="mcps1.2.4.1.1"><p id="p138121023145019"><a name="p138121023145019"></a><a name="p138121023145019"></a>type</p>
</th>
<th class="cellrowborder" valign="top" width="23.557644235576443%" id="mcps1.2.4.1.2"><p id="p6812122316505"><a name="p6812122316505"></a><a name="p6812122316505"></a>形状</p>
</th>
<th class="cellrowborder" valign="top" width="53.36466353364663%" id="mcps1.2.4.1.3"><p id="p7812152385012"><a name="p7812152385012"></a><a name="p7812152385012"></a>标注信息</p>
</th>
</tr>
</thead>
<tbody><tr id="row28121230504"><td class="cellrowborder" valign="top" width="23.077692230776922%" headers="mcps1.2.4.1.1 "><p id="p138122023165012"><a name="p138122023165012"></a><a name="p138122023165012"></a>point</p>
</td>
<td class="cellrowborder" valign="top" width="23.557644235576443%" headers="mcps1.2.4.1.2 "><p id="p1381202317502"><a name="p1381202317502"></a><a name="p1381202317502"></a>点</p>
</td>
<td class="cellrowborder" valign="top" width="53.36466353364663%" headers="mcps1.2.4.1.3 "><p id="p98139233509"><a name="p98139233509"></a><a name="p98139233509"></a>点的坐标。</p>
<p id="p6813162315011"><a name="p6813162315011"></a><a name="p6813162315011"></a>&lt;x&gt;100&lt;x&gt;</p>
<p id="p2081317236509"><a name="p2081317236509"></a><a name="p2081317236509"></a>&lt;y&gt;100&lt;y&gt;</p>
</td>
</tr>
<tr id="row3813823145019"><td class="cellrowborder" valign="top" width="23.077692230776922%" headers="mcps1.2.4.1.1 "><p id="p1381322312507"><a name="p1381322312507"></a><a name="p1381322312507"></a>line</p>
</td>
<td class="cellrowborder" valign="top" width="23.557644235576443%" headers="mcps1.2.4.1.2 "><p id="p781352319501"><a name="p781352319501"></a><a name="p781352319501"></a>线</p>
</td>
<td class="cellrowborder" valign="top" width="53.36466353364663%" headers="mcps1.2.4.1.3 "><p id="p781312320507"><a name="p781312320507"></a><a name="p781312320507"></a>各点坐标。</p>
<p id="p8813623165016"><a name="p8813623165016"></a><a name="p8813623165016"></a>&lt;x1&gt;100&lt;x1&gt;</p>
<p id="p18131223165017"><a name="p18131223165017"></a><a name="p18131223165017"></a>&lt;y1&gt;100&lt;y1&gt;</p>
<p id="p281312232502"><a name="p281312232502"></a><a name="p281312232502"></a>&lt;x2&gt;200&lt;x2&gt;</p>
<p id="p12813323105015"><a name="p12813323105015"></a><a name="p12813323105015"></a>&lt;y2&gt;200&lt;y2&gt;</p>
</td>
</tr>
<tr id="row481312312503"><td class="cellrowborder" valign="top" width="23.077692230776922%" headers="mcps1.2.4.1.1 "><p id="p381352355016"><a name="p381352355016"></a><a name="p381352355016"></a>bndbox</p>
</td>
<td class="cellrowborder" valign="top" width="23.557644235576443%" headers="mcps1.2.4.1.2 "><p id="p19813723175017"><a name="p19813723175017"></a><a name="p19813723175017"></a>矩形框</p>
</td>
<td class="cellrowborder" valign="top" width="53.36466353364663%" headers="mcps1.2.4.1.3 "><p id="p1981315231506"><a name="p1981315231506"></a><a name="p1981315231506"></a>左上和右下两个点坐标。</p>
<p id="p1381316234504"><a name="p1381316234504"></a><a name="p1381316234504"></a>&lt;xmin&gt;100&lt;xmin&gt;</p>
<p id="p3813132315509"><a name="p3813132315509"></a><a name="p3813132315509"></a>&lt;ymin&gt;100&lt;ymin&gt;</p>
<p id="p8813623125018"><a name="p8813623125018"></a><a name="p8813623125018"></a>&lt;xmax&gt;200&lt;xmax&gt;</p>
<p id="p15813923125018"><a name="p15813923125018"></a><a name="p15813923125018"></a>&lt;ymax&gt;200&lt;ymax&gt;</p>
</td>
</tr>
<tr id="row15813192316505"><td class="cellrowborder" valign="top" width="23.077692230776922%" headers="mcps1.2.4.1.1 "><p id="p178131235507"><a name="p178131235507"></a><a name="p178131235507"></a>polygon</p>
</td>
<td class="cellrowborder" valign="top" width="23.557644235576443%" headers="mcps1.2.4.1.2 "><p id="p78130238502"><a name="p78130238502"></a><a name="p78130238502"></a>多边形</p>
</td>
<td class="cellrowborder" valign="top" width="53.36466353364663%" headers="mcps1.2.4.1.3 "><p id="p1281410235509"><a name="p1281410235509"></a><a name="p1281410235509"></a>各点坐标。</p>
<p id="p1781422385011"><a name="p1781422385011"></a><a name="p1781422385011"></a>&lt;x1&gt;100&lt;x1&gt;</p>
<p id="p681482314501"><a name="p681482314501"></a><a name="p681482314501"></a>&lt;y1&gt;100&lt;y1&gt;</p>
<p id="p581422314509"><a name="p581422314509"></a><a name="p581422314509"></a>&lt;x2&gt;200&lt;x2&gt;</p>
<p id="p17814182385013"><a name="p17814182385013"></a><a name="p17814182385013"></a>&lt;y2&gt;100&lt;y2&gt;</p>
<p id="p108144232502"><a name="p108144232502"></a><a name="p108144232502"></a>&lt;x3&gt;250&lt;x3&gt;</p>
<p id="p16814132311509"><a name="p16814132311509"></a><a name="p16814132311509"></a>&lt;y3&gt;150&lt;y3&gt;</p>
<p id="p12814723155016"><a name="p12814723155016"></a><a name="p12814723155016"></a>&lt;x4&gt;200&lt;x4&gt;</p>
<p id="p1881462315014"><a name="p1881462315014"></a><a name="p1881462315014"></a>&lt;y4&gt;200&lt;y4&gt;</p>
<p id="p4814623155015"><a name="p4814623155015"></a><a name="p4814623155015"></a>&lt;x5&gt;100&lt;x5&gt;</p>
<p id="p1481422325015"><a name="p1481422325015"></a><a name="p1481422325015"></a>&lt;y5&gt;200&lt;y5&gt;</p>
<p id="p188141023115011"><a name="p188141023115011"></a><a name="p188141023115011"></a>&lt;x6&gt;50&lt;x6&gt;</p>
<p id="p7814112319504"><a name="p7814112319504"></a><a name="p7814112319504"></a>&lt;y6&gt;150&lt;y6&gt;</p>
</td>
</tr>
<tr id="row981420231502"><td class="cellrowborder" valign="top" width="23.077692230776922%" headers="mcps1.2.4.1.1 "><p id="p128141223145015"><a name="p128141223145015"></a><a name="p128141223145015"></a>circle</p>
</td>
<td class="cellrowborder" valign="top" width="23.557644235576443%" headers="mcps1.2.4.1.2 "><p id="p7814423145019"><a name="p7814423145019"></a><a name="p7814423145019"></a>圆形</p>
</td>
<td class="cellrowborder" valign="top" width="53.36466353364663%" headers="mcps1.2.4.1.3 "><p id="p3814823165018"><a name="p3814823165018"></a><a name="p3814823165018"></a>圆心坐标和半径。</p>
<p id="p1881413233508"><a name="p1881413233508"></a><a name="p1881413233508"></a>&lt;cx&gt;100&lt;cx&gt;</p>
<p id="p5814132310504"><a name="p5814132310504"></a><a name="p5814132310504"></a>&lt;cy&gt;100&lt;cy&gt;</p>
<p id="p6814223175013"><a name="p6814223175013"></a><a name="p6814223175013"></a>&lt;r&gt;50&lt;r&gt;</p>
</td>
</tr>
</tbody>
</table>

示例：

```
<annotation>
   <folder>test_data</folder>
   <filename>260730932.jpg</filename>
   <size>
       <width>767</width>
       <height>959</height>
       <depth>3</depth>
   </size>
   <segmented>0</segmented>
   <object>
       <name>point</name>
       <pose>Unspecified</pose>
       <truncated>0</truncated>
       <occluded>0</occluded>
       <difficult>0</difficult>
       <point>
           <x1>456</x1>
           <y1>596</y1>
       </point>
   </object>
   <object>
       <name>line</name>
       <pose>Unspecified</pose>
       <truncated>0</truncated>
       <occluded>0</occluded>
       <difficult>0</difficult>
       <line>
           <x1>133</x1>
           <y1>651</y1>
           <x2>229</x2>
           <y2>561</y2>
       </line>
   </object>
   <object>
       <name>bag</name>
       <pose>Unspecified</pose>
       <truncated>0</truncated>
       <occluded>0</occluded>
       <difficult>0</difficult>
       <bndbox>
           <xmin>108</xmin>
           <ymin>101</ymin>
           <xmax>251</xmax>
           <ymax>238</ymax>
       </bndbox>
   </object>
   <object>
       <name>boots</name>
       <pose>Unspecified</pose>
       <truncated>0</truncated>
       <occluded>0</occluded>
       <difficult>0</difficult>
       <polygon>
           <x1>373</x1>
           <y1>264</y1>
           <x2>500</x2>
           <y2>198</y2>
           <x3>437</x3>
           <y3>76</y3>
           <x4>310</x4>
           <y4>142</y4>
       </polygon>
   </object>
   <object>
       <name>circle</name>
       <pose>Unspecified</pose>
       <truncated>0</truncated>
       <occluded>0</occluded>
       <difficult>0</difficult>
       <circle>
           <cx>405</cx>
           <cy>170</cy>
           <r>100<r>
       </circle>
   </object>
</annotation>
```

## 声音分类<a name="section2373122922115"></a>

```
{
"source":
"s3://path/to/pets.wav", 
    "annotation": [
        {
            "type": "modelarts/audio_classification",
            "name":"cat",    
            "annotated-by":"human",
            "creation-time":"2019-01-23 11:30:30"
        } 
    ]
}
```

“source“、“usage“、“annotation“等参数说明与[图片分类](#section260132417144)一致，详细说明请参见[表1](#table598984218223)。

## 语音内容<a name="section10586153472113"></a>

```
{
    "source":"s3://path/to/audio1.wav",
    "annotation":[
        {
            "type":"modelarts/audio_content",
            "property":{
                "@modelarts:content":"Today is a good day."
            },
            "annotated-by":"human",
            "creation-time":"2019-01-23 11:30:30"
        }
    ]
}
```

-   “source“、“usage“、“annotation“等参数说明与[图片分类](#section260132417144)一致，详细说明请参见[表1](#table598984218223)。
-   “property“中的“@modelarts:content“参数，数据类型为“String“，表示语音内容。

## 语音分割<a name="section1260563812219"></a>

```
{
    "source":"s3://path/to/audio1.wav",
    "usage":"TRAIN",
    "annotation":[
        {
           
"type":"modelarts/audio_segmentation",
            "property":{
                "@modelarts:start_time":"00:01:10.123",
                "@modelarts:end_time":"00:01:15.456",
               
                "@modelarts:source":"Tom",
               
                "@modelarts:content":"How are you?"
            },
           "annotated-by":"human",
           "creation-time":"2019-01-23 11:30:30"
        },
        {
           "type":"modelarts/audio_segmentation",
            "property":{
                "@modelarts:start_time":"00:01:22.754",
                "@modelarts:end_time":"00:01:24.145",
                "@modelarts:source":"Jerry",
                "@modelarts:content":"I'm fine, thank you."
            },
           "annotated-by":"human",
           "creation-time":"2019-01-23 11:30:30"
        }
    ]
}
```

-   “source“、“usage“、“annotation“等参数说明与[图片分类](#section260132417144)一致，详细说明请参见[表1](#table598984218223)。
-   “property“的参数解释如[表7](#table1151144815513)所示。

    **表 7** “property“参数说明

    <a name="table1151144815513"></a>
    <table><thead align="left"><tr id="row358094865519"><th class="cellrowborder" valign="top" width="26.21%" id="mcps1.2.4.1.1"><p id="p14580048115514"><a name="p14580048115514"></a><a name="p14580048115514"></a>参数名</p>
    </th>
    <th class="cellrowborder" valign="top" width="16.57%" id="mcps1.2.4.1.2"><p id="p45811548105513"><a name="p45811548105513"></a><a name="p45811548105513"></a>数据类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="57.220000000000006%" id="mcps1.2.4.1.3"><p id="p185811748205511"><a name="p185811748205511"></a><a name="p185811748205511"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row15811348145514"><td class="cellrowborder" valign="top" width="26.21%" headers="mcps1.2.4.1.1 "><p id="p10581184815557"><a name="p10581184815557"></a><a name="p10581184815557"></a>@modelarts:start_time</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.57%" headers="mcps1.2.4.1.2 "><p id="p5581114816550"><a name="p5581114816550"></a><a name="p5581114816550"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.220000000000006%" headers="mcps1.2.4.1.3 "><p id="p3568516135610"><a name="p3568516135610"></a><a name="p3568516135610"></a>声音的起始时间，格式为<span class="parmname" id="parmname20568616125612"><a name="parmname20568616125612"></a><a name="parmname20568616125612"></a>“hh:mm:ss.SSS”</span>。</p>
    <p id="p20581114816555"><a name="p20581114816555"></a><a name="p20581114816555"></a>其中<span class="parmname" id="parmname193033155615"><a name="parmname193033155615"></a><a name="parmname193033155615"></a>“hh”</span>表示小时，<span class="parmname" id="parmname3776113205612"><a name="parmname3776113205612"></a><a name="parmname3776113205612"></a>“mm”</span>表示分钟，<span class="parmname" id="parmname49446348569"><a name="parmname49446348569"></a><a name="parmname49446348569"></a>“ss”</span>表示秒，<span class="parmname" id="parmname2549162495220"><a name="parmname2549162495220"></a><a name="parmname2549162495220"></a>“SSS”</span>表示毫秒。</p>
    </td>
    </tr>
    <tr id="row155811648125515"><td class="cellrowborder" valign="top" width="26.21%" headers="mcps1.2.4.1.1 "><p id="p155811748115516"><a name="p155811748115516"></a><a name="p155811748115516"></a>@modelarts:end_time</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.57%" headers="mcps1.2.4.1.2 "><p id="p18581548185512"><a name="p18581548185512"></a><a name="p18581548185512"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.220000000000006%" headers="mcps1.2.4.1.3 "><p id="p97611721145610"><a name="p97611721145610"></a><a name="p97611721145610"></a>声音的结束时间，格式为<span class="parmname" id="parmname19783925614"><a name="parmname19783925614"></a><a name="parmname19783925614"></a>“hh:mm:ss.SSS”</span>。</p>
    <p id="p1581104819558"><a name="p1581104819558"></a><a name="p1581104819558"></a>其中<span class="parmname" id="parmname133421241205618"><a name="parmname133421241205618"></a><a name="parmname133421241205618"></a>“hh”</span>表示小时，<span class="parmname" id="parmname10761124575617"><a name="parmname10761124575617"></a><a name="parmname10761124575617"></a>“mm”</span>表示分钟，<span class="parmname" id="parmname9674134785613"><a name="parmname9674134785613"></a><a name="parmname9674134785613"></a>“ss”</span>表示秒，<span class="parmname" id="parmname96082718534"><a name="parmname96082718534"></a><a name="parmname96082718534"></a>“SSS”</span>表示毫秒。</p>
    </td>
    </tr>
    <tr id="row12581134805516"><td class="cellrowborder" valign="top" width="26.21%" headers="mcps1.2.4.1.1 "><p id="p11581124815551"><a name="p11581124815551"></a><a name="p11581124815551"></a>@modelarts:source</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.57%" headers="mcps1.2.4.1.2 "><p id="p2058111487559"><a name="p2058111487559"></a><a name="p2058111487559"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.220000000000006%" headers="mcps1.2.4.1.3 "><p id="p558194815513"><a name="p558194815513"></a><a name="p558194815513"></a>声音来源。</p>
    </td>
    </tr>
    <tr id="row1158124885511"><td class="cellrowborder" valign="top" width="26.21%" headers="mcps1.2.4.1.1 "><p id="p958114814553"><a name="p958114814553"></a><a name="p958114814553"></a>@modelarts:content</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.57%" headers="mcps1.2.4.1.2 "><p id="p2058118480559"><a name="p2058118480559"></a><a name="p2058118480559"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.220000000000006%" headers="mcps1.2.4.1.3 "><p id="p158104865516"><a name="p158104865516"></a><a name="p158104865516"></a>声音内容。</p>
    </td>
    </tr>
    </tbody>
    </table>


