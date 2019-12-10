# ModelArts支持的监控指标<a name="modelarts_23_0187"></a>

## 功能说明<a name="section15651122173511"></a>

为使用户更好地掌握自己的ModelArts在线服务和对应模型负载的运行状态，公有云平台提供了云监控。您可以使用该服务监控您的ModelArts在线服务和对应模型负载，执行自动实时监控、告警和通知操作，帮助您更好地了解服务和模型的各项性能指标。

## 命名空间<a name="section16695191443410"></a>

SYS.ModelArts

## 监控指标<a name="section15935133518359"></a>

**表 1**  ModelArts支持的监控指标

<a name="table3293914123812"></a>
<table><thead align="left"><tr id="row429415149384"><th class="cellrowborder" valign="top" width="15.16848315168483%" id="mcps1.2.7.1.1"><p id="p929461493813"><a name="p929461493813"></a><a name="p929461493813"></a>指标ID</p>
</th>
<th class="cellrowborder" valign="top" width="14.83851614838516%" id="mcps1.2.7.1.2"><p id="p14294151473815"><a name="p14294151473815"></a><a name="p14294151473815"></a>指标名称</p>
</th>
<th class="cellrowborder" valign="top" width="23.187681231876812%" id="mcps1.2.7.1.3"><p id="p132951514193813"><a name="p132951514193813"></a><a name="p132951514193813"></a>含义</p>
</th>
<th class="cellrowborder" valign="top" width="14.2985701429857%" id="mcps1.2.7.1.4"><p id="p1929510147381"><a name="p1929510147381"></a><a name="p1929510147381"></a>取值范围</p>
</th>
<th class="cellrowborder" valign="top" width="17.10828917108289%" id="mcps1.2.7.1.5"><p id="p42952014203811"><a name="p42952014203811"></a><a name="p42952014203811"></a>测量对象&amp;维度</p>
</th>
<th class="cellrowborder" valign="top" width="15.398460153984603%" id="mcps1.2.7.1.6"><p id="p129531413386"><a name="p129531413386"></a><a name="p129531413386"></a>监控周期</p>
</th>
</tr>
</thead>
<tbody><tr id="row8295111416383"><td class="cellrowborder" valign="top" width="15.16848315168483%" headers="mcps1.2.7.1.1 "><p id="p029581418384"><a name="p029581418384"></a><a name="p029581418384"></a>cpu_usage</p>
</td>
<td class="cellrowborder" valign="top" width="14.83851614838516%" headers="mcps1.2.7.1.2 "><p id="p11295161473816"><a name="p11295161473816"></a><a name="p11295161473816"></a>CPU使用率</p>
</td>
<td class="cellrowborder" valign="top" width="23.187681231876812%" headers="mcps1.2.7.1.3 "><p id="p182956141381"><a name="p182956141381"></a><a name="p182956141381"></a>该指标用于统计ModelArts用户服务的CPU使用率。</p>
<p id="p15295214133820"><a name="p15295214133820"></a><a name="p15295214133820"></a>单位：百分比。</p>
</td>
<td class="cellrowborder" valign="top" width="14.2985701429857%" headers="mcps1.2.7.1.4 "><p id="p202958148386"><a name="p202958148386"></a><a name="p202958148386"></a>≥ 0%</p>
</td>
<td class="cellrowborder" valign="top" width="17.10828917108289%" headers="mcps1.2.7.1.5 "><p id="p198839715365"><a name="p198839715365"></a><a name="p198839715365"></a>测量对象：</p>
<p id="p417318245378"><a name="p417318245378"></a><a name="p417318245378"></a>ModelArts模型负载</p>
<p id="p69869316376"><a name="p69869316376"></a><a name="p69869316376"></a>测量维度：</p>
<p id="p029514149385"><a name="p029514149385"></a><a name="p029514149385"></a>model_id</p>
</td>
<td class="cellrowborder" valign="top" width="15.398460153984603%" headers="mcps1.2.7.1.6 "><p id="p122951414103812"><a name="p122951414103812"></a><a name="p122951414103812"></a>1分钟</p>
</td>
</tr>
<tr id="row1929581418384"><td class="cellrowborder" valign="top" width="15.16848315168483%" headers="mcps1.2.7.1.1 "><p id="p8295151416382"><a name="p8295151416382"></a><a name="p8295151416382"></a>mem_usage</p>
</td>
<td class="cellrowborder" valign="top" width="14.83851614838516%" headers="mcps1.2.7.1.2 "><p id="p10296131415387"><a name="p10296131415387"></a><a name="p10296131415387"></a>内存使用率</p>
</td>
<td class="cellrowborder" valign="top" width="23.187681231876812%" headers="mcps1.2.7.1.3 "><p id="p629601423814"><a name="p629601423814"></a><a name="p629601423814"></a>该指标用于统计ModelArts用户服务的内存使用率。</p>
<p id="p18296141473815"><a name="p18296141473815"></a><a name="p18296141473815"></a>单位：百分比。</p>
</td>
<td class="cellrowborder" valign="top" width="14.2985701429857%" headers="mcps1.2.7.1.4 "><p id="p17296214133817"><a name="p17296214133817"></a><a name="p17296214133817"></a>≥ 0%</p>
</td>
<td class="cellrowborder" valign="top" width="17.10828917108289%" headers="mcps1.2.7.1.5 "><p id="p21129291113"><a name="p21129291113"></a><a name="p21129291113"></a>测量对象：</p>
<p id="p171125292015"><a name="p171125292015"></a><a name="p171125292015"></a>ModelArts模型负载</p>
<p id="p161125293112"><a name="p161125293112"></a><a name="p161125293112"></a>测量维度：</p>
<p id="p151136294119"><a name="p151136294119"></a><a name="p151136294119"></a>model_id</p>
</td>
<td class="cellrowborder" valign="top" width="15.398460153984603%" headers="mcps1.2.7.1.6 "><p id="p3296161483811"><a name="p3296161483811"></a><a name="p3296161483811"></a>1分钟</p>
</td>
</tr>
<tr id="row929620142382"><td class="cellrowborder" valign="top" width="15.16848315168483%" headers="mcps1.2.7.1.1 "><p id="p1629611413818"><a name="p1629611413818"></a><a name="p1629611413818"></a>gpu_util</p>
</td>
<td class="cellrowborder" valign="top" width="14.83851614838516%" headers="mcps1.2.7.1.2 "><p id="p12296201411385"><a name="p12296201411385"></a><a name="p12296201411385"></a>GPU使用率</p>
</td>
<td class="cellrowborder" valign="top" width="23.187681231876812%" headers="mcps1.2.7.1.3 "><p id="p429641418384"><a name="p429641418384"></a><a name="p429641418384"></a>该指标用于统计ModelArts用户服务的磁盘使用情况。</p>
<p id="p17296161463817"><a name="p17296161463817"></a><a name="p17296161463817"></a>单位：百分比。</p>
</td>
<td class="cellrowborder" valign="top" width="14.2985701429857%" headers="mcps1.2.7.1.4 "><p id="p329661433817"><a name="p329661433817"></a><a name="p329661433817"></a>≥ 0%</p>
</td>
<td class="cellrowborder" valign="top" width="17.10828917108289%" headers="mcps1.2.7.1.5 "><p id="p91341738518"><a name="p91341738518"></a><a name="p91341738518"></a>测量对象：</p>
<p id="p1213414381013"><a name="p1213414381013"></a><a name="p1213414381013"></a>ModelArts模型负载</p>
<p id="p713416383111"><a name="p713416383111"></a><a name="p713416383111"></a>测量维度：</p>
<p id="p813415381418"><a name="p813415381418"></a><a name="p813415381418"></a>model_id</p>
</td>
<td class="cellrowborder" valign="top" width="15.398460153984603%" headers="mcps1.2.7.1.6 "><p id="p1296614103812"><a name="p1296614103812"></a><a name="p1296614103812"></a>1分钟</p>
</td>
</tr>
<tr id="row14296181416382"><td class="cellrowborder" valign="top" width="15.16848315168483%" headers="mcps1.2.7.1.1 "><p id="p16296101416381"><a name="p16296101416381"></a><a name="p16296101416381"></a>gpu_mem_usage</p>
</td>
<td class="cellrowborder" valign="top" width="14.83851614838516%" headers="mcps1.2.7.1.2 "><p id="p8296151433813"><a name="p8296151433813"></a><a name="p8296151433813"></a>GPU显存使用率</p>
</td>
<td class="cellrowborder" valign="top" width="23.187681231876812%" headers="mcps1.2.7.1.3 "><p id="p329616144384"><a name="p329616144384"></a><a name="p329616144384"></a>该指标用于统计ModelArts用户服务的磁盘显存使用情况。</p>
<p id="p20296514153815"><a name="p20296514153815"></a><a name="p20296514153815"></a>单位：百分比。</p>
</td>
<td class="cellrowborder" valign="top" width="14.2985701429857%" headers="mcps1.2.7.1.4 "><p id="p529761415384"><a name="p529761415384"></a><a name="p529761415384"></a>≥ 0%</p>
</td>
<td class="cellrowborder" valign="top" width="17.10828917108289%" headers="mcps1.2.7.1.5 "><p id="p68346409117"><a name="p68346409117"></a><a name="p68346409117"></a>测量对象：</p>
<p id="p883410405118"><a name="p883410405118"></a><a name="p883410405118"></a>ModelArts模型负载</p>
<p id="p1683484018116"><a name="p1683484018116"></a><a name="p1683484018116"></a>测量维度：</p>
<p id="p1183454018115"><a name="p1183454018115"></a><a name="p1183454018115"></a>model_id</p>
</td>
<td class="cellrowborder" valign="top" width="15.398460153984603%" headers="mcps1.2.7.1.6 "><p id="p202971514163810"><a name="p202971514163810"></a><a name="p202971514163810"></a>1分钟</p>
</td>
</tr>
<tr id="row11297111413388"><td class="cellrowborder" valign="top" width="15.16848315168483%" headers="mcps1.2.7.1.1 "><p id="p829741433814"><a name="p829741433814"></a><a name="p829741433814"></a>successfully_called_times</p>
</td>
<td class="cellrowborder" valign="top" width="14.83851614838516%" headers="mcps1.2.7.1.2 "><p id="p1529741417387"><a name="p1529741417387"></a><a name="p1529741417387"></a>调用成功次数</p>
</td>
<td class="cellrowborder" valign="top" width="23.187681231876812%" headers="mcps1.2.7.1.3 "><p id="p229751419387"><a name="p229751419387"></a><a name="p229751419387"></a>统计ModelArts用户调用服务的成功次数。</p>
<p id="p4297114133819"><a name="p4297114133819"></a><a name="p4297114133819"></a>单位：次/分钟。</p>
</td>
<td class="cellrowborder" valign="top" width="14.2985701429857%" headers="mcps1.2.7.1.4 "><p id="p129731413380"><a name="p129731413380"></a><a name="p129731413380"></a>≥Count/min</p>
</td>
<td class="cellrowborder" valign="top" width="17.10828917108289%" headers="mcps1.2.7.1.5 "><p id="p198111346116"><a name="p198111346116"></a><a name="p198111346116"></a>测量对象：</p>
<p id="p19811144610118"><a name="p19811144610118"></a><a name="p19811144610118"></a>ModelArts模型负载</p>
<p id="p35743546119"><a name="p35743546119"></a><a name="p35743546119"></a>ModelArts在线服务</p>
<p id="p4811104615113"><a name="p4811104615113"></a><a name="p4811104615113"></a>测量维度：</p>
<p id="p316813912175"><a name="p316813912175"></a><a name="p316813912175"></a>model_id，</p>
<p id="p729761411388"><a name="p729761411388"></a><a name="p729761411388"></a>service_id</p>
</td>
<td class="cellrowborder" valign="top" width="15.398460153984603%" headers="mcps1.2.7.1.6 "><p id="p729741483817"><a name="p729741483817"></a><a name="p729741483817"></a>1分钟</p>
</td>
</tr>
<tr id="row1297111463817"><td class="cellrowborder" valign="top" width="15.16848315168483%" headers="mcps1.2.7.1.1 "><p id="p1429719147389"><a name="p1429719147389"></a><a name="p1429719147389"></a>failed_called_times</p>
</td>
<td class="cellrowborder" valign="top" width="14.83851614838516%" headers="mcps1.2.7.1.2 "><p id="p829771417381"><a name="p829771417381"></a><a name="p829771417381"></a>调用失败次数</p>
</td>
<td class="cellrowborder" valign="top" width="23.187681231876812%" headers="mcps1.2.7.1.3 "><p id="p16297101413811"><a name="p16297101413811"></a><a name="p16297101413811"></a>统计ModelArts用户调用服务的失败次数。</p>
<p id="p82971114143820"><a name="p82971114143820"></a><a name="p82971114143820"></a>单位：次/分钟。</p>
</td>
<td class="cellrowborder" valign="top" width="14.2985701429857%" headers="mcps1.2.7.1.4 "><p id="p172971914183818"><a name="p172971914183818"></a><a name="p172971914183818"></a>≥Count/min</p>
</td>
<td class="cellrowborder" valign="top" width="17.10828917108289%" headers="mcps1.2.7.1.5 "><p id="p647588625"><a name="p647588625"></a><a name="p647588625"></a>测量对象：</p>
<p id="p1847516812217"><a name="p1847516812217"></a><a name="p1847516812217"></a>ModelArts模型负载</p>
<p id="p94752080220"><a name="p94752080220"></a><a name="p94752080220"></a>ModelArts在线服务</p>
<p id="p747518816214"><a name="p747518816214"></a><a name="p747518816214"></a>测量维度：</p>
<p id="p46951212111716"><a name="p46951212111716"></a><a name="p46951212111716"></a>model_id，</p>
<p id="p1229741414381"><a name="p1229741414381"></a><a name="p1229741414381"></a>service_id</p>
</td>
<td class="cellrowborder" valign="top" width="15.398460153984603%" headers="mcps1.2.7.1.6 "><p id="p182971144380"><a name="p182971144380"></a><a name="p182971144380"></a>1分钟</p>
</td>
</tr>
<tr id="row17297111443818"><td class="cellrowborder" valign="top" width="15.16848315168483%" headers="mcps1.2.7.1.1 "><p id="p1629781410382"><a name="p1629781410382"></a><a name="p1629781410382"></a>total_called_times</p>
</td>
<td class="cellrowborder" valign="top" width="14.83851614838516%" headers="mcps1.2.7.1.2 "><p id="p9298114203814"><a name="p9298114203814"></a><a name="p9298114203814"></a>调用次数</p>
</td>
<td class="cellrowborder" valign="top" width="23.187681231876812%" headers="mcps1.2.7.1.3 "><p id="p12981414123820"><a name="p12981414123820"></a><a name="p12981414123820"></a>统计ModelArts用户调用服务的次数。</p>
<p id="p12983143387"><a name="p12983143387"></a><a name="p12983143387"></a>单位：次/分钟。</p>
</td>
<td class="cellrowborder" valign="top" width="14.2985701429857%" headers="mcps1.2.7.1.4 "><p id="p829819147389"><a name="p829819147389"></a><a name="p829819147389"></a>≥Count/min</p>
</td>
<td class="cellrowborder" valign="top" width="17.10828917108289%" headers="mcps1.2.7.1.5 "><p id="p131081313627"><a name="p131081313627"></a><a name="p131081313627"></a>测量对象：</p>
<p id="p101080131226"><a name="p101080131226"></a><a name="p101080131226"></a>ModelArts模型负载</p>
<p id="p1610813131426"><a name="p1610813131426"></a><a name="p1610813131426"></a>ModelArts在线服务</p>
<p id="p1110812132020"><a name="p1110812132020"></a><a name="p1110812132020"></a>测量维度：</p>
<p id="p197131613176"><a name="p197131613176"></a><a name="p197131613176"></a>model_id，</p>
<p id="p152981214193810"><a name="p152981214193810"></a><a name="p152981214193810"></a>service_id</p>
</td>
<td class="cellrowborder" valign="top" width="15.398460153984603%" headers="mcps1.2.7.1.6 "><p id="p16298191416382"><a name="p16298191416382"></a><a name="p16298191416382"></a>1分钟</p>
</td>
</tr>
<tr id="row134045328819"><td class="cellrowborder" colspan="6" valign="top" headers="mcps1.2.7.1.1 mcps1.2.7.1.2 mcps1.2.7.1.3 mcps1.2.7.1.4 mcps1.2.7.1.5 mcps1.2.7.1.6 "><p id="p216913514125"><a name="p216913514125"></a><a name="p216913514125"></a>对于有多个测量维度的测量对象，使用接口查询监控指标时，所有测量维度均为必选。</p>
<a name="ul2016993518128"></a><a name="ul2016993518128"></a><ul id="ul2016993518128"><li>查询单个监控指标时，多维度dim使用样例：dim.0=service_id,530cd6b0-86d7-4818-837f-935f6a27414d&amp;dim.1="model_id,3773b058-5b4f-4366-9035-9bbd9964714a。</li><li>批量查询监控指标时，多维度dim使用样例：<p id="p20169153516124"><a name="p20169153516124"></a><a name="p20169153516124"></a>"dimensions": [</p>
<p id="p1316903519122"><a name="p1316903519122"></a><a name="p1316903519122"></a>{</p>
<p id="p816903516122"><a name="p816903516122"></a><a name="p816903516122"></a>"name": "service_id",</p>
<p id="p916953591215"><a name="p916953591215"></a><a name="p916953591215"></a>"value": "530cd6b0-86d7-4818-837f-935f6a27414d"</p>
<p id="p316953520127"><a name="p316953520127"></a><a name="p316953520127"></a>}</p>
<p id="p8169113521219"><a name="p8169113521219"></a><a name="p8169113521219"></a>{</p>
<p id="p41692035161218"><a name="p41692035161218"></a><a name="p41692035161218"></a>"name": "model_id",</p>
<p id="p8169173581214"><a name="p8169173581214"></a><a name="p8169173581214"></a>"value": "3773b058-5b4f-4366-9035-9bbd9964714a"</p>
<p id="p1169635101211"><a name="p1169635101211"></a><a name="p1169635101211"></a>}</p>
<p id="p14170103518125"><a name="p14170103518125"></a><a name="p14170103518125"></a>],</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

