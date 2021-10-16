# 创建Notebook实例<a name="modelarts_30_0004"></a>

在开始进行模型开发前，您需要创建Notebook实例，并打开Notebook进行编码。

## 背景信息<a name="section65441556168"></a>

-   “运行中“的Notebook将一直收费，当您不需要使用时，建议停止Notebook，避免产生不必要的费用。在创建Notebook时，也可以选择开启自动停止功能，在指定时间内停止运行Notebook，避免产生不必要的费用。
-   只有处于“运行中“状态的Notebook，才可以执行打开、停止、删除操作。
-   基于MindStudio框架创建的实例，只能通过远程开发环境访问。其他框架的Notebook实例，可以在Notebook实例的列表页面打开。
-   一个账户最多创建10个Notebook。
-   创建Notebook实例前，可先了解ModelArts[支持的AI引擎](开发环境简介.md#section191109611479)及其对应版本情况。

## 创建Notebook实例<a name="section1458310428584"></a>

1.  登录ModelArts管理控制台，在左侧导航栏中选择“开发环境 \> Notebook“，进入“Notebook“新版管理页面。

    **图 1**  进入新版Notebook<a name="fig564152610526"></a>  
    ![](figures/进入新版Notebook.png "进入新版Notebook")

2.  单击“创建“，进入“创建Notebook“页面，请参见如下说明填写参数。
    1.  填写Notebook基本信息，包含名称、描述、是否自动停止，详细参数请参见[表1](#table1669535791517)。

        **图 2**  Notebook基本信息<a name="fig12309736151510"></a>  
        ![](figures/Notebook基本信息.png "Notebook基本信息")

        **表 1**  基本信息的参数描述

        <a name="table1669535791517"></a>
        <table><thead align="left"><tr id="row156957575157"><th class="cellrowborder" valign="top" width="16.71%" id="mcps1.2.3.1.1"><p id="p19734156171419"><a name="p19734156171419"></a><a name="p19734156171419"></a>参数名称</p>
        </th>
        <th class="cellrowborder" valign="top" width="83.28999999999999%" id="mcps1.2.3.1.2"><p id="p15734256161411"><a name="p15734256161411"></a><a name="p15734256161411"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row12695105718152"><td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.2.3.1.1 "><p id="p3734056191410"><a name="p3734056191410"></a><a name="p3734056191410"></a><span class="parmname" id="parmname107341956161415"><a name="parmname107341956161415"></a><a name="parmname107341956161415"></a>“名称”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="83.28999999999999%" headers="mcps1.2.3.1.2 "><p id="p167341256171415"><a name="p167341256171415"></a><a name="p167341256171415"></a>Notebook的名称。只能包含数字、大小写字母、下划线和中划线，长度不能超过20位且不能为空。</p>
        </td>
        </tr>
        <tr id="row2069535761517"><td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.2.3.1.1 "><p id="p157341956121416"><a name="p157341956121416"></a><a name="p157341956121416"></a><span class="parmname" id="parmname9734105611415"><a name="parmname9734105611415"></a><a name="parmname9734105611415"></a>“描述”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="83.28999999999999%" headers="mcps1.2.3.1.2 "><p id="p1473425641419"><a name="p1473425641419"></a><a name="p1473425641419"></a>对Notebook的简要描述。</p>
        </td>
        </tr>
        <tr id="row26969577153"><td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.2.3.1.1 "><p id="p2073420566140"><a name="p2073420566140"></a><a name="p2073420566140"></a><span class="parmname" id="parmname15734756151416"><a name="parmname15734756151416"></a><a name="parmname15734756151416"></a>“自动停止”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="83.28999999999999%" headers="mcps1.2.3.1.2 "><p id="p673455615141"><a name="p673455615141"></a><a name="p673455615141"></a>默认开启，且默认值为<span class="parmname" id="parmname473495691416"><a name="parmname473495691416"></a><a name="parmname473495691416"></a>“1小时后”</span>，表示该Notebook实例将在运行1小时之后自动停止，即1小时后停止计费。</p>
        <p id="p3734165611140"><a name="p3734165611140"></a><a name="p3734165611140"></a>开启自动停止功能后，可选择<span class="parmname" id="parmname273410568146"><a name="parmname273410568146"></a><a name="parmname273410568146"></a>“1小时后”</span>、<span class="parmname" id="parmname9734256101418"><a name="parmname9734256101418"></a><a name="parmname9734256101418"></a>“2小时后”</span>、<span class="parmname" id="parmname137345564145"><a name="parmname137345564145"></a><a name="parmname137345564145"></a>“4小时后”</span>、<span class="parmname" id="parmname0734125610148"><a name="parmname0734125610148"></a><a name="parmname0734125610148"></a>“6小时后”</span>或<span class="parmname" id="parmname973425671412"><a name="parmname973425671412"></a><a name="parmname973425671412"></a>“自定义”</span>几种模式。选择<span class="parmname" id="parmname673495661413"><a name="parmname673495661413"></a><a name="parmname673495661413"></a>“自定义”</span>模式时，可指定1~24小时范围内任意整数。</p>
        </td>
        </tr>
        </tbody>
        </table>

    2.  填写Notebook详细参数，如工作环境、资源规格等，详细参数请参见[表2](#table4606194015227)。

        **图 3**  Notebook实例的详细参数<a name="fig1049410611200"></a>  
        ![](figures/Notebook实例的详细参数.png "Notebook实例的详细参数")

        ![](figures/zh-cn_image_0000001171546689.png)

        **表 2**  Notebook实例的详细参数说明

        <a name="table4606194015227"></a>
        <table><thead align="left"><tr id="row1604184022219"><th class="cellrowborder" valign="top" width="16.8%" id="mcps1.2.3.1.1"><p id="p18604640152219"><a name="p18604640152219"></a><a name="p18604640152219"></a>参数名称</p>
        </th>
        <th class="cellrowborder" valign="top" width="83.2%" id="mcps1.2.3.1.2"><p id="p7604164013227"><a name="p7604164013227"></a><a name="p7604164013227"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row26048409224"><td class="cellrowborder" valign="top" width="16.8%" headers="mcps1.2.3.1.1 "><p id="p1360454019229"><a name="p1360454019229"></a><a name="p1360454019229"></a><span class="parmname" id="parmname18604164018224"><a name="parmname18604164018224"></a><a name="parmname18604164018224"></a>“镜像”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="83.2%" headers="mcps1.2.3.1.2 "><p id="p086519261112"><a name="p086519261112"></a><a name="p086519261112"></a>支持公共镜像和自定义镜像。</p>
        <a name="ul106491257429"></a><a name="ul106491257429"></a><ul id="ul106491257429"><li>公共镜像：即预置在ModelArts内部的AI框架。</li><li>自定义镜像：可以将基于公共镜像创建的实例保存下来，作为自定义镜像使用。</li></ul>
        <p id="p56191747143017"><a name="p56191747143017"></a><a name="p56191747143017"></a>一个镜像对应支持一种AI引擎，创建Notebook实例时选择好了对应AI引擎的镜像。用户可以根据需要选择镜像。</p>
        <p id="p15604194013229"><a name="p15604194013229"></a><a name="p15604194013229"></a>不可以在同一个Notebook实例中切换AI引擎。</p>
        </td>
        </tr>
        <tr id="row18604164013223"><td class="cellrowborder" valign="top" width="16.8%" headers="mcps1.2.3.1.1 "><p id="p4604640202212"><a name="p4604640202212"></a><a name="p4604640202212"></a><span class="parmname" id="parmname9604154082214"><a name="parmname9604154082214"></a><a name="parmname9604154082214"></a>“资源池”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="83.2%" headers="mcps1.2.3.1.2 "><p id="p1060404014228"><a name="p1060404014228"></a><a name="p1060404014228"></a><span class="parmname" id="parmname2865512286"><a name="parmname2865512286"></a><a name="parmname2865512286"></a>“公共资源池”</span>无需单独购买，即开即用，按需付费，即按您的Notebook实例运行时长进行收费。</p>
        <p id="p871113394116"><a name="p871113394116"></a><a name="p871113394116"></a><span class="parmname" id="parmname11217154019119"><a name="parmname11217154019119"></a><a name="parmname11217154019119"></a>“专属资源池”</span>需要单独购买并创建。</p>
        </td>
        </tr>
        <tr id="row136058406229"><td class="cellrowborder" valign="top" width="16.8%" headers="mcps1.2.3.1.1 "><p id="p11604114015221"><a name="p11604114015221"></a><a name="p11604114015221"></a><span class="parmname" id="parmname260474016221"><a name="parmname260474016221"></a><a name="parmname260474016221"></a>“类型”</span></p>
        <p id="p8166163018376"><a name="p8166163018376"></a><a name="p8166163018376"></a></p>
        </td>
        <td class="cellrowborder" valign="top" width="83.2%" headers="mcps1.2.3.1.2 "><p id="p10222519123818"><a name="p10222519123818"></a><a name="p10222519123818"></a>芯片类型包括CPU、GPU和Ascend类型。</p>
        <p id="p4133623133815"><a name="p4133623133815"></a><a name="p4133623133815"></a>不同的镜像支持的芯片类型不同，根据实际需要选择。</p>
        <p id="p12645183303715"><a name="p12645183303715"></a><a name="p12645183303715"></a>GPU性能更佳，但是相对CPU而言，费用更高。</p>
        </td>
        </tr>
        <tr id="row19605184010226"><td class="cellrowborder" valign="top" width="16.8%" headers="mcps1.2.3.1.1 "><p id="p106051640172210"><a name="p106051640172210"></a><a name="p106051640172210"></a><span class="parmname" id="parmname860504013228"><a name="parmname860504013228"></a><a name="parmname860504013228"></a>“规格”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="83.2%" headers="mcps1.2.3.1.2 "><p id="p4605740122211"><a name="p4605740122211"></a><a name="p4605740122211"></a>根据选择的芯片类型不同，可选资源规格也不同。</p>
        <a name="ul66051440132210"></a><a name="ul66051440132210"></a><ul id="ul66051440132210"><li>CPU规格<p id="p990913205593"><a name="p990913205593"></a><a name="p990913205593"></a><span class="parmname" id="parmname17909920185915"><a name="parmname17909920185915"></a><a name="parmname17909920185915"></a>“2核8GB”</span>：Intel CPU通用规格，用于快速数据探索和实验</p>
        <p id="p2049220179596"><a name="p2049220179596"></a><a name="p2049220179596"></a><span class="parmname" id="parmname13605174022219"><a name="parmname13605174022219"></a><a name="parmname13605174022219"></a>“8核32GB”</span>：Intel CPU算力增强型，适用于密集计算场景下运算</p>
        </li><li>GPU规格<p id="p153714311501"><a name="p153714311501"></a><a name="p153714311501"></a><span class="parmname" id="parmname146054408228"><a name="parmname146054408228"></a><a name="parmname146054408228"></a>“GPU: 1*V100(32GB)|CPU: 8 核 64GB”</span>：NVIDIA V100 GPU单卡规格，32GB显存，适合深度学习场景下的算法训练和调测</p>
        </li><li>Ascend规格<p id="p125271175213"><a name="p125271175213"></a><a name="p125271175213"></a><span class="parmname" id="parmname126701730135310"><a name="parmname126701730135310"></a><a name="parmname126701730135310"></a>“Ascend: 1*Ascend 910|CPU: 24 核 96GB”</span>：昇腾910(32GB显存)单卡规格，配搭ARM处理器，适合深度学习场景下的模型训练和调测</p>
        </li></ul>
        </td>
        </tr>
        <tr id="row5606114012216"><td class="cellrowborder" valign="top" width="16.8%" headers="mcps1.2.3.1.1 "><p id="p960518405227"><a name="p960518405227"></a><a name="p960518405227"></a><span class="parmname" id="parmname56051740132219"><a name="parmname56051740132219"></a><a name="parmname56051740132219"></a>“存储配置”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="83.2%" headers="mcps1.2.3.1.2 "><p id="p20606174062210"><a name="p20606174062210"></a><a name="p20606174062210"></a>存储配置可选<span class="parmname" id="parmname34435417557"><a name="parmname34435417557"></a><a name="parmname34435417557"></a>“默认存储”</span>和<span class="parmname" id="parmname186061940142211"><a name="parmname186061940142211"></a><a name="parmname186061940142211"></a>“云硬盘EVS”</span>。</p>
        <a name="ul106061540192218"></a><a name="ul106061540192218"></a><ul id="ul106061540192218"><li>选择<span class="parmname" id="parmname4487204817151"><a name="parmname4487204817151"></a><a name="parmname4487204817151"></a>“默认存储”</span>作为存储位置。<p id="p1170644919155"><a name="p1170644919155"></a><a name="p1170644919155"></a>公共资源池模式下支持，专属资源池模式下不支持。</p>
        <p id="p1178192516321"><a name="p1178192516321"></a><a name="p1178192516321"></a>选择此模式，平台免费为每一个Notebook提供50GB的默认存储。</p>
        </li><li>选择<span class="parmname" id="parmname16606040172220"><a name="parmname16606040172220"></a><a name="parmname16606040172220"></a>“云硬盘EVS”</span>作为存储位置<p id="p11980135117569"><a name="p11980135117569"></a><a name="p11980135117569"></a>根据实际使用量设置磁盘规格。磁盘规格默认5GB。磁盘规格的取值范围为5GB～4096GB。</p>
        <p id="p18207236175718"><a name="p18207236175718"></a><a name="p18207236175718"></a>从Notebook实例创建成功开始，直至实例删除成功，磁盘每GB按照规定费用收费。</p>
        </li></ul>
        <p id="p101352055134117"><a name="p101352055134117"></a><a name="p101352055134117"></a><span class="parmname" id="parmname1013511556415"><a name="parmname1013511556415"></a><a name="parmname1013511556415"></a>“默认存储”</span>和<span class="parmname" id="parmname2013511558414"><a name="parmname2013511558414"></a><a name="parmname2013511558414"></a>“云硬盘EVS”</span>的存储路径挂载在/home/ma-user/work目录下。用户在Notebook实例中的所有文件读写操作都是针对该存储目录下的的内容操作，与OBS无关。</p>
        <p id="p1575552324218"><a name="p1575552324218"></a><a name="p1575552324218"></a>停止或重启Notebook实例时，内容会被保留，不丢失。</p>
        <p id="p43829014426"><a name="p43829014426"></a><a name="p43829014426"></a>删除Notebook实例时，内容不保留。</p>
        </td>
        </tr>
        <tr id="row6606144010222"><td class="cellrowborder" valign="top" width="16.8%" headers="mcps1.2.3.1.1 "><p id="p76061340122212"><a name="p76061340122212"></a><a name="p76061340122212"></a><span class="parmname" id="parmname106064408221"><a name="parmname106064408221"></a><a name="parmname106064408221"></a>“SSH远程开发”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="83.2%" headers="mcps1.2.3.1.2 "><p id="p6554391531"><a name="p6554391531"></a><a name="p6554391531"></a>开启此功能后，用户可以在本地开发环境中远程接入Notebook实例的开发环境。</p>
        </td>
        </tr>
        <tr id="row15192194815534"><td class="cellrowborder" valign="top" width="16.8%" headers="mcps1.2.3.1.1 "><p id="p719214487537"><a name="p719214487537"></a><a name="p719214487537"></a><span class="parmname" id="parmname16422814165511"><a name="parmname16422814165511"></a><a name="parmname16422814165511"></a>“密钥对”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="83.2%" headers="mcps1.2.3.1.2 "><p id="p621823355417"><a name="p621823355417"></a><a name="p621823355417"></a>开启<span class="parmname" id="parmname2218933105419"><a name="parmname2218933105419"></a><a name="parmname2218933105419"></a>“SSH远程开发”</span>功能后，需要设置此参数。</p>
        <p id="p7192164814538"><a name="p7192164814538"></a><a name="p7192164814538"></a>可以选择已有密钥对。</p>
        <p id="p42909384718"><a name="p42909384718"></a><a name="p42909384718"></a>也可以单击密钥对右侧的<span class="uicontrol" id="uicontrol151732007556"><a name="uicontrol151732007556"></a><a name="uicontrol151732007556"></a>“立即创建”</span>，跳转到数据加密控制台，在<span class="menucascade" id="menucascade113926300551"><a name="menucascade113926300551"></a><a name="menucascade113926300551"></a>“<span class="uicontrol" id="uicontrol239253017558"><a name="uicontrol239253017558"></a><a name="uicontrol239253017558"></a>密钥对管理 &gt; 私有密钥对</span>”</span>页面，单击<span class="uicontrol" id="uicontrol22444353552"><a name="uicontrol22444353552"></a><a name="uicontrol22444353552"></a>“创建密钥对”</span>。</p>
        <div class="caution" id="note168871542778"><a name="note168871542778"></a><a name="note168871542778"></a><span class="cautiontitle"> 注意： </span><div class="cautionbody"><p id="p1088711421375"><a name="p1088711421375"></a><a name="p1088711421375"></a>创建好的密钥对，请下载并妥善保存，使用本地IDE远程连接云上Notebook开发环境时，需要用到密钥对进行鉴权认证。</p>
        </div></div>
        </td>
        </tr>
        <tr id="row152971344135318"><td class="cellrowborder" valign="top" width="16.8%" headers="mcps1.2.3.1.1 "><p id="p19297744165315"><a name="p19297744165315"></a><a name="p19297744165315"></a><span class="parmname" id="parmname826031011555"><a name="parmname826031011555"></a><a name="parmname826031011555"></a>“远程访问白名单”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="83.2%" headers="mcps1.2.3.1.2 "><p id="p2084611102574"><a name="p2084611102574"></a><a name="p2084611102574"></a>开启<span class="parmname" id="parmname12777181155714"><a name="parmname12777181155714"></a><a name="parmname12777181155714"></a>“SSH远程开发”</span>功能后，需要设置此参数。</p>
        <p id="p8601311647"><a name="p8601311647"></a><a name="p8601311647"></a>远程访问白名单设置为将要访问这个Notebook的IP地址，例如本地PC的IP地址或者访问机器的外网地址。</p>
        <p id="p17297184414539"><a name="p17297184414539"></a><a name="p17297184414539"></a>如果用户使用的访问机器和华为云ModelArts服务的网络有隔离，则访问机器的外网地址需要在主流搜索引擎中搜索“IP地址查询”获取，而不是使用ipconfig或ifconfigip命令在本地查询。支持最多配置5个IP地址。</p>
        <div class="fignone" id="fig16623133332011"><a name="fig16623133332011"></a><a name="fig16623133332011"></a><span class="figcap"><b>图1 </b>查询外网IP地址</span><br><a name="image13776855134512"></a><a name="image13776855134512"></a><span><img id="image13776855134512" src="figures/查询外网IP地址.png" width="383.8380000000001" height="170.594711"></span></div>
        <p id="p885144975719"><a name="p885144975719"></a><a name="p885144975719"></a>白名单IP地址如果配置错误将无法连接Notebook开发环境。</p>
        <p id="p94152054154815"><a name="p94152054154815"></a><a name="p94152054154815"></a>创建完Notebook后，可以在Notebook详情页中修改白名单IP地址。</p>
        </td>
        </tr>
        </tbody>
        </table>

3.  参数填写完成后，单击“下一步“进行规格确认。
4.  参数确认无误后，单击“提交“，完成Notebook的创建操作。

    进入Notebook列表，正在创建中的Notebook状态为“创建中“，创建过程需要几分钟，请耐心等待。当Notebook状态变为“运行中“时，表示Notebook已创建并启动完成。

5.  在Notebook列表，单击实例名称，进入实例详情页，查看Notebook实例配置信息。

    包括Notebook实例名称、规格、状态、镜像类型、用户ID、存储路径、存储容量、Notebook地址和端口号、允许远程访问的白名单IP地址、认证密钥文件名。

    **图 5**  查看Notebook实例详情<a name="fig63831517914"></a>  
    ![](figures/查看Notebook实例详情.png "查看Notebook实例详情")

    在白名单右侧单击修改，可以修改允许远程访问的白名单IP地址。


