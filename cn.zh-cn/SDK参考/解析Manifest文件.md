# 解析Manifest文件<a name="modelarts_04_0351"></a>

解析manifest文件，支持本地和OBS。如果是OBS，需要Session信息。

```
manifest.parse_manifest(manifest_path, encoding='utf-8')
```

## 示例代码<a name="section1130916814189"></a>

通过Manifest路径来解析获取Manifest的信息。

```
from modelarts.session import Session 
from modelarts.dataset.format.manifest import Manifest

path = "obs://your-obs-bucket/manifest/V001.manifest"
session = Session() 
manifest_info= Manifest.parse_manifest(path,session=session)
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
<tbody><tr id="row1685321016244"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.2.5.1.1 "><p id="p11832822194818"><a name="p11832822194818"></a><a name="p11832822194818"></a>manifest_path</p>
</td>
<td class="cellrowborder" valign="top" width="8.77%" headers="mcps1.2.5.1.2 "><p id="p184616124511"><a name="p184616124511"></a><a name="p184616124511"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.04%" headers="mcps1.2.5.1.3 "><p id="p385418296158"><a name="p385418296158"></a><a name="p385418296158"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.72%" headers="mcps1.2.5.1.4 "><p id="p5601639154814"><a name="p5601639154814"></a><a name="p5601639154814"></a>manifest文件路径，支持OBS和本地路径。如果是OBS，需要Session信息。</p>
</td>
</tr>
<tr id="row19852164442512"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.2.5.1.1 "><p id="p11852194432510"><a name="p11852194432510"></a><a name="p11852194432510"></a>encoding</p>
</td>
<td class="cellrowborder" valign="top" width="8.77%" headers="mcps1.2.5.1.2 "><p id="p785212449251"><a name="p785212449251"></a><a name="p785212449251"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.04%" headers="mcps1.2.5.1.3 "><p id="p1385214446255"><a name="p1385214446255"></a><a name="p1385214446255"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.72%" headers="mcps1.2.5.1.4 "><p id="p7831783133"><a name="p7831783133"></a><a name="p7831783133"></a>文件编码格式，默认为utf-8。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  manifest\_info返回参数说明

<a name="zh-cn_topic_0170904391_table970151471612"></a>
<table><thead align="left"><tr id="zh-cn_topic_0170904391_row12541201471612"><th class="cellrowborder" valign="top" width="22.58%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0170904391_p1454151431611"><a name="zh-cn_topic_0170904391_p1454151431611"></a><a name="zh-cn_topic_0170904391_p1454151431611"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="24.15%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0170904391_p954171417160"><a name="zh-cn_topic_0170904391_p954171417160"></a><a name="zh-cn_topic_0170904391_p954171417160"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="53.269999999999996%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0170904391_p16541131451612"><a name="zh-cn_topic_0170904391_p16541131451612"></a><a name="zh-cn_topic_0170904391_p16541131451612"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0170904391_row14541141411610"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p1540215383124"><a name="p1540215383124"></a><a name="p1540215383124"></a>size</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p198213297362"><a name="p198213297362"></a><a name="p198213297362"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p158201429183619"><a name="p158201429183619"></a><a name="p158201429183619"></a>样本数量。</p>
</td>
</tr>
<tr id="zh-cn_topic_0170904391_row4541181420167"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p1720245521220"><a name="p1720245521220"></a><a name="p1720245521220"></a>samples</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p16809220133910"><a name="p16809220133910"></a><a name="p16809220133910"></a>JSON Array</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p3817132943620"><a name="p3817132943620"></a><a name="p3817132943620"></a>样本列表。样本属性请见<a href="#table8889203855012">表3</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  sample样本属性

<a name="table8889203855012"></a>
<table><thead align="left"><tr id="row3889183817505"><th class="cellrowborder" valign="top" width="22.58%" id="mcps1.2.4.1.1"><p id="p888983865011"><a name="p888983865011"></a><a name="p888983865011"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="24.15%" id="mcps1.2.4.1.2"><p id="p88891238165016"><a name="p88891238165016"></a><a name="p88891238165016"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="53.269999999999996%" id="mcps1.2.4.1.3"><p id="p1889133855018"><a name="p1889133855018"></a><a name="p1889133855018"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1889133812501"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p9906443506"><a name="p9906443506"></a><a name="p9906443506"></a>source</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p88894386502"><a name="p88894386502"></a><a name="p88894386502"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p588943845013"><a name="p588943845013"></a><a name="p588943845013"></a>被标注对象的URI，支持的scheme有OBS、HTTPS、Content。其中Content为文本内容，例如：“source”:“s3://path-to-jpg”，“source”:“content://I love machine learning”。</p>
</td>
</tr>
<tr id="row088918385505"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p390154485011"><a name="p390154485011"></a><a name="p390154485011"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p14889938195010"><a name="p14889938195010"></a><a name="p14889938195010"></a>JSON Array</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1865446135718"><a name="p1865446135718"></a><a name="p1865446135718"></a>样本标注信息。若不给出，则是未标注对象。</p>
<p id="p68891938175018"><a name="p68891938175018"></a><a name="p68891938175018"></a>annotations值为一个对象列表。标注属性请见<a href="#table166132402112">表4</a>。</p>
</td>
</tr>
<tr id="row188993816502"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p190164414508"><a name="p190164414508"></a><a name="p190164414508"></a>usage</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1688953815016"><a name="p1688953815016"></a><a name="p1688953815016"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p5889183811500"><a name="p5889183811500"></a><a name="p5889183811500"></a>用途，可选值为TRAIN、EVAL、TEST、INFERENCE。指明该对象用于训练、评估、测试、推理，若没有给出该字段，则使用者自行决定如何使用该对象。</p>
</td>
</tr>
<tr id="row1888923885018"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p1989154412503"><a name="p1989154412503"></a><a name="p1989154412503"></a>inference_loc</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p988911387505"><a name="p988911387505"></a><a name="p988911387505"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p20889113819501"><a name="p20889113819501"></a><a name="p20889113819501"></a>当此manifest文件由推理服务生成时会有该字段，表示推理输出的结果文件位置。</p>
</td>
</tr>
<tr id="row14889138165014"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p11891044195010"><a name="p11891044195010"></a><a name="p11891044195010"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1688918381503"><a name="p1688918381503"></a><a name="p1688918381503"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1888920388508"><a name="p1888920388508"></a><a name="p1888920388508"></a>样本ID。</p>
</td>
</tr>
<tr id="row1788943895015"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p15891244165010"><a name="p15891244165010"></a><a name="p15891244165010"></a>source_type</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p11889113818509"><a name="p11889113818509"></a><a name="p11889113818509"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p18893388507"><a name="p18893388507"></a><a name="p18893388507"></a>source的类型，比如csv。</p>
</td>
</tr>
<tr id="row128891438135014"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p188644165018"><a name="p188644165018"></a><a name="p188644165018"></a>source_property</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p388915385505"><a name="p388915385505"></a><a name="p388915385505"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1289012382505"><a name="p1289012382505"></a><a name="p1289012382505"></a>source的属性。</p>
</td>
</tr>
<tr id="row2890133855018"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p118816445508"><a name="p118816445508"></a><a name="p118816445508"></a>hard</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1589019382503"><a name="p1589019382503"></a><a name="p1589019382503"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p28901638155018"><a name="p28901638155018"></a><a name="p28901638155018"></a>是否是难例，true表示是难例，false为非难例。</p>
</td>
</tr>
<tr id="row389023815011"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p9885440503"><a name="p9885440503"></a><a name="p9885440503"></a>hard_coefficient</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p208901138105020"><a name="p208901138105020"></a><a name="p208901138105020"></a>Double</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p251126155211"><a name="p251126155211"></a><a name="p251126155211"></a>难度系数，范围为[0,1]。</p>
</td>
</tr>
<tr id="row389033855016"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p158718445504"><a name="p158718445504"></a><a name="p158718445504"></a>hard_reasons</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p188903382506"><a name="p188903382506"></a><a name="p188903382506"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p2051116175213"><a name="p2051116175213"></a><a name="p2051116175213"></a>标签级别难例原因。通过中划线间隔单个难例原因ID。</p>
</td>
</tr>
<tr id="row1890153895012"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p2698447507"><a name="p2698447507"></a><a name="p2698447507"></a>source_map</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p989015382508"><a name="p989015382508"></a><a name="p989015382508"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p13890113811506"><a name="p13890113811506"></a><a name="p13890113811506"></a>source的映射。</p>
</td>
</tr>
</tbody>
</table>

**表 4**  annotation标注属性

<a name="table166132402112"></a>
<table><thead align="left"><tr id="row36131240101117"><th class="cellrowborder" valign="top" width="22.58%" id="mcps1.2.4.1.1"><p id="p1613174011117"><a name="p1613174011117"></a><a name="p1613174011117"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="24.15%" id="mcps1.2.4.1.2"><p id="p1161364010115"><a name="p1161364010115"></a><a name="p1161364010115"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="53.269999999999996%" id="mcps1.2.4.1.3"><p id="p196131140191117"><a name="p196131140191117"></a><a name="p196131140191117"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row461315401112"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p1418023013016"><a name="p1418023013016"></a><a name="p1418023013016"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1982220337711"><a name="p1982220337711"></a><a name="p1982220337711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p178217331712"><a name="p178217331712"></a><a name="p178217331712"></a>标注名称。</p>
</td>
</tr>
<tr id="row1061314014112"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p1618073013013"><a name="p1618073013013"></a><a name="p1618073013013"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p5819103311719"><a name="p5819103311719"></a><a name="p5819103311719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1581711331378"><a name="p1581711331378"></a><a name="p1581711331378"></a>标注类型。</p>
</td>
</tr>
<tr id="row15613140181111"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p51807301006"><a name="p51807301006"></a><a name="p51807301006"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p198151433771"><a name="p198151433771"></a><a name="p198151433771"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p5814233873"><a name="p5814233873"></a><a name="p5814233873"></a>标注ID。</p>
</td>
</tr>
<tr id="row961354018111"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p1917963012019"><a name="p1917963012019"></a><a name="p1917963012019"></a>annotation_loc</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1581210336720"><a name="p1581210336720"></a><a name="p1581210336720"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p19810143310718"><a name="p19810143310718"></a><a name="p19810143310718"></a>标注文件的云存储路径，对于物体检测是必选字段，对于其他类型是可选字段。</p>
</td>
</tr>
<tr id="row36131840141111"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p8179133010015"><a name="p8179133010015"></a><a name="p8179133010015"></a>annotation_property</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p18087333710"><a name="p18087333710"></a><a name="p18087333710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1480783320712"><a name="p1480783320712"></a><a name="p1480783320712"></a>标注属性。</p>
</td>
</tr>
<tr id="row8613140121110"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p417913301501"><a name="p417913301501"></a><a name="p417913301501"></a>confidence</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1680520338718"><a name="p1680520338718"></a><a name="p1680520338718"></a>Double</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1180473311711"><a name="p1180473311711"></a><a name="p1180473311711"></a>置信度，数值类型，范围0&lt;=confidence&lt;=1，表示机器标注的置信度。</p>
</td>
</tr>
<tr id="row0613154013112"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p191791130102"><a name="p191791130102"></a><a name="p191791130102"></a>creation_time</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1080112331711"><a name="p1080112331711"></a><a name="p1080112331711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1142819519213"><a name="p1142819519213"></a><a name="p1142819519213"></a>创建该标注的时间。是用户写入标注的时间，不是manifest生成时间。</p>
</td>
</tr>
<tr id="row11613114031120"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p1917933014017"><a name="p1917933014017"></a><a name="p1917933014017"></a>annotated_by</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p079803310718"><a name="p079803310718"></a><a name="p079803310718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1779723317716"><a name="p1779723317716"></a><a name="p1779723317716"></a>标注人。</p>
</td>
</tr>
<tr id="row1061317409110"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p101789304017"><a name="p101789304017"></a><a name="p101789304017"></a>annotation_format</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1079419333716"><a name="p1079419333716"></a><a name="p1079419333716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p01271693127"><a name="p01271693127"></a><a name="p01271693127"></a>描述标注文件的格式。默认为“PASCAL VOC”。</p>
</td>
</tr>
<tr id="row361314011114"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p6178230804"><a name="p6178230804"></a><a name="p6178230804"></a>hard</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1079183314718"><a name="p1079183314718"></a><a name="p1079183314718"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p279017331179"><a name="p279017331179"></a><a name="p279017331179"></a>是否是难例。</p>
</td>
</tr>
<tr id="row76131040161119"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p1517815301806"><a name="p1517815301806"></a><a name="p1517815301806"></a>hard_coefficient</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p1878815338716"><a name="p1878815338716"></a><a name="p1878815338716"></a>Double</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p1776916331477"><a name="p1776916331477"></a><a name="p1776916331477"></a>难度系数。</p>
</td>
</tr>
<tr id="row176661451582"><td class="cellrowborder" valign="top" width="22.58%" headers="mcps1.2.4.1.1 "><p id="p13159230102"><a name="p13159230102"></a><a name="p13159230102"></a>annotation_loc_map</p>
</td>
<td class="cellrowborder" valign="top" width="24.15%" headers="mcps1.2.4.1.2 "><p id="p176670451884"><a name="p176670451884"></a><a name="p176670451884"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="53.269999999999996%" headers="mcps1.2.4.1.3 "><p id="p86672045480"><a name="p86672045480"></a><a name="p86672045480"></a>标注文件路径的映射。</p>
</td>
</tr>
</tbody>
</table>

