# API概览<a name="modelarts_03_0002"></a>

ModelArts服务所提供的接口均为自研接口。

通过ModelArts服务自研接口，您可以使用ModelArts数据集管理、训练管理、模型管理及服务管理功能。

## 数据管理接口<a name="section129120417301"></a>

数据管理接口包括数据集管理、数据集版本管理、样本管理、标签管理等，通过这些接口可以创建数据集并完成数据标注，具体接口信息请参见[数据管理接口概述](数据管理接口概述.md)。

## 开发环境接口<a name="section458310261398"></a>

**表 1**  开发环境接口

<a name="table6223102719106"></a>
<table><thead align="left"><tr id="row92301279102"><th class="cellrowborder" valign="top" width="36%" id="mcps1.2.3.1.1"><p id="p1023211273101"><a name="p1023211273101"></a><a name="p1023211273101"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="64%" id="mcps1.2.3.1.2"><p id="p18234227181015"><a name="p18234227181015"></a><a name="p18234227181015"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row182432275105"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p1146711962218"><a name="p1146711962218"></a><a name="p1146711962218"></a><a href="创建开发环境实例.md">创建开发环境实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p19248122710105"><a name="p19248122710105"></a><a name="p19248122710105"></a>创建开发环境实例，用于代码开发。</p>
</td>
</tr>
<tr id="row524902701014"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p127431839102211"><a name="p127431839102211"></a><a name="p127431839102211"></a><a href="查询开发环境实例列表.md">查询开发环境实例列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p12572272109"><a name="p12572272109"></a><a name="p12572272109"></a>查询开发环境实例列表，用户可按需查询满足条件的开发环境实例列表。</p>
</td>
</tr>
<tr id="row122571227151017"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p16956125542217"><a name="p16956125542217"></a><a name="p16956125542217"></a><a href="查询开发环境实例详情.md">查询开发环境实例详情</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p122651627151014"><a name="p122651627151014"></a><a name="p122651627151014"></a>查询开发环境实例详情。</p>
</td>
</tr>
<tr id="row1726672714102"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p1620411715236"><a name="p1620411715236"></a><a name="p1620411715236"></a><a href="更新开发环境实例信息.md">更新开发环境实例信息</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p1427272718101"><a name="p1427272718101"></a><a name="p1427272718101"></a>更新开发环境实例的描述信息。</p>
</td>
</tr>
<tr id="row12731327181012"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p118651118182310"><a name="p118651118182310"></a><a name="p118651118182310"></a><a href="删除开发环境实例.md">删除开发环境实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p52796273103"><a name="p52796273103"></a><a name="p52796273103"></a>删除开发环境实例。</p>
</td>
</tr>
<tr id="row52792027141013"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p13280122717101"><a name="p13280122717101"></a><a name="p13280122717101"></a><a href="管理开发环境实例.md">管理开发环境实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p10283162712101"><a name="p10283162712101"></a><a name="p10283162712101"></a>启动和停止开发环境实例。</p>
</td>
</tr>
</tbody>
</table>

## 训练管理接口<a name="section10117106134014"></a>

**表 2**  训练管理接口

