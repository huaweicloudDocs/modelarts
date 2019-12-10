# 创建并打开Notebook<a name="modelarts_23_0034"></a>

在开始进行模型开发前，您需要创建Notebook，并打开Notebook进行编码。

## 背景信息<a name="section65441556168"></a>

-   创建和使用Notebook需要消耗资源，需要收费。根据您选择的资源不同，收费标准不同，针对不同类型资源的价格，详情请参见[产品价格详情](https://www.huaweicloud.com/price_detail.html#/modelarts_detail)。
-   “运行中“的Notebook将一直收费，当您不需要使用时，建议停止Notebook，避免产生不必要的费用。在创建Notebook时，也可以选择开启自动停止功能，在指定时间内停止运行Notebook，避免产生不必要的费用。
-   “启动中“、“停止“或“错误“状态的Notebook，无法执行打开操作。
-   一个账户最多创建10个Notebook。
-   由于ModelArts支持多种AI引擎，在创建Notebook实例时，首先选择Python2或Python3的工作环境，Notebook实例创建完成后，再访问Notebook实例，在Jupyter页面创建对应AI引擎的工作环境。详情指导请参见[选择不同AI引擎新建文件](#section498263112184)。
-   如果设置使用OBS存储，确保您指定的OBS目录与ModelArts在同一区域。

## 创建Notebook<a name="section1458310428584"></a>

1.  登录ModelArts管理控制台，在左侧菜单栏中选择“开发环境\>Notebook“，进入“Notebook“管理页面。
2.  单击“创建“进入“创建Notebook“页面，参考[表1](#table49201520828)填写信息。

    **表 1**  参数说明

    <a name="table49201520828"></a>
    <table><thead align="left"><tr id="row199161820229"><th class="cellrowborder" valign="top" width="16.71%" id="mcps1.2.3.1.1"><p id="p13916920226"><a name="p13916920226"></a><a name="p13916920226"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="83.28999999999999%" id="mcps1.2.3.1.2"><p id="p199163201722"><a name="p199163201722"></a><a name="p199163201722"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row17917112012210"><td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.2.3.1.1 "><p id="p13916520027"><a name="p13916520027"></a><a name="p13916520027"></a><span class="parmname" id="parmname158561439164918"><a name="parmname158561439164918"></a><a name="parmname158561439164918"></a>“计费方式”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="83.28999999999999%" headers="mcps1.2.3.1.2 "><p id="p1691612010211"><a name="p1691612010211"></a><a name="p1691612010211"></a>按需计费。当前仅支持按需计费，无需修改。</p>
    </td>
    </tr>
    <tr id="row1291714201927"><td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.2.3.1.1 "><p id="p59173204218"><a name="p59173204218"></a><a name="p59173204218"></a><span class="parmname" id="parmname13519125514497"><a name="parmname13519125514497"></a><a name="parmname13519125514497"></a>“名称”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="83.28999999999999%" headers="mcps1.2.3.1.2 "><p id="p3917102018217"><a name="p3917102018217"></a><a name="p3917102018217"></a>Notebook的名称。只能包含数字、字母、下划线和中划线，长度不能超过20位且不能为空。</p>
    </td>
    </tr>
    <tr id="row27561314171414"><td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.2.3.1.1 "><p id="p975761431416"><a name="p975761431416"></a><a name="p975761431416"></a><span class="parmname" id="parmname1999442531418"><a name="parmname1999442531418"></a><a name="parmname1999442531418"></a>“自动停止”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="83.28999999999999%" headers="mcps1.2.3.1.2 "><p id="p77571414101412"><a name="p77571414101412"></a><a name="p77571414101412"></a>默认开启，且默认值为<span class="parmname" id="parmname9970450151416"><a name="parmname9970450151416"></a><a name="parmname9970450151416"></a>“1小时后”</span>，表示该Notebook实例将在运行1小时之后自动停止，即1小时后停止计费。</p>
    <p id="p1968615173155"><a name="p1968615173155"></a><a name="p1968615173155"></a>开启自动停止功能后，可选择<span class="parmname" id="parmname13786133219152"><a name="parmname13786133219152"></a><a name="parmname13786133219152"></a>“1小时后”</span>、<span class="parmname" id="parmname12974933101516"><a name="parmname12974933101516"></a><a name="parmname12974933101516"></a>“2小时后”</span>、<span class="parmname" id="parmname12345935171517"><a name="parmname12345935171517"></a><a name="parmname12345935171517"></a>“4小时后”</span>、<span class="parmname" id="parmname183841737181518"><a name="parmname183841737181518"></a><a name="parmname183841737181518"></a>“6小时后”</span>或<span class="parmname" id="parmname479183813153"><a name="parmname479183813153"></a><a name="parmname479183813153"></a>“自定义”</span>几种模式。选择<span class="parmname" id="parmname135608241616"><a name="parmname135608241616"></a><a name="parmname135608241616"></a>“自定义”</span>模式时，可指定1~24小时范围内任意整数。</p>
    </td>
    </tr>
    <tr id="row1917112010214"><td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.2.3.1.1 "><p id="p1991742019212"><a name="p1991742019212"></a><a name="p1991742019212"></a><span class="parmname" id="parmname02461353174919"><a name="parmname02461353174919"></a><a name="parmname02461353174919"></a>“描述”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="83.28999999999999%" headers="mcps1.2.3.1.2 "><p id="p9917122010211"><a name="p9917122010211"></a><a name="p9917122010211"></a>对Notebook的简要描述。</p>
    </td>
    </tr>
    <tr id="row8918182013219"><td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.2.3.1.1 "><p id="p5917620423"><a name="p5917620423"></a><a name="p5917620423"></a><span class="parmname" id="parmname13556204994916"><a name="parmname13556204994916"></a><a name="parmname13556204994916"></a>“工作环境”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="83.28999999999999%" headers="mcps1.2.3.1.2 "><p id="p139531822602"><a name="p139531822602"></a><a name="p139531822602"></a>当前支持2种工作环境，分别为<span class="parmname" id="parmname12135130525"><a name="parmname12135130525"></a><a name="parmname12135130525"></a>“Python2”</span>和<span class="parmname" id="parmname78981331725"><a name="parmname78981331725"></a><a name="parmname78981331725"></a>“Python3”</span>，不同工作环境其对应可使用的AI引擎不同，详细支持列表请参见<a href="Notebook简介.md#section191109611479">支持的AI引擎</a>。</p>
    <p id="p3179193214329"><a name="p3179193214329"></a><a name="p3179193214329"></a>每个工作环境多种AI引擎，可以在同一个Notebook实例中使用所有支持的AI引擎，不同的引擎之间可快速、方便的切换，并且有独立的运行环境。您可以在Notebook实例创建完成后，进入Jupyter页面创建对应AI引擎的开发环境。</p>
    <div class="note" id="note1691812018212"><a name="note1691812018212"></a><a name="note1691812018212"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1998944229"><a name="p1998944229"></a><a name="p1998944229"></a>ModelArts还支持Keras引擎，详细说明请参见<a href="https://support.huaweicloud.com/modelarts_faq/modelarts_05_0042.html" target="_blank" rel="noopener noreferrer">ModelArts是否支持Keras引擎？</a></p>
    </div></div>
    </td>
    </tr>
    <tr id="row1491818201024"><td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.2.3.1.1 "><p id="p18918152012217"><a name="p18918152012217"></a><a name="p18918152012217"></a><span class="parmname" id="parmname2521645164915"><a name="parmname2521645164915"></a><a name="parmname2521645164915"></a>“资源池”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="83.28999999999999%" headers="mcps1.2.3.1.2 "><p id="p149180202212"><a name="p149180202212"></a><a name="p149180202212"></a>可选公共资源池和专属资源池，关于ModelArts专属资源池的介绍和购买，请参见<a href="资源池.md">资源池</a>。</p>
    </td>
    </tr>
    <tr id="row691916202217"><td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.2.3.1.1 "><p id="p691814201027"><a name="p691814201027"></a><a name="p691814201027"></a><span class="parmname" id="parmname159119424498"><a name="parmname159119424498"></a><a name="parmname159119424498"></a>“类型”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="83.28999999999999%" headers="mcps1.2.3.1.2 "><p id="p691913201322"><a name="p691913201322"></a><a name="p691913201322"></a>支持CPU和GPU两种类型。GPU性能更佳，但是相对CPU而言，费用更高。</p>
    </td>
    </tr>
    <tr id="row13919142012210"><td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.2.3.1.1 "><p id="p291918203215"><a name="p291918203215"></a><a name="p291918203215"></a><span class="parmname" id="parmname944663944917"><a name="parmname944663944917"></a><a name="parmname944663944917"></a>“规格”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="83.28999999999999%" headers="mcps1.2.3.1.2 "><p id="p137524719617"><a name="p137524719617"></a><a name="p137524719617"></a>只有选择<span class="parmname" id="parmname10103115310476"><a name="parmname10103115310476"></a><a name="parmname10103115310476"></a>“公共资源池”</span>时，需要选择规格。根据选择的类型不同，可选规格也不同。</p>
    <a name="ul0557112811613"></a><a name="ul0557112811613"></a><ul id="ul0557112811613"><li>CPU规格支持：<span class="parmname" id="parmname10725181665013"><a name="parmname10725181665013"></a><a name="parmname10725181665013"></a>“2核8GiB”</span>、<span class="parmname" id="parmname1147152145010"><a name="parmname1147152145010"></a><a name="parmname1147152145010"></a>“8核32GiB”</span>。</li><li>GPU规格支持：<span class="parmname" id="parmname1457712512507"><a name="parmname1457712512507"></a><a name="parmname1457712512507"></a>“8核64GiB 1*p100”</span>（默认）、<span class="parmname" id="parmname0973124217129"><a name="parmname0973124217129"></a><a name="parmname0973124217129"></a>“8核64Gi B 1*v100NV32”</span>（仅在华北-北京四可用）</li></ul>
    </td>
    </tr>
    <tr id="row29205209212"><td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.2.3.1.1 "><p id="p6919162010214"><a name="p6919162010214"></a><a name="p6919162010214"></a><span class="parmname" id="parmname14623173720494"><a name="parmname14623173720494"></a><a name="parmname14623173720494"></a>“存储配置”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="83.28999999999999%" headers="mcps1.2.3.1.2 "><p id="p1391917201622"><a name="p1391917201622"></a><a name="p1391917201622"></a>存储配置可选<span class="parmname" id="parmname117182681418"><a name="parmname117182681418"></a><a name="parmname117182681418"></a>“云硬盘”</span>和<span class="parmname" id="parmname957232811145"><a name="parmname957232811145"></a><a name="parmname957232811145"></a>“对象存储服务”</span>。</p>
    <a name="ul491912207219"></a><a name="ul491912207219"></a><ul id="ul491912207219"><li>选择<span class="parmname" id="parmname123141943114"><a name="parmname123141943114"></a><a name="parmname123141943114"></a>“云硬盘”</span>作为存储位置<p id="p129182052155"><a name="p129182052155"></a><a name="p129182052155"></a>根据实际使用量设置磁盘规格。磁盘规格默认5GB。ModelArts提供5GB容量供用户免费使用。超出5GB时，超出部分每GB按<span class="parmname" id="parmname153420149316"><a name="parmname153420149316"></a><a name="parmname153420149316"></a>“超高IO”</span>类型的收费标准进行按需收费。磁盘规格的取值范围为5GB～500GB。</p>
    <p id="p78214017162"><a name="p78214017162"></a><a name="p78214017162"></a>选择此模式，用户在Notebook列表的所有文件读写操作都是针对容器中的内容操作，与OBS无关；重启该实例，内容不丢失。</p>
    </li><li>选择<span class="parmname" id="parmname1843014112319"><a name="parmname1843014112319"></a><a name="parmname1843014112319"></a>“对象存储服务”</span>作为存储位置<p id="p1066265732012"><a name="p1066265732012"></a><a name="p1066265732012"></a>在<span class="parmname" id="parmname24901450192316"><a name="parmname24901450192316"></a><a name="parmname24901450192316"></a>“存储位置”</span>右侧单击<span class="uicontrol" id="uicontrol18915145232317"><a name="uicontrol18915145232317"></a><a name="uicontrol18915145232317"></a>“选择”</span>，设置用于存储Notebook数据的OBS路径。如果想直接使用已有的文件或数据，可将数据提前上传至对应的OBS路径下。<span class="parmname" id="parmname14760143715516"><a name="parmname14760143715516"></a><a name="parmname14760143715516"></a>“存储位置”</span>不能设置为OBS桶的根目录，需设置为对应OBS桶下的具体目录。</p>
    <p id="p8517173341620"><a name="p8517173341620"></a><a name="p8517173341620"></a>选择此模式，用户在Notebook列表的所有文件读写操作是基于所选择的OBS路径下的内容操作，与当前实例空间无关。如果您需要将内容同步到实例空间，先选中该内容，单击<span class="uicontrol" id="uicontrol187746427240"><a name="uicontrol187746427240"></a><a name="uicontrol187746427240"></a>“Sync OBS”</span>，即可将所选内容同步到当前容器空间，详细操作可参见<a href="使用Sync-OBS功能.md">使用Sync OBS功能</a>。重启该实例时，内容不丢失。</p>
    </li></ul>
    </td>
    </tr>
    </tbody>
    </table>

3.  参数填写完成后，单击“下一步“进行规格确认。
4.  参数确认无误后，单击“立即创建“，完成Notebook的创建操作。

    进入Notebook列表，正在创建中的Notebook状态为“启动中“，创建过程需要几分钟，请耐心等待。当Notebook状态变为“运行中“时，表示Notebook已创建完成。


## 打开Notebook<a name="section15550517465"></a>

在Notebook列表中，选择需要打开的Notebook，单击“操作“列中的“打开“，进入“Jupyter Notebook“开发页面。

在“Jupyter Notebook“页面中，有“Files“、“Running“、“Clusters“、“ModelArts Examples“4个页签。

**图 1**  Jupyter Notebook开发界面<a name="fig3835162873611"></a>  
![](figures/Jupyter-Notebook开发界面.png "Jupyter-Notebook开发界面")

## 选择不同AI引擎新建文件<a name="section498263112184"></a>

打开Notebook实例后，进入“Jupyter Notebook“页面，在“Files“页签下，您可以单击右上角“New“，然后选择所需的AI引擎，创建一个用于编码的文件。

**图 2**  选择不同的AI引擎<a name="fig2984115918203"></a>  
![](figures/选择不同的AI引擎.png "选择不同的AI引擎")

