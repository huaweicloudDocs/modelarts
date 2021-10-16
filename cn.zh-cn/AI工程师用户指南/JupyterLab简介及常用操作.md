# JupyterLab简介及常用操作<a name="modelarts_30_0009"></a>

JupyterLab是一个交互式的开发环境，是Jupyter Notebook的下一代产品，可以使用它编写Notebook、操作终端、编辑MarkDown文本、打开交互模式、查看csv文件及图片等功能。

可以说，JupyterLab是开发者们下一阶段更主流的开发环境。JupyterLab支持更加灵活和更加强大的项目操作方式，但具有和Jupyter Notebooks一样的组件。

## 打开JupyterLab<a name="section195461127123320"></a>

下面介绍如何从运行中的Notebook实例打开JupyterLab。

1.  登录ModelArts管理控制台，在左侧菜单栏中选择“开发环境 \> Notebook“，进入新版Notebook管理页面。
2.  选择状态为“运行中“的Notebook实例，单击操作列的“打开“，访问JupyterLab。

    **图 1**  打开Notebook实例<a name="fig1896661974915"></a>  
    ![](figures/打开Notebook实例.png "打开Notebook实例")

3.  进入JupyterLab页面后，自动打开Launcher页面，如下图所示。您可以使用开源支持的所有功能，详细操作指导可参见[JupyterLab官网文档](https://jupyterlab.readthedocs.io/en/stable/)。

    **图 2**  JupyterLab主页<a name="fig1727316104710"></a>  
    ![](figures/JupyterLab主页.png "JupyterLab主页")


## 在JupyterLab中新建ipynb文件<a name="section127401521103612"></a>

进入JupyterLab主页后，可在“Notebook“区域下，选择适用的AI引擎，单击后将新建一个对应框架的ipynb文件。

由于每个Notebook实例选择的工作环境不同，其支持的AI框架也不同，下图仅为示例，请根据实际显示界面选择AI框架。

**图 3**  选择AI引擎并新建一个ipynb文件<a name="fig812525717438"></a>  
![](figures/选择AI引擎并新建一个ipynb文件.png "选择AI引擎并新建一个ipynb文件")

新建的ipynb文件将呈现在左侧菜单栏中。

**图 4**  新建文件<a name="fig6910322104612"></a>  
![](figures/新建文件.png "新建文件")

## 新建文件并打开Console<a name="section3737112793710"></a>

Console的本质为Python终端，输入一条语句就会给出相应的输出，类似于Python原生的IDE。

进入JupyterLab主页后，可在“Console“区域下，选择适用的AI引擎，单击后将新建一个对应框架的Notebook文件。

由于每个Notebook实例选择的工作环境不同，其支持的AI框架也不同，下图仅为示例，请根据实际显示界面选择AI框架。

**图 5**  选择AI引擎并新建一个Console<a name="fig146903307496"></a>  
![](figures/选择AI引擎并新建一个Console.png "选择AI引擎并新建一个Console")

文件创建成功后，将直接呈现Console页面。

**图 6**  新建文件（Console）<a name="fig12167335121119"></a>  
![](figures/新建文件（Console）.png "新建文件（Console）")

## 在JupyterLab中编辑文件<a name="section9338612161812"></a>

JupyterLab可以在同一个窗口同时打开几个Notebook或文件（如HTML、TXT、Markdown等），以页签形式展示。

JupyterLab的一大优点是，可以任意排版多个文件。在右侧文件展示区，您可以拖动打开文件，随意调整文件展示位置，可以同时打开多个文件。

**图 7**  多文件任意编排<a name="fig6301121132215"></a>  
![](figures/多文件任意编排.png "多文件任意编排")

当在一个Notebook中写代码时，如果需要实时同步编辑文件并查看执行结果，可以新建该文件的多个视图。

打开此文件，然后单击菜单栏“File \> New View for Notebook“，即可打开多个视图。

**图 8**  同一个文件的多个视图<a name="fig9122203643213"></a>  
![](figures/同一个文件的多个视图.png "同一个文件的多个视图")

## 自动停止及续期<a name="section13676123218445"></a>

在创建或启动Notebook时，如果启用了自动停止功能，则在JupyterLab的右上角会显示当前实例停止的倒计时（剩余时长），在倒计时结束前可以单击剩余时间进行续期。

**图 9**  自动停止<a name="fig177412921616"></a>  
![](figures/自动停止.png "自动停止")

**图 10**  续期<a name="fig1547114331616"></a>  
![](figures/续期.png "续期")

## JupyterLab常用快捷键和插件栏<a name="section95631258134014"></a>

**图 11**  JupyterLab常用快捷键和插件栏<a name="fig18661212194314"></a>  
![](figures/JupyterLab常用快捷键和插件栏.png "JupyterLab常用快捷键和插件栏")

**表 1**  快捷键说明

<a name="table17325391430"></a>
<table><thead align="left"><tr id="row19732163904312"><th class="cellrowborder" valign="top" width="19.689999999999998%" id="mcps1.2.3.1.1"><p id="p1373220396430"><a name="p1373220396430"></a><a name="p1373220396430"></a>快捷键</p>
</th>
<th class="cellrowborder" valign="top" width="80.31%" id="mcps1.2.3.1.2"><p id="p1673273911432"><a name="p1673273911432"></a><a name="p1673273911432"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row17732183912437"><td class="cellrowborder" valign="top" width="19.689999999999998%" headers="mcps1.2.3.1.1 "><p id="p1973223911439"><a name="p1973223911439"></a><a name="p1973223911439"></a><a name="image3259125718470"></a><a name="image3259125718470"></a><span><img id="image3259125718470" src="figures/zh-cn_image_0000001163168521.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80.31%" headers="mcps1.2.3.1.2 "><p id="p1273213394437"><a name="p1273213394437"></a><a name="p1273213394437"></a>打开Launcher页面，可快速创建新的Notebook、Console或其他文件。</p>
</td>
</tr>
<tr id="row1073293944310"><td class="cellrowborder" valign="top" width="19.689999999999998%" headers="mcps1.2.3.1.1 "><p id="p773263934313"><a name="p773263934313"></a><a name="p773263934313"></a><a name="image41441365481"></a><a name="image41441365481"></a><span><img id="image41441365481" src="figures/zh-cn_image_0000001117288648.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80.31%" headers="mcps1.2.3.1.2 "><p id="p473215391435"><a name="p473215391435"></a><a name="p473215391435"></a>创建文件夹。</p>
</td>
</tr>
<tr id="row14732113994310"><td class="cellrowborder" valign="top" width="19.689999999999998%" headers="mcps1.2.3.1.1 "><p id="p147321539104315"><a name="p147321539104315"></a><a name="p147321539104315"></a><a name="image154147144486"></a><a name="image154147144486"></a><span><img id="image154147144486" src="figures/zh-cn_image_0000001117128740.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80.31%" headers="mcps1.2.3.1.2 "><p id="p20732103934313"><a name="p20732103934313"></a><a name="p20732103934313"></a>上传文件。详细说明可参见<a href="从本地上传文件至JupyterLab.md#section172463910383">从本地上传100MB以内的文件到JupyterLab</a>。</p>
</td>
</tr>
<tr id="row373233954317"><td class="cellrowborder" valign="top" width="19.689999999999998%" headers="mcps1.2.3.1.1 "><p id="p1473283954312"><a name="p1473283954312"></a><a name="p1473283954312"></a><a name="image688632424817"></a><a name="image688632424817"></a><span><img id="image688632424817" src="figures/zh-cn_image_0000001163488495.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80.31%" headers="mcps1.2.3.1.2 "><p id="p173263924319"><a name="p173263924319"></a><a name="p173263924319"></a>刷新文件目录。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  插件栏常用插件说明

<a name="table8147032134415"></a>
<table><thead align="left"><tr id="row12147193213442"><th class="cellrowborder" valign="top" width="19.3%" id="mcps1.2.3.1.1"><p id="p414723294416"><a name="p414723294416"></a><a name="p414723294416"></a>插件</p>
</th>
<th class="cellrowborder" valign="top" width="80.7%" id="mcps1.2.3.1.2"><p id="p1114710325444"><a name="p1114710325444"></a><a name="p1114710325444"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row314711326446"><td class="cellrowborder" valign="top" width="19.3%" headers="mcps1.2.3.1.1 "><p id="p15147532154411"><a name="p15147532154411"></a><a name="p15147532154411"></a><a name="image2665205034813"></a><a name="image2665205034813"></a><span><img id="image2665205034813" src="figures/zh-cn_image_0000001117288652.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80.7%" headers="mcps1.2.3.1.2 "><p id="p1914717327448"><a name="p1914717327448"></a><a name="p1914717327448"></a>文件列表。单击此处，将展示此Notebook实例下的所有文件列表。</p>
</td>
</tr>
<tr id="row111471932164413"><td class="cellrowborder" valign="top" width="19.3%" headers="mcps1.2.3.1.1 "><p id="p1914703216446"><a name="p1914703216446"></a><a name="p1914703216446"></a><a name="image12130135374916"></a><a name="image12130135374916"></a><span><img id="image12130135374916" src="figures/zh-cn_image_0000001117128742.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80.7%" headers="mcps1.2.3.1.2 "><p id="p16147173220443"><a name="p16147173220443"></a><a name="p16147173220443"></a>罗列ModelArts Examples。</p>
<p id="p39509162447"><a name="p39509162447"></a><a name="p39509162447"></a>不同Region支持的Examples不一样，请以控制台实际界面为准。</p>
</td>
</tr>
<tr id="row0147173244417"><td class="cellrowborder" valign="top" width="19.3%" headers="mcps1.2.3.1.1 "><p id="p20147203212440"><a name="p20147203212440"></a><a name="p20147203212440"></a><a name="image08241650165011"></a><a name="image08241650165011"></a><span><img id="image08241650165011" src="figures/zh-cn_image_0000001163488497.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80.7%" headers="mcps1.2.3.1.2 "><p id="p7147203214449"><a name="p7147203214449"></a><a name="p7147203214449"></a>当前实例中正在运行的Terminal和Kernel。</p>
</td>
</tr>
<tr id="row1614753224420"><td class="cellrowborder" valign="top" width="19.3%" headers="mcps1.2.3.1.1 "><p id="p8147932174416"><a name="p8147932174416"></a><a name="p8147932174416"></a><a name="image1364725219"></a><a name="image1364725219"></a><span><img id="image1364725219" src="figures/zh-cn_image_0000001117288658.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80.7%" headers="mcps1.2.3.1.2 "><p id="p20147153274414"><a name="p20147153274414"></a><a name="p20147153274414"></a>快速启动命令。</p>
</td>
</tr>
<tr id="row6791122316234"><td class="cellrowborder" valign="top" width="19.3%" headers="mcps1.2.3.1.1 "><p id="p12792182312320"><a name="p12792182312320"></a><a name="p12792182312320"></a><a name="image1199612411233"></a><a name="image1199612411233"></a><span><img id="image1199612411233" src="figures/zh-cn_image_0000001167765029.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80.7%" headers="mcps1.2.3.1.2 "><p id="p1792723132313"><a name="p1792723132313"></a><a name="p1792723132313"></a>属性检查器。</p>
</td>
</tr>
<tr id="row1456581516529"><td class="cellrowborder" valign="top" width="19.3%" headers="mcps1.2.3.1.1 "><p id="p356571525210"><a name="p356571525210"></a><a name="p356571525210"></a><a name="image78687105320"></a><a name="image78687105320"></a><span><img id="image78687105320" src="figures/zh-cn_image_0000001117128750.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80.7%" headers="mcps1.2.3.1.2 "><p id="p45651215165211"><a name="p45651215165211"></a><a name="p45651215165211"></a>查看正在打开的文件页签。</p>
</td>
</tr>
<tr id="row15403154985311"><td class="cellrowborder" valign="top" width="19.3%" headers="mcps1.2.3.1.1 "><p id="p340416497537"><a name="p340416497537"></a><a name="p340416497537"></a><a name="image1526025811539"></a><a name="image1526025811539"></a><span><img id="image1526025811539" src="figures/zh-cn_image_0000001163488501.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80.7%" headers="mcps1.2.3.1.2 "><p id="p1440413494537"><a name="p1440413494537"></a><a name="p1440413494537"></a>文档结构图。</p>
</td>
</tr>
</tbody>
</table>

**图 12**  导航栏按钮<a name="fig6956143785713"></a>  
![](figures/导航栏按钮.png "导航栏按钮")

**表 3**  导航栏按钮介绍

<a name="table8624788586"></a>
<table><thead align="left"><tr id="row4624885583"><th class="cellrowborder" valign="top" width="20.27%" id="mcps1.2.3.1.1"><p id="p10624208195810"><a name="p10624208195810"></a><a name="p10624208195810"></a>按钮</p>
</th>
<th class="cellrowborder" valign="top" width="79.73%" id="mcps1.2.3.1.2"><p id="p1362417835819"><a name="p1362417835819"></a><a name="p1362417835819"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row166249815817"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p462415835812"><a name="p462415835812"></a><a name="p462415835812"></a>File</p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p2062411815816"><a name="p2062411815816"></a><a name="p2062411815816"></a>新建、关闭、保存、重新加载、、重命名、导出、打印Notebook等功能。</p>
</td>
</tr>
<tr id="row862416813588"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p15624208205815"><a name="p15624208205815"></a><a name="p15624208205815"></a>Edit</p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p762468115815"><a name="p762468115815"></a><a name="p762468115815"></a>编辑ipynb文件中代码块的相关操作，包括撤销、重做、剪切、复制、粘贴、选择、移动、合并、清除、查找代码块等。</p>
</td>
</tr>
<tr id="row562417815585"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p156240810583"><a name="p156240810583"></a><a name="p156240810583"></a>View</p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p1827352814412"><a name="p1827352814412"></a><a name="p1827352814412"></a>查看视图相关操作。</p>
</td>
</tr>
<tr id="row1262414815580"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p1062478125819"><a name="p1062478125819"></a><a name="p1062478125819"></a>Run</p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p166249835811"><a name="p166249835811"></a><a name="p166249835811"></a>运行代码块相关操作，例如：运行选中代码块、一键运行所有代码块等。</p>
</td>
</tr>
<tr id="row1262414815816"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p46240845818"><a name="p46240845818"></a><a name="p46240845818"></a>Kernel</p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p146241980582"><a name="p146241980582"></a><a name="p146241980582"></a>中断、重启、关闭、改变Kernel相关操作。</p>
</td>
</tr>
<tr id="row26249811588"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p196241683586"><a name="p196241683586"></a><a name="p196241683586"></a>Tabs</p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p26246811584"><a name="p26246811584"></a><a name="p26246811584"></a>同时打开多个ipynb文件时，通过Tabs激活或选择文件。</p>
</td>
</tr>
<tr id="row362413895816"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p6625198135815"><a name="p6625198135815"></a><a name="p6625198135815"></a>Settings</p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p206259835816"><a name="p206259835816"></a><a name="p206259835816"></a>JupyterLab工具系统设置。</p>
</td>
</tr>
<tr id="row13625188145814"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p206259805817"><a name="p206259805817"></a><a name="p206259805817"></a>Help</p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p116252875819"><a name="p116252875819"></a><a name="p116252875819"></a>JupyterLab工具自带的帮助参考。</p>
</td>
</tr>
</tbody>
</table>

**图 13**  ipynb文件菜单栏中的快捷键<a name="fig13260173222416"></a>  
![](figures/ipynb文件菜单栏中的快捷键.png "ipynb文件菜单栏中的快捷键")

**表 4**  ipynb文件菜单栏中的快捷键

<a name="table1498446172514"></a>
<table><thead align="left"><tr id="row199849672516"><th class="cellrowborder" valign="top" width="20.27%" id="mcps1.2.3.1.1"><p id="p19845610253"><a name="p19845610253"></a><a name="p19845610253"></a>快捷键</p>
</th>
<th class="cellrowborder" valign="top" width="79.73%" id="mcps1.2.3.1.2"><p id="p698410610255"><a name="p698410610255"></a><a name="p698410610255"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row898412618254"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p698456202514"><a name="p698456202514"></a><a name="p698456202514"></a><a name="image698194662920"></a><a name="image698194662920"></a><span><img id="image698194662920" src="figures/zh-cn_image_0000001177376713.png" width="22.942500000000003" height="24.707276999999998"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p6984136162516"><a name="p6984136162516"></a><a name="p6984136162516"></a>保存文件</p>
</td>
</tr>
<tr id="row1698456172513"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p298412617255"><a name="p298412617255"></a><a name="p298412617255"></a><a name="image142546546292"></a><a name="image142546546292"></a><span><img id="image142546546292" src="figures/zh-cn_image_0000001177376715.png" width="20.9475" height="21.723289"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p159843602518"><a name="p159843602518"></a><a name="p159843602518"></a>添加新代码块</p>
</td>
</tr>
<tr id="row6984156142512"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p119846616257"><a name="p119846616257"></a><a name="p119846616257"></a><a name="image356216310306"></a><a name="image356216310306"></a><span><img id="image356216310306" src="figures/zh-cn_image_0000001131297310.png" width="27.93" height="20.381319"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p7984961255"><a name="p7984961255"></a><a name="p7984961255"></a>剪切选中的代码块</p>
</td>
</tr>
<tr id="row179841865254"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p109840612253"><a name="p109840612253"></a><a name="p109840612253"></a><a name="image155527128307"></a><a name="image155527128307"></a><span><img id="image155527128307" src="figures/zh-cn_image_0000001131297314.png" width="29.925" height="25.76875"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p119847613250"><a name="p119847613250"></a><a name="p119847613250"></a>复制选中的代码块</p>
</td>
</tr>
<tr id="row3984163251"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p598420662511"><a name="p598420662511"></a><a name="p598420662511"></a><a name="image44985202305"></a><a name="image44985202305"></a><span><img id="image44985202305" src="figures/zh-cn_image_0000001177376747.png" width="28.927500000000002" height="27.174294"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p298417692519"><a name="p298417692519"></a><a name="p298417692519"></a>粘贴选中的代码块</p>
</td>
</tr>
<tr id="row1498476192519"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p189841668256"><a name="p189841668256"></a><a name="p189841668256"></a><a name="image08620329304"></a><a name="image08620329304"></a><span><img id="image08620329304" src="figures/zh-cn_image_0000001177376749.png" width="25.935000000000002" height="22.477"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p298486172513"><a name="p298486172513"></a><a name="p298486172513"></a>执行选中的代码块</p>
</td>
</tr>
<tr id="row159846672516"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p16984365258"><a name="p16984365258"></a><a name="p16984365258"></a><a name="image172684018307"></a><a name="image172684018307"></a><span><img id="image172684018307" src="figures/zh-cn_image_0000001177456835.png" width="22.942500000000003" height="24.524801"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p1098412682517"><a name="p1098412682517"></a><a name="p1098412682517"></a>终止kernel</p>
</td>
</tr>
<tr id="row17124149102719"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p1124139182717"><a name="p1124139182717"></a><a name="p1124139182717"></a><a name="image1981419480307"></a><a name="image1981419480307"></a><span><img id="image1981419480307" src="figures/zh-cn_image_0000001177376755.png" width="21.945" height="21.161231"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p512420912711"><a name="p512420912711"></a><a name="p512420912711"></a>重启kernel</p>
</td>
</tr>
<tr id="row37842112277"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p1278481115271"><a name="p1278481115271"></a><a name="p1278481115271"></a><a name="image1566430163112"></a><a name="image1566430163112"></a><span><img id="image1566430163112" src="figures/zh-cn_image_0000001177376757.png" width="74.8125" height="18.389777000000002"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p65751921193512"><a name="p65751921193512"></a><a name="p65751921193512"></a>此处下拉框有4个选项，分别是：</p>
<p id="p169120243355"><a name="p169120243355"></a><a name="p169120243355"></a>Code（写python代码），Markdown（写Markdown代码，通常用于注释），Raw（一个转换工具），-（不修改）</p>
</td>
</tr>
<tr id="row15631915172713"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p76420154272"><a name="p76420154272"></a><a name="p76420154272"></a><a name="image124638811312"></a><a name="image124638811312"></a><span><img id="image124638811312" src="figures/zh-cn_image_0000001131297338.png" width="27.93" height="23.275000000000002"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p1641215202717"><a name="p1641215202717"></a><a name="p1641215202717"></a>查看代码历史版本</p>
</td>
</tr>
<tr id="row526416171273"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p1526471710279"><a name="p1526471710279"></a><a name="p1526471710279"></a><a name="image1022219179312"></a><a name="image1022219179312"></a><span><img id="image1022219179312" src="figures/zh-cn_image_0000001131457118.png" width="29.925" height="21.837137000000002"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p526413173278"><a name="p526413173278"></a><a name="p526413173278"></a>git插件，图标显示灰色表示当前Region不支持。</p>
</td>
</tr>
<tr id="row743215191274"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p1843241922715"><a name="p1843241922715"></a><a name="p1843241922715"></a><a name="image113603242312"></a><a name="image113603242312"></a><span><img id="image113603242312" src="figures/zh-cn_image_0000001131457120.png" width="86.7825" height="16.986095"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p643221918277"><a name="p643221918277"></a><a name="p643221918277"></a>当前的资源规格</p>
</td>
</tr>
<tr id="row10845132714314"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p584519278318"><a name="p584519278318"></a><a name="p584519278318"></a><a name="image10815941163112"></a><a name="image10815941163112"></a><span><img id="image10815941163112" src="figures/zh-cn_image_0000001131297352.png" width="66.83250000000001" height="16.387861"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p108451827183115"><a name="p108451827183115"></a><a name="p108451827183115"></a>单击可以选择Kernel</p>
</td>
</tr>
<tr id="row640915331311"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p84091633153119"><a name="p84091633153119"></a><a name="p84091633153119"></a><a name="image111182518316"></a><a name="image111182518316"></a><span><img id="image111182518316" src="figures/zh-cn_image_0000001177456981.png" width="18.9525" height="20.33437"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p2409333183117"><a name="p2409333183117"></a><a name="p2409333183117"></a>表示代码运行状态，变为实心圆<a name="image938861818416"></a><a name="image938861818416"></a><span><img id="image938861818416" src="figures/zh-cn_image_0000001131457520.png" width="16.9575" height="18.499103"></span>时，表示代码在运行中。</p>
</td>
</tr>
<tr id="row162011130123113"><td class="cellrowborder" valign="top" width="20.27%" headers="mcps1.2.3.1.1 "><p id="p1420112303311"><a name="p1420112303311"></a><a name="p1420112303311"></a><a name="image1392181103213"></a><a name="image1392181103213"></a><span><img id="image1392181103213" src="figures/zh-cn_image_0000001131297502.png" width="14.9625" height="15.515115"></span></p>
</td>
<td class="cellrowborder" valign="top" width="79.73%" headers="mcps1.2.3.1.2 "><p id="p14201133003118"><a name="p14201133003118"></a><a name="p14201133003118"></a>分享到AI Gallery</p>
</td>
</tr>
</tbody>
</table>

## 资源监控<a name="section1810623016320"></a>

在使用过程中，如果想了解资源使用情况，可在右侧区域选择“Resource Monitor”，展示“CPU使用率”和“内存使用率”。

**图 14**  资源监控<a name="fig202283556553"></a>  
![](figures/资源监控-24.png "资源监控-24")