## 维度<a name="section1432993519387"></a>

**表 2**  维度说明

<a name="table130310173915"></a>
<table><thead align="left"><tr id="row180161014397"><th class="cellrowborder" valign="top" width="48.74%" id="mcps1.2.3.1.1"><p id="p150111013393"><a name="p150111013393"></a><a name="p150111013393"></a>Key</p>
</th>
<th class="cellrowborder" valign="top" width="51.25999999999999%" id="mcps1.2.3.1.2"><p id="p170101018391"><a name="p170101018391"></a><a name="p170101018391"></a>Value</p>
</th>
</tr>
</thead>
<tbody><tr id="row511910163916"><td class="cellrowborder" valign="top" width="48.74%" headers="mcps1.2.3.1.1 "><p id="p9111033917"><a name="p9111033917"></a><a name="p9111033917"></a>service_id</p>
</td>
<td class="cellrowborder" valign="top" width="51.25999999999999%" headers="mcps1.2.3.1.2 "><p id="p118109393"><a name="p118109393"></a><a name="p118109393"></a>在线服务ID。</p>
</td>
</tr>
<tr id="row1141063916"><td class="cellrowborder" valign="top" width="48.74%" headers="mcps1.2.3.1.1 "><p id="p91810153912"><a name="p91810153912"></a><a name="p91810153912"></a>model_id</p>
</td>
<td class="cellrowborder" valign="top" width="51.25999999999999%" headers="mcps1.2.3.1.2 "><p id="p16221014395"><a name="p16221014395"></a><a name="p16221014395"></a>模型负载ID。</p>
</td>
</tr>
</tbody>
</table>