<a name="table19560011132619"></a>
<table><thead align="left"><tr id="row1056021113264"><th class="cellrowborder" valign="top" width="19.98%" id="mcps1.2.4.1.1"><p id="p121931935228"><a name="p121931935228"></a><a name="p121931935228"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="33.900000000000006%" id="mcps1.2.4.1.2"><p id="p4560171162619"><a name="p4560171162619"></a><a name="p4560171162619"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="46.12%" id="mcps1.2.4.1.3"><p id="p1056091114268"><a name="p1056091114268"></a><a name="p1056091114268"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row963865810585"><td class="cellrowborder" rowspan="12" valign="top" width="19.98%" headers="mcps1.2.4.1.1 "><p id="p5193113516218"><a name="p5193113516218"></a><a name="p5193113516218"></a>训练作业</p>
</td>
<td class="cellrowborder" valign="top" width="33.900000000000006%" headers="mcps1.2.4.1.2 "><p id="p1146764014010"><a name="p1146764014010"></a><a name="p1146764014010"></a><a href="创建训练作业.md">创建训练作业</a></p>
</td>
<td class="cellrowborder" valign="top" width="46.12%" headers="mcps1.2.4.1.3 "><p id="p66388587586"><a name="p66388587586"></a><a name="p66388587586"></a>创建一个训练作业。</p>
</td>
</tr>
<tr id="row363895855813"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p563895816583"><a name="p563895816583"></a><a name="p563895816583"></a><a href="查询训练作业列表.md">查询训练作业列表</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p16387585588"><a name="p16387585588"></a><a name="p16387585588"></a>根据指定条件查询用户创建的训练作业。</p>
</td>
</tr>
<tr id="row26381058165819"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p46388585585"><a name="p46388585585"></a><a name="p46388585585"></a><a href="查询训练作业版本详情.md">查询训练作业版本详情</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p17639258135817"><a name="p17639258135817"></a><a name="p17639258135817"></a>根据作业ID查看指定的训练作业详情。</p>
</td>
</tr>
<tr id="row1963995865813"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1787313411011"><a name="p1787313411011"></a><a name="p1787313411011"></a><a href="删除训练作业版本.md">删除训练作业版本</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p26391258105819"><a name="p26391258105819"></a><a name="p26391258105819"></a>删除训练作业一个版本。</p>
</td>
</tr>
<tr id="row136391358135811"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p176850438011"><a name="p176850438011"></a><a name="p176850438011"></a><a href="查询训练作业版本列表.md">查询训练作业版本列表</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1463945815586"><a name="p1463945815586"></a><a name="p1463945815586"></a>根据作业ID查看指定的训练作业版本。</p>
</td>
</tr>
<tr id="row176397586589"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1639158175811"><a name="p1639158175811"></a><a name="p1639158175811"></a><a href="创建训练作业版本.md">创建训练作业版本</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1963925815820"><a name="p1963925815820"></a><a name="p1963925815820"></a>创建一个训练作业版本。</p>
</td>
</tr>
<tr id="row663918584588"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p567016449014"><a name="p567016449014"></a><a name="p567016449014"></a><a href="停止训练作业版本.md">停止训练作业版本</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1864015584589"><a name="p1864015584589"></a><a name="p1864015584589"></a>停止训练作业。</p>
</td>
</tr>
<tr id="row1264045855811"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p949654516016"><a name="p949654516016"></a><a name="p949654516016"></a><a href="更新训练作业描述.md">更新训练作业描述</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p864016588587"><a name="p864016588587"></a><a name="p864016588587"></a>更新训练作业的描述。</p>
</td>
</tr>
<tr id="row1164095845811"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p134181646302"><a name="p134181646302"></a><a name="p134181646302"></a><a href="删除训练作业.md">删除训练作业</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p10640195813581"><a name="p10640195813581"></a><a name="p10640195813581"></a>删除训练作业。</p>
</td>
</tr>
<tr id="row2640175895818"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1446884716015"><a name="p1446884716015"></a><a name="p1446884716015"></a><a href="获取训练作业日志的文件名.md">获取训练作业日志的文件名</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1364015815817"><a name="p1364015815817"></a><a name="p1364015815817"></a>获取训练作业日志的文件名。</p>
</td>
</tr>
<tr id="row1451231121817"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p652173151816"><a name="p652173151816"></a><a name="p652173151816"></a><a href="查询预置算法.md">查询预置算法</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p8531031101816"><a name="p8531031101816"></a><a name="p8531031101816"></a>查看预置模型的详情。</p>
</td>
</tr>
<tr id="row9990164191713"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p10991154112178"><a name="p10991154112178"></a><a name="p10991154112178"></a><a href="查询训练作业日志.md">查询训练作业日志</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p3991341121718"><a name="p3991341121718"></a><a name="p3991341121718"></a>按行来查询训练作业日志详细信息。</p>
</td>
</tr>
<tr id="row16594454155813"><td class="cellrowborder" rowspan="5" valign="top" width="19.98%" headers="mcps1.2.4.1.1 "><p id="p6194193515219"><a name="p6194193515219"></a><a name="p6194193515219"></a>训练作业参数配置</p>
</td>
<td class="cellrowborder" valign="top" width="33.900000000000006%" headers="mcps1.2.4.1.2 "><p id="p23448301418"><a name="p23448301418"></a><a name="p23448301418"></a><a href="创建训练作业参数.md">创建训练作业参数</a></p>
</td>
<td class="cellrowborder" valign="top" width="46.12%" headers="mcps1.2.4.1.3 "><p id="p6595654125812"><a name="p6595654125812"></a><a name="p6595654125812"></a>创建训练作业参数。</p>
</td>
</tr>
<tr id="row16595165475812"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p51763214115"><a name="p51763214115"></a><a name="p51763214115"></a><a href="查询训练作业参数列表.md">查询训练作业参数列表</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p14595554175811"><a name="p14595554175811"></a><a name="p14595554175811"></a>根据指定条件查询用户创建的训练作业参数。</p>
</td>
</tr>
<tr id="row95951054125819"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p10887133213120"><a name="p10887133213120"></a><a name="p10887133213120"></a><a href="更新训练作业参数.md">更新训练作业参数</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p55951754115817"><a name="p55951754115817"></a><a name="p55951754115817"></a>更新训练作业参数。</p>
</td>
</tr>
<tr id="row1595145414588"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p205969545588"><a name="p205969545588"></a><a name="p205969545588"></a><a href="删除训练作业参数.md">删除训练作业参数</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p759625419583"><a name="p759625419583"></a><a name="p759625419583"></a>删除训练作业参数。</p>
</td>
</tr>
<tr id="row5596125411582"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1596254155820"><a name="p1596254155820"></a><a name="p1596254155820"></a><a href="查询训练作业参数详情.md">查询训练作业参数详情</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p22623770"><a name="p22623770"></a><a name="p22623770"></a>查看指定的训练作业参数详情。</p>
</td>
</tr>
<tr id="row6596205485815"><td class="cellrowborder" rowspan="7" valign="top" width="19.98%" headers="mcps1.2.4.1.1 "><p id="p3194835221"><a name="p3194835221"></a><a name="p3194835221"></a>可视化作业管理</p>
</td>
<td class="cellrowborder" valign="top" width="33.900000000000006%" headers="mcps1.2.4.1.2 "><p id="p178513354216"><a name="p178513354216"></a><a name="p178513354216"></a><a href="创建可视化作业.md">创建可视化作业</a></p>
</td>
<td class="cellrowborder" valign="top" width="46.12%" headers="mcps1.2.4.1.3 "><p id="p1596155413589"><a name="p1596155413589"></a><a name="p1596155413589"></a>创建可视化作业。</p>
</td>
</tr>
<tr id="row16596145475818"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p559635455817"><a name="p559635455817"></a><a name="p559635455817"></a><a href="查询可视化作业列表.md">查询可视化作业列表</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p11597175445818"><a name="p11597175445818"></a><a name="p11597175445818"></a>根据指定条件查询用户创建的可视化作业列表。</p>
</td>
</tr>
<tr id="row6597115418589"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p12171734126"><a name="p12171734126"></a><a name="p12171734126"></a><a href="查询可视化作业详情.md">查询可视化作业详情</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p19597165417585"><a name="p19597165417585"></a><a name="p19597165417585"></a>根据作业名称查看指定的可视化作业详情。</p>
</td>
</tr>
<tr id="row13698145017586"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p18841633828"><a name="p18841633828"></a><a name="p18841633828"></a><a href="更新可视化作业描述.md">更新可视化作业描述</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p12698165017581"><a name="p12698165017581"></a><a name="p12698165017581"></a>更新可视化作业的描述。</p>
</td>
</tr>
<tr id="row156981150145820"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p203338321125"><a name="p203338321125"></a><a name="p203338321125"></a><a href="删除可视化作业.md">删除可视化作业</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p269865085817"><a name="p269865085817"></a><a name="p269865085817"></a>删除可视化作业。</p>
</td>
</tr>
<tr id="row369817506585"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p11541103117211"><a name="p11541103117211"></a><a name="p11541103117211"></a><a href="停止可视化作业.md">停止可视化作业</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p96981850145817"><a name="p96981850145817"></a><a name="p96981850145817"></a>停止可视化作业。</p>
</td>
</tr>
<tr id="row1569895035811"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p680511301429"><a name="p680511301429"></a><a name="p680511301429"></a><a href="重启可视化作业.md">重启可视化作业</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1069995085814"><a name="p1069995085814"></a><a name="p1069995085814"></a>重启可视化作业。</p>
</td>
</tr>
<tr id="row37149384587"><td class="cellrowborder" rowspan="2" valign="top" width="19.98%" headers="mcps1.2.4.1.1 "><p id="p12194235827"><a name="p12194235827"></a><a name="p12194235827"></a>资源和引擎规格接口</p>
</td>
<td class="cellrowborder" valign="top" width="33.900000000000006%" headers="mcps1.2.4.1.2 "><p id="p189731729329"><a name="p189731729329"></a><a name="p189731729329"></a><a href="查询作业资源规格.md">查询作业资源规格</a></p>
</td>
<td class="cellrowborder" valign="top" width="46.12%" headers="mcps1.2.4.1.3 "><p id="p11626845133420"><a name="p11626845133420"></a><a name="p11626845133420"></a>查看指定作业类型的资源规格。</p>
</td>
</tr>
<tr id="row18961174017588"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p96671928827"><a name="p96671928827"></a><a name="p96671928827"></a><a href="查询作业引擎规格.md">查询作业引擎规格</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p17961540145810"><a name="p17961540145810"></a><a name="p17961540145810"></a>查看指定作业的引擎类型和版本。</p>
</td>
</tr>
<tr id="row8297114517811"><td class="cellrowborder" valign="top" width="19.98%" headers="mcps1.2.4.1.1 "><p id="p10297194512810"><a name="p10297194512810"></a><a name="p10297194512810"></a>作业状态参考</p>
</td>
<td class="cellrowborder" valign="top" width="33.900000000000006%" headers="mcps1.2.4.1.2 "><p id="p202978451482"><a name="p202978451482"></a><a name="p202978451482"></a><a href="作业状态参考.md">作业状态参考</a></p>
</td>
<td class="cellrowborder" valign="top" width="46.12%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0105159288_p10118881153428"><a name="zh-cn_topic_0105159288_p10118881153428"></a><a name="zh-cn_topic_0105159288_p10118881153428"></a>查看作业状态值和作业状态说明。</p>
</td>
</tr>
</tbody>
</table>

