# 解析Pascal VOC文件<a name="modelarts_04_0353"></a>

解析xml文件支持本地和OBS，如果是OBS，需要Session信息。

```
PascalVoc.parse_xml(xml_file_path, session=None)
```

## 示例代码<a name="section1130916814189"></a>

指定xml路径，通过调用parse\_xml来解析获取xml文件的信息。

```
from modelarts.dataset.format.voc.pascal_voc import PascalVoc
from modelarts.session import Session

path = "obs://your-obs-bucket/voc/test.xml"
session = Session()
pascal_voc = PascalVoc.parse_xml(path, session=session)
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
<td class="cellrowborder" valign="top" width="54.72%" headers="mcps1.2.5.1.4 "><p id="p5601639154814"><a name="p5601639154814"></a><a name="p5601639154814"></a>xml文件<span id="ph8841145772617"><a name="ph8841145772617"></a><a name="ph8841145772617"></a>路径</span>。</p>
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
</tbody>
</table>

**表 2**  pascal\_voc 返回参数

<a name="zh-cn_topic_0170904391_table970151471612"></a>
<table><thead align="left"><tr id="zh-cn_topic_0170904391_row12541201471612"><th class="cellrowborder" valign="top" width="22.58%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0170904391_p1454151431611"><a name="zh-cn_topic_0170904391_p1454151431611"></a><a name="zh-cn_topic_0170904391_p1454151431611"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="24.15%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0170904391_p954171417160"><a name="zh-cn_topic_0170904391_p954171417160"></a><a name="zh-cn_topic_0170904391_p954171417160"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="53.269999999999996%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0170904391_p16541131451612"><a name="zh-cn_topic_0170904391_p16541131451612"></a><a name="zh-cn_topic_0170904391_p16541131451612"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0170904391_row14541141411610"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p9365142013168"><a name="p9365142013168"></a><a name="p9365142013168"></a>folder</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p198213297362"><a name="p198213297362"></a><a name="p198213297362"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p158201429183619"><a name="p158201429183619"></a><a name="p158201429183619"></a>文件夹名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0170904391_row4541181420167"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p17365620171619"><a name="p17365620171619"></a><a name="p17365620171619"></a>file_name</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p57641916114117"><a name="p57641916114117"></a><a name="p57641916114117"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p171342010104112"><a name="p171342010104112"></a><a name="p171342010104112"></a>文件名称。</p>
</td>
</tr>
<tr id="row199642026104114"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p4365192015166"><a name="p4365192015166"></a><a name="p4365192015166"></a>source</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1099758154314"><a name="p1099758154314"></a><a name="p1099758154314"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p129651226114110"><a name="p129651226114110"></a><a name="p129651226114110"></a>数据源信息，详细请见<a href="#table2056114243438">表3</a>。</p>
</td>
</tr>
<tr id="row16480103713418"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p53648203163"><a name="p53648203163"></a><a name="p53648203163"></a>width</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1648012373419"><a name="p1648012373419"></a><a name="p1648012373419"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p9480137174120"><a name="p9480137174120"></a><a name="p9480137174120"></a>图片长度。</p>
</td>
</tr>
<tr id="row131434716419"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p4364132041614"><a name="p4364132041614"></a><a name="p4364132041614"></a>height</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p201415474415"><a name="p201415474415"></a><a name="p201415474415"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p131413473413"><a name="p131413473413"></a><a name="p131413473413"></a>图片高度。</p>
</td>
</tr>
<tr id="row95681144144118"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p16363520121611"><a name="p16363520121611"></a><a name="p16363520121611"></a>depth</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p856844417412"><a name="p856844417412"></a><a name="p856844417412"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p45681444194113"><a name="p45681444194113"></a><a name="p45681444194113"></a>图片深度。</p>
</td>
</tr>
<tr id="row1293184115417"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p636352013161"><a name="p636352013161"></a><a name="p636352013161"></a>segmented</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p529304114119"><a name="p529304114119"></a><a name="p529304114119"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p11293154119415"><a name="p11293154119415"></a><a name="p11293154119415"></a>分割。</p>
</td>
</tr>
<tr id="row1719213184111"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p143631020131611"><a name="p143631020131611"></a><a name="p143631020131611"></a>mask_source</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p17192163118419"><a name="p17192163118419"></a><a name="p17192163118419"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p2192031104118"><a name="p2192031104118"></a><a name="p2192031104118"></a>图像分割得到的mask文件的云存储路径，目前只支持PNG格式。</p>
</td>
</tr>
<tr id="row7516534134111"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p1534418209164"><a name="p1534418209164"></a><a name="p1534418209164"></a>voc_objects</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p37841349113912"><a name="p37841349113912"></a><a name="p37841349113912"></a>JSON Array</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p11516734164117"><a name="p11516734164117"></a><a name="p11516734164117"></a>标注对象列表，详细请见<a href="#table17421625134317">表4</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  source参数

<a name="table2056114243438"></a>
<table><thead align="left"><tr id="row6561182413434"><th class="cellrowborder" valign="top" width="22.58%" id="mcps1.2.4.1.1"><p id="p3561924104317"><a name="p3561924104317"></a><a name="p3561924104317"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="24.15%" id="mcps1.2.4.1.2"><p id="p10561112454320"><a name="p10561112454320"></a><a name="p10561112454320"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="53.269999999999996%" id="mcps1.2.4.1.3"><p id="p75619248437"><a name="p75619248437"></a><a name="p75619248437"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row155611824194312"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p19335161820174"><a name="p19335161820174"></a><a name="p19335161820174"></a>database</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1156192418437"><a name="p1156192418437"></a><a name="p1156192418437"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p20943318154712"><a name="p20943318154712"></a><a name="p20943318154712"></a>数据集名称，比如“The VOC2007 Database”。</p>
</td>
</tr>
<tr id="row16561824184319"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p3335718101719"><a name="p3335718101719"></a><a name="p3335718101719"></a>annotation</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1556102415434"><a name="p1556102415434"></a><a name="p1556102415434"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p2561624104313"><a name="p2561624104313"></a><a name="p2561624104313"></a>标注，比如“PASCAL VOC2007”。</p>
</td>
</tr>
<tr id="row556117246433"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p73171618181717"><a name="p73171618181717"></a><a name="p73171618181717"></a>image</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p17561142454314"><a name="p17561142454314"></a><a name="p17561142454314"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p756117241433"><a name="p756117241433"></a><a name="p756117241433"></a>图片信息。</p>
</td>
</tr>
</tbody>
</table>

**表 4**  voc\_object参数

<a name="table17421625134317"></a>
<table><thead align="left"><tr id="row1574214254433"><th class="cellrowborder" valign="top" width="22.58%" id="mcps1.2.4.1.1"><p id="p874242519433"><a name="p874242519433"></a><a name="p874242519433"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="24.15%" id="mcps1.2.4.1.2"><p id="p074214253438"><a name="p074214253438"></a><a name="p074214253438"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="53.269999999999996%" id="mcps1.2.4.1.3"><p id="p974212514433"><a name="p974212514433"></a><a name="p974212514433"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1074220253430"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p147271310201815"><a name="p147271310201815"></a><a name="p147271310201815"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p18742122518438"><a name="p18742122518438"></a><a name="p18742122518438"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p10742525154312"><a name="p10742525154312"></a><a name="p10742525154312"></a>文件夹名称。</p>
</td>
</tr>
<tr id="row18742725114315"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p11726201001816"><a name="p11726201001816"></a><a name="p11726201001816"></a>properties</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0179315308_p1756418919215"><a name="zh-cn_topic_0179315308_p1756418919215"></a><a name="zh-cn_topic_0179315308_p1756418919215"></a>JSON Array</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p22437421401"><a name="p22437421401"></a><a name="p22437421401"></a>标注对象属性，为key-value列表格式，其中key和value的值均为String类型。</p>
</td>
</tr>
<tr id="row127420258432"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p15726101061819"><a name="p15726101061819"></a><a name="p15726101061819"></a>pose</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p162438425018"><a name="p162438425018"></a><a name="p162438425018"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p82251424017"><a name="p82251424017"></a><a name="p82251424017"></a>标注内容的拍摄角度。</p>
</td>
</tr>
<tr id="row9742325154318"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p972661019186"><a name="p972661019186"></a><a name="p972661019186"></a>truncated</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p5742192544313"><a name="p5742192544313"></a><a name="p5742192544313"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1674222514319"><a name="p1674222514319"></a><a name="p1674222514319"></a>标注内容是否被截断（0表示完整）。</p>
</td>
</tr>
<tr id="row12742725134316"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p87261010131810"><a name="p87261010131810"></a><a name="p87261010131810"></a>occluded</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p974272516433"><a name="p974272516433"></a><a name="p974272516433"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p137421325164314"><a name="p137421325164314"></a><a name="p137421325164314"></a>标注内容是否被遮挡（0表示未遮挡）。</p>
</td>
</tr>
<tr id="row1074213257432"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p13725131013182"><a name="p13725131013182"></a><a name="p13725131013182"></a>difficult</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p167421425184314"><a name="p167421425184314"></a><a name="p167421425184314"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p147429257435"><a name="p147429257435"></a><a name="p147429257435"></a>标注目标是否难以识别（0表示容易识别）。</p>
</td>
</tr>
<tr id="row17742142513431"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p127251010141818"><a name="p127251010141818"></a><a name="p127251010141818"></a>confidence</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1174214258436"><a name="p1174214258436"></a><a name="p1174214258436"></a>Double</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1180473311711"><a name="p1180473311711"></a><a name="p1180473311711"></a>置信度，数值类型，范围0&lt;=confidence&lt;=1，表示机器标注的置信度。</p>
</td>
</tr>
<tr id="row13742102512434"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p197251210161813"><a name="p197251210161813"></a><a name="p197251210161813"></a>position</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p2742122584316"><a name="p2742122584316"></a><a name="p2742122584316"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p574212517432"><a name="p574212517432"></a><a name="p574212517432"></a>标注对象的位置信息，详细请见<a href="#table2082317383192">表5</a>。</p>
</td>
</tr>
<tr id="row2742152534315"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p1972441016184"><a name="p1972441016184"></a><a name="p1972441016184"></a>parts</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p117421525144310"><a name="p117421525144310"></a><a name="p117421525144310"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p157421625104310"><a name="p157421625104310"></a><a name="p157421625104310"></a>子标注对象列表，即嵌套的voc_object列表，详细请见<a href="#table17421625134317">表4</a>。</p>
</td>
</tr>
<tr id="row1323413235117"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p4706131012187"><a name="p4706131012187"></a><a name="p4706131012187"></a>mask_color</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p323419238115"><a name="p323419238115"></a><a name="p323419238115"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1023416235116"><a name="p1023416235116"></a><a name="p1023416235116"></a>图像分割mask图像的颜色。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  Position说明

<a name="table2082317383192"></a>
<table><thead align="left"><tr id="row1082363811194"><th class="cellrowborder" valign="top" width="22.58%" id="mcps1.2.4.1.1"><p id="p34961231192117"><a name="p34961231192117"></a><a name="p34961231192117"></a>type</p>
</th>
<th class="cellrowborder" valign="top" width="24.15%" id="mcps1.2.4.1.2"><p id="p9496183115219"><a name="p9496183115219"></a><a name="p9496183115219"></a>形状</p>
</th>
<th class="cellrowborder" valign="top" width="53.269999999999996%" id="mcps1.2.4.1.3"><p id="p74961431182119"><a name="p74961431182119"></a><a name="p74961431182119"></a>标注信息</p>
</th>
</tr>
</thead>
<tbody><tr id="row1382316387193"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p1449618318218"><a name="p1449618318218"></a><a name="p1449618318218"></a>point</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p849615313211"><a name="p849615313211"></a><a name="p849615313211"></a>点</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1249610315215"><a name="p1249610315215"></a><a name="p1249610315215"></a>点的坐标</p>
<p id="p549673115213"><a name="p549673115213"></a><a name="p549673115213"></a>&lt;x&gt;100&lt;x&gt;</p>
<p id="p12496143162116"><a name="p12496143162116"></a><a name="p12496143162116"></a>&lt;y&gt;100&lt;y&gt;</p>
</td>
</tr>
<tr id="row18231138191911"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p849614310214"><a name="p849614310214"></a><a name="p849614310214"></a>line</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p5496123117214"><a name="p5496123117214"></a><a name="p5496123117214"></a>线</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p2496931122115"><a name="p2496931122115"></a><a name="p2496931122115"></a>各点坐标</p>
<p id="p749619316219"><a name="p749619316219"></a><a name="p749619316219"></a>&lt;x1&gt;100&lt;x1&gt;</p>
<p id="p14969312218"><a name="p14969312218"></a><a name="p14969312218"></a>&lt;y1&gt;100&lt;y1&gt;</p>
<p id="p1049614313217"><a name="p1049614313217"></a><a name="p1049614313217"></a>&lt;x2&gt;200&lt;x2&gt;</p>
<p id="p8496131152115"><a name="p8496131152115"></a><a name="p8496131152115"></a>&lt;y2&gt;200&lt;y2&gt;</p>
</td>
</tr>
<tr id="row7823193816194"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p14496631172112"><a name="p14496631172112"></a><a name="p14496631172112"></a>bndbox</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p20496231192111"><a name="p20496231192111"></a><a name="p20496231192111"></a>矩形框</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p17496123192111"><a name="p17496123192111"></a><a name="p17496123192111"></a>左下和右上两个点坐标</p>
<p id="p1496183114217"><a name="p1496183114217"></a><a name="p1496183114217"></a>&lt;x_min&gt;100&lt;x_min&gt;</p>
<p id="p349615319216"><a name="p349615319216"></a><a name="p349615319216"></a>&lt;y_min&gt;100&lt;y_min&gt;</p>
<p id="p449663102119"><a name="p449663102119"></a><a name="p449663102119"></a>&lt;x_max&gt;200&lt;x_max&gt;</p>
<p id="p10496163122113"><a name="p10496163122113"></a><a name="p10496163122113"></a>&lt;y_max&gt;200&lt;y_max&gt;</p>
<p id="p94961731132112"><a name="p94961731132112"></a><a name="p94961731132112"></a></p>
</td>
</tr>
<tr id="row78241638191911"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p149693114214"><a name="p149693114214"></a><a name="p149693114214"></a>polygon</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1749610312211"><a name="p1749610312211"></a><a name="p1749610312211"></a>多边形</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1449693119214"><a name="p1449693119214"></a><a name="p1449693119214"></a>各点坐标</p>
<p id="p149614319214"><a name="p149614319214"></a><a name="p149614319214"></a>&lt;x1&gt;100&lt;x1&gt;</p>
<p id="p9496153116213"><a name="p9496153116213"></a><a name="p9496153116213"></a>&lt;y1&gt;100&lt;y1&gt;</p>
<p id="p649611313216"><a name="p649611313216"></a><a name="p649611313216"></a>&lt;x2&gt;200&lt;x2&gt;</p>
<p id="p449618317214"><a name="p449618317214"></a><a name="p449618317214"></a>&lt;y2&gt;100&lt;y2&gt;</p>
<p id="p1649613112214"><a name="p1649613112214"></a><a name="p1649613112214"></a>&lt;x3&gt;250&lt;x3&gt;</p>
<p id="p1649673172110"><a name="p1649673172110"></a><a name="p1649673172110"></a>&lt;y3&gt;150&lt;y3&gt;</p>
<p id="p1497031182116"><a name="p1497031182116"></a><a name="p1497031182116"></a>&lt;x4&gt;200&lt;x4&gt;</p>
<p id="p124973311211"><a name="p124973311211"></a><a name="p124973311211"></a>&lt;y4&gt;200&lt;y4&gt;</p>
<p id="p0497123119214"><a name="p0497123119214"></a><a name="p0497123119214"></a>&lt;x5&gt;100&lt;x5&gt;</p>
<p id="p1049763112112"><a name="p1049763112112"></a><a name="p1049763112112"></a>&lt;y5&gt;200&lt;y5&gt;</p>
<p id="p1449753111214"><a name="p1449753111214"></a><a name="p1449753111214"></a>&lt;x6&gt;50&lt;x6&gt;</p>
<p id="p104972313216"><a name="p104972313216"></a><a name="p104972313216"></a>&lt;y6&gt;150&lt;y6&gt;</p>
</td>
</tr>
<tr id="row178061226152116"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p11497123122114"><a name="p11497123122114"></a><a name="p11497123122114"></a>circle</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p149713114212"><a name="p149713114212"></a><a name="p149713114212"></a>圆形</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p94970315213"><a name="p94970315213"></a><a name="p94970315213"></a>圆心坐标和半径</p>
<p id="p184971031122112"><a name="p184971031122112"></a><a name="p184971031122112"></a>&lt;cx&gt;100&lt;cx&gt;</p>
<p id="p5497193122110"><a name="p5497193122110"></a><a name="p5497193122110"></a>&lt;cy&gt;100&lt;cy&gt;</p>
<p id="p64971531172113"><a name="p64971531172113"></a><a name="p64971531172113"></a>&lt;r&gt;50&lt;r&gt;</p>
</td>
</tr>
</tbody>
</table>