## 模型管理接口<a name="section20428135064013"></a>

**表 3**  模型管理接口

<a name="table172059163715"></a>
<table><thead align="left"><tr id="row1972011913377"><th class="cellrowborder" valign="top" width="36%" id="mcps1.2.3.1.1"><p id="p117201799375"><a name="p117201799375"></a><a name="p117201799375"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="64%" id="mcps1.2.3.1.2"><p id="p1672069153713"><a name="p1672069153713"></a><a name="p1672069153713"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row19907174375513"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p455311107569"><a name="p455311107569"></a><a name="p455311107569"></a><a href="导入模型.md">导入模型</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p5907443165510"><a name="p5907443165510"></a><a name="p5907443165510"></a>导入模型。</p>
</td>
</tr>
<tr id="row1217174611553"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p1221717465559"><a name="p1221717465559"></a><a name="p1221717465559"></a><a href="查询模型列表.md">查询模型列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p49947236445"><a name="p49947236445"></a><a name="p49947236445"></a>查询模型列表，可以根据不同的检索参数进行查询。</p>
</td>
</tr>
<tr id="row3829164717557"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p1725381215567"><a name="p1725381215567"></a><a name="p1725381215567"></a><a href="查询模型详情.md">查询模型详情</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p5829947145514"><a name="p5829947145514"></a><a name="p5829947145514"></a>查询模型详情，根据模型ID查询模型的详细信息。</p>
</td>
</tr>
<tr id="row837710497557"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p1238751335611"><a name="p1238751335611"></a><a name="p1238751335611"></a><a href="删除模型.md">删除模型</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p11378134965511"><a name="p11378134965511"></a><a name="p11378134965511"></a>删除模型，根据模型ID删除指定模型，可以级联删除该模型下的所有版本。</p>
</td>
</tr>
</tbody>
</table>

## 服务管理接口<a name="section82616461414"></a>

**表 4**  服务管理接口

<a name="table17144179535"></a>
<table><thead align="left"><tr id="row15144107125316"><th class="cellrowborder" valign="top" width="36.08%" id="mcps1.2.3.1.1"><p id="p714477115312"><a name="p714477115312"></a><a name="p714477115312"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="63.92%" id="mcps1.2.3.1.2"><p id="p13409122965316"><a name="p13409122965316"></a><a name="p13409122965316"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row14144479535"><td class="cellrowborder" valign="top" width="36.08%" headers="mcps1.2.3.1.1 "><p id="p1987110523516"><a name="p1987110523516"></a><a name="p1987110523516"></a><a href="部署服务.md">部署服务</a></p>
</td>
<td class="cellrowborder" valign="top" width="63.92%" headers="mcps1.2.3.1.2 "><p id="p1687116521510"><a name="p1687116521510"></a><a name="p1687116521510"></a>部署模型服务。</p>
</td>
</tr>
<tr id="row814417755316"><td class="cellrowborder" valign="top" width="36.08%" headers="mcps1.2.3.1.1 "><p id="p191441075538"><a name="p191441075538"></a><a name="p191441075538"></a><a href="查询服务列表.md">查询服务列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="63.92%" headers="mcps1.2.3.1.2 "><p id="p15144276534"><a name="p15144276534"></a><a name="p15144276534"></a>查询模型服务列表。</p>
</td>
</tr>
<tr id="row1814407155317"><td class="cellrowborder" valign="top" width="36.08%" headers="mcps1.2.3.1.1 "><p id="p1414417735314"><a name="p1414417735314"></a><a name="p1414417735314"></a><a href="查询服务详情.md">查询服务详情</a></p>
</td>
<td class="cellrowborder" valign="top" width="63.92%" headers="mcps1.2.3.1.2 "><p id="p1144573534"><a name="p1144573534"></a><a name="p1144573534"></a>查询模型服务详情，根据服务ID查询服务详情。</p>
</td>
</tr>
<tr id="row21441176533"><td class="cellrowborder" valign="top" width="36.08%" headers="mcps1.2.3.1.1 "><p id="p314416735316"><a name="p314416735316"></a><a name="p314416735316"></a><a href="启动停止边缘节点服务实例.md">启动停止边缘节点服务实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="63.92%" headers="mcps1.2.3.1.2 "><p id="p161443713531"><a name="p161443713531"></a><a name="p161443713531"></a>启动停止边缘节点服务实例。</p>
</td>
</tr>
<tr id="row41444711534"><td class="cellrowborder" valign="top" width="36.08%" headers="mcps1.2.3.1.1 "><p id="p7144187195311"><a name="p7144187195311"></a><a name="p7144187195311"></a><a href="更新服务配置.md">更新服务配置</a></p>
</td>
<td class="cellrowborder" valign="top" width="63.92%" headers="mcps1.2.3.1.2 "><p id="p181441677531"><a name="p181441677531"></a><a name="p181441677531"></a>更新模型服务。</p>
</td>
</tr>
<tr id="row13144127115310"><td class="cellrowborder" valign="top" width="36.08%" headers="mcps1.2.3.1.1 "><p id="p16144117185310"><a name="p16144117185310"></a><a name="p16144117185310"></a><a href="查询服务监控信息.md">查询服务监控信息</a></p>
</td>
<td class="cellrowborder" valign="top" width="63.92%" headers="mcps1.2.3.1.2 "><p id="p11144157105314"><a name="p11144157105314"></a><a name="p11144157105314"></a>查询服务监控信息。</p>
</td>
</tr>
<tr id="row97411651135313"><td class="cellrowborder" valign="top" width="36.08%" headers="mcps1.2.3.1.1 "><p id="p374185114534"><a name="p374185114534"></a><a name="p374185114534"></a><a href="查询服务更新日志.md">查询服务更新日志</a></p>
</td>
<td class="cellrowborder" valign="top" width="63.92%" headers="mcps1.2.3.1.2 "><p id="p33591545993"><a name="p33591545993"></a><a name="p33591545993"></a>查询实时服务更新日志。</p>
</td>
</tr>
<tr id="row54947181924"><td class="cellrowborder" valign="top" width="36.08%" headers="mcps1.2.3.1.1 "><p id="p124956181215"><a name="p124956181215"></a><a name="p124956181215"></a><a href="查询服务事件日志.md">查询服务事件日志</a></p>
</td>
<td class="cellrowborder" valign="top" width="63.92%" headers="mcps1.2.3.1.2 "><p id="p149516181226"><a name="p149516181226"></a><a name="p149516181226"></a>查询服务事件日志，包含服务的操作记录及部署过程中的关键动作、部署失败原因。</p>
</td>
</tr>
<tr id="row97419511536"><td class="cellrowborder" valign="top" width="36.08%" headers="mcps1.2.3.1.1 "><p id="p10741125113538"><a name="p10741125113538"></a><a name="p10741125113538"></a><a href="删除服务.md">删除服务</a></p>
</td>
<td class="cellrowborder" valign="top" width="63.92%" headers="mcps1.2.3.1.2 "><p id="p77411051135311"><a name="p77411051135311"></a><a name="p77411051135311"></a>删除模型服务。</p>
</td>
</tr>
<tr id="row16922152111215"><td class="cellrowborder" valign="top" width="36.08%" headers="mcps1.2.3.1.1 "><p id="p8922192111210"><a name="p8922192111210"></a><a name="p8922192111210"></a><a href="查询支持的服务部署规格.md">查询支持的服务部署规格</a></p>
</td>
<td class="cellrowborder" valign="top" width="63.92%" headers="mcps1.2.3.1.2 "><p id="p692217211521"><a name="p692217211521"></a><a name="p692217211521"></a>查询支持的服务部署规格列表。</p>
</td>
</tr>
<tr id="row7366174619212"><td class="cellrowborder" valign="top" width="36.08%" headers="mcps1.2.3.1.1 "><p id="p1290541321"><a name="p1290541321"></a><a name="p1290541321"></a><a href="查询专属资源池列表.md">查询专属资源池列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="63.92%" headers="mcps1.2.3.1.2 "><p id="p8755183115114"><a name="p8755183115114"></a><a name="p8755183115114"></a>查询专属资源池列表。</p>
</td>
</tr>
</tbody>
</table>

## 授权管理接口<a name="section20853132693312"></a>

**表 5**  工作空间管理接口

<a name="table19853112615335"></a>
<table><thead align="left"><tr id="row18531026193319"><th class="cellrowborder" valign="top" width="36%" id="mcps1.2.3.1.1"><p id="p5853226203311"><a name="p5853226203311"></a><a name="p5853226203311"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="64%" id="mcps1.2.3.1.2"><p id="p10853182683316"><a name="p10853182683316"></a><a name="p10853182683316"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1085392693310"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p1585312263332"><a name="p1585312263332"></a><a name="p1585312263332"></a><a href="查看授权列表.md">查看授权列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p674120349347"><a name="p674120349347"></a><a name="p674120349347"></a>查看授权列表。</p>
</td>
</tr>
<tr id="row085482663316"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p1854102612337"><a name="p1854102612337"></a><a name="p1854102612337"></a><a href="配置授权.md">配置授权</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p147404345341"><a name="p147404345341"></a><a name="p147404345341"></a>配置ModelArts授权。若没有授权，ModelArts训练管理、开发环境、数据管理、在线服务等功能将不能正常使用。</p>
</td>
</tr>
<tr id="row178541626143311"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p285402613310"><a name="p285402613310"></a><a name="p285402613310"></a><a href="删除授权.md">删除授权</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p11248121416224"><a name="p11248121416224"></a><a name="p11248121416224"></a>删除指定用户的授权或者删除全量用户的授权。</p>
</td>
</tr>
<tr id="row085414266335"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p12854192613333"><a name="p12854192613333"></a><a name="p12854192613333"></a><a href="创建ModelArts委托.md">创建ModelArts委托</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p3444131442217"><a name="p3444131442217"></a><a name="p3444131442217"></a>创建包含OBS、SWR、IEF等依赖服务的ModelArts委托。</p>
</td>
</tr>
</tbody>
</table>

## 工作空间管理接口<a name="section07661718174211"></a>

**表 6**  工作空间管理接口

<a name="table1931210311171"></a>
<table><thead align="left"><tr id="row1731214313176"><th class="cellrowborder" valign="top" width="36%" id="mcps1.2.3.1.1"><p id="p15766151910249"><a name="p15766151910249"></a><a name="p15766151910249"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="64%" id="mcps1.2.3.1.2"><p id="p976641912243"><a name="p976641912243"></a><a name="p976641912243"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row75613415246"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p15312132176"><a name="p15312132176"></a><a name="p15312132176"></a><a href="查询工作空间列表.md">查询工作空间列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p6211419"><a name="p6211419"></a><a name="p6211419"></a>查询工作空间列表，响应消息体中包含详细信息。</p>
</td>
</tr>
<tr id="row4469143215317"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p497613371531"><a name="p497613371531"></a><a name="p497613371531"></a><a href="创建工作空间.md">创建工作空间</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p1976337205313"><a name="p1976337205313"></a><a name="p1976337205313"></a>创建工作空间。</p>
</td>
</tr>
<tr id="row14982517135420"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p1020092845419"><a name="p1020092845419"></a><a name="p1020092845419"></a><a href="查询工作空间详情.md">查询工作空间详情</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p19200142813546"><a name="p19200142813546"></a><a name="p19200142813546"></a>查询工作空间详情。</p>
</td>
</tr>
<tr id="row1531217317175"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p1031216331710"><a name="p1031216331710"></a><a name="p1031216331710"></a><a href="修改工作空间.md">修改工作空间</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p231219321711"><a name="p231219321711"></a><a name="p231219321711"></a>修改工作空间。</p>
</td>
</tr>
<tr id="row1465152114554"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p2623142955516"><a name="p2623142955516"></a><a name="p2623142955516"></a><a href="删除工作空间.md">删除工作空间</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p13623132913554"><a name="p13623132913554"></a><a name="p13623132913554"></a>删除工作空间。</p>
</td>
</tr>
<tr id="row3756715205112"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p167567153514"><a name="p167567153514"></a><a name="p167567153514"></a><a href="查询工作空间配额.md">查询工作空间配额</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p1375771515110"><a name="p1375771515110"></a><a name="p1375771515110"></a>查看工作空间配额。</p>
</td>
</tr>
<tr id="row48743203516"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p1587410201517"><a name="p1587410201517"></a><a name="p1587410201517"></a><a href="修改工作空间配额.md">修改工作空间配额</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p16874152035118"><a name="p16874152035118"></a><a name="p16874152035118"></a>修改工作空间配额。</p>
</td>
</tr>
</tbody>
</table>

