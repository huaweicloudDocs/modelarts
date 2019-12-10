# 从OBS中选择元模型<a name="modelarts_23_0207"></a>

针对使用常用框架完成模型开发和训练的场景，可以将您的模型导入至ModelArts中，进行统一管理。

## 使用前必读<a name="section149289423310"></a>

-   已完成模型开发和训练，使用的AI引擎为ModelArts支持的类型和版本。ModelArts支持如下几种常用引擎及其支持的runtime范围。

    **表 1**  推理支持的常用引擎及其Runtime

    <a name="table191424319137"></a>
    <table><thead align="left"><tr id="row21432031201310"><th class="cellrowborder" valign="top" width="26.97%" id="mcps1.2.4.1.1"><p id="p414313310130"><a name="p414313310130"></a><a name="p414313310130"></a>模型使用的引擎类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="27.279999999999998%" id="mcps1.2.4.1.2"><p id="p514310313137"><a name="p514310313137"></a><a name="p514310313137"></a>支持的运行环境（Runtime）</p>
    </th>
    <th class="cellrowborder" valign="top" width="45.75%" id="mcps1.2.4.1.3"><p id="p6565163053415"><a name="p6565163053415"></a><a name="p6565163053415"></a>备注</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row71437318132"><td class="cellrowborder" valign="top" width="26.97%" headers="mcps1.2.4.1.1 "><p id="p1614383131315"><a name="p1614383131315"></a><a name="p1614383131315"></a>TensorFlow</p>
    </td>
    <td class="cellrowborder" valign="top" width="27.279999999999998%" headers="mcps1.2.4.1.2 "><p id="p1419510107149"><a name="p1419510107149"></a><a name="p1419510107149"></a>python3.6</p>
    <p id="p13111811131412"><a name="p13111811131412"></a><a name="p13111811131412"></a>python2.7</p>
    <p id="p635545715219"><a name="p635545715219"></a><a name="p635545715219"></a>tf1.13-python2.7-gpu</p>
    <p id="p9596207318"><a name="p9596207318"></a><a name="p9596207318"></a>tf1.13-python2.7-cpu</p>
    <p id="p7663523136"><a name="p7663523136"></a><a name="p7663523136"></a>tf1.13-python3.6-gpu</p>
    <p id="p206081924635"><a name="p206081924635"></a><a name="p206081924635"></a>tf1.13-python3.6-cpu</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.75%" headers="mcps1.2.4.1.3 "><p id="p13565173093417"><a name="p13565173093417"></a><a name="p13565173093417"></a>python2.7以及python3.6的运行环境搭载的TensorFlow版本为1.8.0。默认使用的runtime为python2.7。</p>
    </td>
    </tr>
    <tr id="row1114312310138"><td class="cellrowborder" valign="top" width="26.97%" headers="mcps1.2.4.1.1 "><p id="p2014363171312"><a name="p2014363171312"></a><a name="p2014363171312"></a>MXNet</p>
    </td>
    <td class="cellrowborder" valign="top" width="27.279999999999998%" headers="mcps1.2.4.1.2 "><p id="p4553201911410"><a name="p4553201911410"></a><a name="p4553201911410"></a>python3.6</p>
    <p id="p18143153161317"><a name="p18143153161317"></a><a name="p18143153161317"></a>python2.7</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.75%" headers="mcps1.2.4.1.3 "><p id="p16565030173411"><a name="p16565030173411"></a><a name="p16565030173411"></a>python2.7以及python3.6的运行环境搭载的MXNet版本为1.2.1。默认使用的runtime为python2.7。</p>
    </td>
    </tr>
    <tr id="row16143193119135"><td class="cellrowborder" valign="top" width="26.97%" headers="mcps1.2.4.1.1 "><p id="p3143431131316"><a name="p3143431131316"></a><a name="p3143431131316"></a>Caffe</p>
    </td>
    <td class="cellrowborder" valign="top" width="27.279999999999998%" headers="mcps1.2.4.1.2 "><p id="p2143831181316"><a name="p2143831181316"></a><a name="p2143831181316"></a>python2.7</p>
    <p id="p17321236558"><a name="p17321236558"></a><a name="p17321236558"></a>python3.6</p>
    <p id="p19510173465315"><a name="p19510173465315"></a><a name="p19510173465315"></a>python2.7-gpu</p>
    <p id="p1844718407533"><a name="p1844718407533"></a><a name="p1844718407533"></a>python3.6-gpu</p>
    <p id="p1513014765310"><a name="p1513014765310"></a><a name="p1513014765310"></a>python2.7-cpu</p>
    <p id="p1821752135311"><a name="p1821752135311"></a><a name="p1821752135311"></a>python3.6-cpu</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.75%" headers="mcps1.2.4.1.3 "><p id="p099451712559"><a name="p099451712559"></a><a name="p099451712559"></a>python2.7、python3.6、python2.7-gpu、python3.6-gpu、python2.7-cpu、python3.6-cpu的运行环境搭载的Caffe版本为1.0.0</p>
    <p id="p72561652155520"><a name="p72561652155520"></a><a name="p72561652155520"></a>python2.7、python3.6只能用于运行适用于CPU的模型。推荐使用python2.7-gpu、python3.6-gpu、python2.7-cpu、python3.6-cpu的Runtime。默认使用的runtime为python2.7。</p>
    </td>
    </tr>
    <tr id="row514313161318"><td class="cellrowborder" valign="top" width="26.97%" headers="mcps1.2.4.1.1 "><p id="p16143193110139"><a name="p16143193110139"></a><a name="p16143193110139"></a>Spark_MLlib</p>
    </td>
    <td class="cellrowborder" valign="top" width="27.279999999999998%" headers="mcps1.2.4.1.2 "><p id="p032193413143"><a name="p032193413143"></a><a name="p032193413143"></a>python2.7</p>
    <p id="p101432031111317"><a name="p101432031111317"></a><a name="p101432031111317"></a>python3.6</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.75%" headers="mcps1.2.4.1.3 "><p id="p1356514304342"><a name="p1356514304342"></a><a name="p1356514304342"></a>python2.7以及python3.6的运行环境搭载的Spark_MLlib版本为2.3.2。默认使用的runtime为python2.7。</p>
    </td>
    </tr>
    <tr id="row1143331201316"><td class="cellrowborder" valign="top" width="26.97%" headers="mcps1.2.4.1.1 "><p id="p4143143115139"><a name="p4143143115139"></a><a name="p4143143115139"></a>Scikit_Learn</p>
    </td>
    <td class="cellrowborder" valign="top" width="27.279999999999998%" headers="mcps1.2.4.1.2 "><p id="p138174441410"><a name="p138174441410"></a><a name="p138174441410"></a>python2.7</p>
    <p id="p1314323121317"><a name="p1314323121317"></a><a name="p1314323121317"></a>python3.6</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.75%" headers="mcps1.2.4.1.3 "><p id="p1256553019345"><a name="p1256553019345"></a><a name="p1256553019345"></a>python2.7以及python3.6的运行环境搭载的Scikit_Learn版本为0.18.1。默认使用的runtime为python2.7。</p>
    </td>
    </tr>
    <tr id="row11432314131"><td class="cellrowborder" valign="top" width="26.97%" headers="mcps1.2.4.1.1 "><p id="p1214373116138"><a name="p1214373116138"></a><a name="p1214373116138"></a>XGBoost</p>
    </td>
    <td class="cellrowborder" valign="top" width="27.279999999999998%" headers="mcps1.2.4.1.2 "><p id="p163361454171410"><a name="p163361454171410"></a><a name="p163361454171410"></a>python2.7</p>
    <p id="p61431731141317"><a name="p61431731141317"></a><a name="p61431731141317"></a>python3.6</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.75%" headers="mcps1.2.4.1.3 "><p id="p10565630163417"><a name="p10565630163417"></a><a name="p10565630163417"></a>python2.7以及python3.6的运行环境搭载的XGBoost版本为0.80。默认使用的runtime为python2.7。</p>
    </td>
    </tr>
    <tr id="row9143331141312"><td class="cellrowborder" valign="top" width="26.97%" headers="mcps1.2.4.1.1 "><p id="p1114319312138"><a name="p1114319312138"></a><a name="p1114319312138"></a>PyTorch</p>
    </td>
    <td class="cellrowborder" valign="top" width="27.279999999999998%" headers="mcps1.2.4.1.2 "><p id="p11563116151"><a name="p11563116151"></a><a name="p11563116151"></a>python2.7</p>
    <p id="p2014313114135"><a name="p2014313114135"></a><a name="p2014313114135"></a>python3.6</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.75%" headers="mcps1.2.4.1.3 "><p id="p1656519309347"><a name="p1656519309347"></a><a name="p1656519309347"></a>python2.7以及python3.6的运行环境搭载的PyTorch版本为1.0。默认使用的runtime为python2.7。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   针对导入的模型，需符合ModelArts的模型包规范，推理代码和配置文件也需遵循ModelArts的要求，详细说明请参见[模型包规范介绍](模型包规范介绍.md)、[模型配置文件编写说明](模型配置文件编写说明.md)、[模型推理代码编写说明](模型推理代码编写说明.md)。
-   已完成训练的模型包，及其对应的推理代码和配置文件，已上传至OBS目录中。
-   确保您使用的OBS与ModelArts在同一区域。

## 导入模型操作步骤<a name="section118927471271"></a>

1.  登录ModelArts管理控制台，在左侧导航栏中选择“模型管理 \> 模型“，进入模型列表页面。
2.  单击左上角的“导入“，进入“导入模型“页面。
3.  在“导入模型“页面，填写相关参数。
    1.  填写模型基本信息，详细参数说明请参见[表2](#table19428112584211)。

        **表 2**  模型基本信息参数说明

        <a name="table19428112584211"></a>
        <table><thead align="left"><tr id="row2042972515427"><th class="cellrowborder" valign="top" width="18.91%" id="mcps1.2.3.1.1"><p id="p18429225134213"><a name="p18429225134213"></a><a name="p18429225134213"></a>参数名称</p>
        </th>
        <th class="cellrowborder" valign="top" width="81.08999999999999%" id="mcps1.2.3.1.2"><p id="p1742912544217"><a name="p1742912544217"></a><a name="p1742912544217"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row164292250428"><td class="cellrowborder" valign="top" width="18.91%" headers="mcps1.2.3.1.1 "><p id="p1842982518421"><a name="p1842982518421"></a><a name="p1842982518421"></a>名称</p>
        </td>
        <td class="cellrowborder" valign="top" width="81.08999999999999%" headers="mcps1.2.3.1.2 "><p id="p10429132534219"><a name="p10429132534219"></a><a name="p10429132534219"></a>模型名称。支持1～64位可见字符（含中文），名称可以包含字母、中文、数字、中划线、下划线。</p>
        </td>
        </tr>
        <tr id="row5429112564217"><td class="cellrowborder" valign="top" width="18.91%" headers="mcps1.2.3.1.1 "><p id="p14298255423"><a name="p14298255423"></a><a name="p14298255423"></a>版本</p>
        </td>
        <td class="cellrowborder" valign="top" width="81.08999999999999%" headers="mcps1.2.3.1.2 "><p id="p11429125104218"><a name="p11429125104218"></a><a name="p11429125104218"></a>设置所创建模型的版本。第一次导入时，默认为0.0.1。</p>
        </td>
        </tr>
        <tr id="row18429132512429"><td class="cellrowborder" valign="top" width="18.91%" headers="mcps1.2.3.1.1 "><p id="p24294259424"><a name="p24294259424"></a><a name="p24294259424"></a>描述</p>
        </td>
        <td class="cellrowborder" valign="top" width="81.08999999999999%" headers="mcps1.2.3.1.2 "><p id="p1042942514210"><a name="p1042942514210"></a><a name="p1042942514210"></a>模型的简要描述。</p>
        </td>
        </tr>
        </tbody>
        </table>

    2.  填写元模型来源及其相关参数。根据用户的不同场景，“元模型来源“的选择有4种不同方式，请参见[导入模型的4种场景](模型管理简介.md#section179419351998)。当“元模型来源“选择“从OBS中选择“时，其相关的参数配置请参见[表3](#table1631162916535)。

        针对从OBS导入的元模型，ModelArts要求根据[模型包规范](模型包规范介绍.md)，编写推理代码和配置文件，并将推理代码和配置文件放置元模型存储的“model“文件夹下。如果您选择的目录下无对应的推理代码及配置文件，将无法导入模型。

        **图 1**  从OBS中选择元模型<a name="fig1462852910532"></a>  
        ![](figures/从OBS中选择元模型.png "从OBS中选择元模型")

        **表 3**  元模型来源参数说明

        <a name="table1631162916535"></a>
        <table><thead align="left"><tr id="row362872915531"><th class="cellrowborder" valign="top" width="18.57%" id="mcps1.2.3.1.1"><p id="p6628132913538"><a name="p6628132913538"></a><a name="p6628132913538"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="81.43%" id="mcps1.2.3.1.2"><p id="p6628132985312"><a name="p6628132985312"></a><a name="p6628132985312"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row862812294533"><td class="cellrowborder" valign="top" width="18.57%" headers="mcps1.2.3.1.1 "><p id="p96281229195315"><a name="p96281229195315"></a><a name="p96281229195315"></a><span class="parmname" id="parmname36281329205318"><a name="parmname36281329205318"></a><a name="parmname36281329205318"></a>“选择元模型”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="81.43%" headers="mcps1.2.3.1.2 "><p id="p196286292531"><a name="p196286292531"></a><a name="p196286292531"></a>选择模型存储路径，此路径为训练作业中指定的<span class="parmname" id="parmname15628829135315"><a name="parmname15628829135315"></a><a name="parmname15628829135315"></a>“训练输出位置”</span>。</p>
        </td>
        </tr>
        <tr id="row1262920291539"><td class="cellrowborder" valign="top" width="18.57%" headers="mcps1.2.3.1.1 "><p id="p4629129145315"><a name="p4629129145315"></a><a name="p4629129145315"></a><span class="parmname" id="parmname262882905313"><a name="parmname262882905313"></a><a name="parmname262882905313"></a>“AI引擎”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="81.43%" headers="mcps1.2.3.1.2 "><p id="p17629172914537"><a name="p17629172914537"></a><a name="p17629172914537"></a>根据您选择的元模型存储路径，将自动关联出对应的<span class="parmname" id="parmname162982965310"><a name="parmname162982965310"></a><a name="parmname162982965310"></a>“AI引擎”</span>。</p>
        </td>
        </tr>
        <tr id="row0629229135315"><td class="cellrowborder" valign="top" width="18.57%" headers="mcps1.2.3.1.1 "><p id="p2629102915319"><a name="p2629102915319"></a><a name="p2629102915319"></a><span class="parmname" id="parmname062962915312"><a name="parmname062962915312"></a><a name="parmname062962915312"></a>“部署类型”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="81.43%" headers="mcps1.2.3.1.2 "><p id="p86291429165319"><a name="p86291429165319"></a><a name="p86291429165319"></a>导入模型后，选择此模型支持部署服务的类型，部署上线时只支持部署为此处选择的部署类型，例如此处只选择在线服务，那您的导入后只能部署为在线服务。当前支持<span class="parmname" id="parmname18636552133915"><a name="parmname18636552133915"></a><a name="parmname18636552133915"></a>“在线服务”</span>、<span class="parmname" id="parmname586325510392"><a name="parmname586325510392"></a><a name="parmname586325510392"></a>“批量服务”</span>和<span class="parmname" id="parmname8348358173918"><a name="parmname8348358173918"></a><a name="parmname8348358173918"></a>“边缘服务”</span>。</p>
        </td>
        </tr>
        <tr id="row10630102912539"><td class="cellrowborder" valign="top" width="18.57%" headers="mcps1.2.3.1.1 "><p id="p14629152935312"><a name="p14629152935312"></a><a name="p14629152935312"></a><span class="parmname" id="parmname9629929185316"><a name="parmname9629929185316"></a><a name="parmname9629929185316"></a>“配置文件”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="81.43%" headers="mcps1.2.3.1.2 "><p id="p763012911534"><a name="p763012911534"></a><a name="p763012911534"></a>系统默认关联您存储在OBS中的配置文件。打开开关，您可以直接在当前界面查看、编辑或从OBS导入您的模型配置文件。</p>
        </td>
        </tr>
        <tr id="row563010299534"><td class="cellrowborder" valign="top" width="18.57%" headers="mcps1.2.3.1.1 "><p id="p1863082919538"><a name="p1863082919538"></a><a name="p1863082919538"></a><span class="parmname" id="parmname86301229105319"><a name="parmname86301229105319"></a><a name="parmname86301229105319"></a>“参数配置”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="81.43%" headers="mcps1.2.3.1.2 "><p id="p863011299536"><a name="p863011299536"></a><a name="p863011299536"></a>单击右侧的<a name="image9630162935316"></a><a name="image9630162935316"></a><span><img id="image9630162935316" src="figures/zh-cn_image_0207659170.png"></span>，查看当前模型的入参和出参。</p>
        </td>
        </tr>
        <tr id="row3630102914534"><td class="cellrowborder" valign="top" width="18.57%" headers="mcps1.2.3.1.1 "><p id="p1463072914538"><a name="p1463072914538"></a><a name="p1463072914538"></a><span class="parmname" id="parmname063018295533"><a name="parmname063018295533"></a><a name="parmname063018295533"></a>“运行时依赖”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="81.43%" headers="mcps1.2.3.1.2 "><p id="p463032985316"><a name="p463032985316"></a><a name="p463032985316"></a>罗列选中模型对环境的依赖。例如依赖<span class="parmvalue" id="parmvalue1863018295535"><a name="parmvalue1863018295535"></a><a name="parmvalue1863018295535"></a>“tensorflow”</span>，安装方式为<span class="parmvalue" id="parmvalue1263052919532"><a name="parmvalue1263052919532"></a><a name="parmvalue1263052919532"></a>“pip”</span>，其版本必须为1.8.0及以上版本。</p>
        </td>
        </tr>
        </tbody>
        </table>

    3.  设置推理规格和模型说明。
        -   “最小推理规格“：如果您的模型需要一定的规格资源才能完成推理，您可以在此配置自定义推理规格，即您的模型部署上线进行正常推理所需要的规格，后续版本部署上线时系统将会参考您填写的推理规格来分配资源，部署时可视情况修改该规格。需要注意的是此处自定义的规格，仅在部署在线服务且使用专属资源池、部署边缘这两种场景有效。
        -   “模型说明“：为了帮助其他模型开发者更好的理解及使用您的模型，建议您提供模型的说明文档。单击“增加模型说明“，设置“文档名称“及其“URL“。模型说明支持增加多条。

            **图 2**  推理规格和模型说明<a name="fig1568815910313"></a>  
            ![](figures/推理规格和模型说明-16.png "推理规格和模型说明-16")

    4.  确认信息填写无误，单击“立即创建“，完成模型导入。

        在模型列表中，您可以查看刚导入的模型及其对应的版本。当模型状态变更为“正常“时，表示模型导入成功。在此页面，您还可以创建新版本、快速部署模型、将模型发布至市场、导出模型等操作。



## 后续操作<a name="section67499327247"></a>

-   **[部署模型](模型部署简介.md)**：在“模型列表“中，单击模型名称左侧的小三角，打开此模型下的所有版本。在对应版本所在行，单击“操作“列的“部署“，在下拉框中选择部署类型，可以将模型部署上线为导入模型时所选择的部署类型。在部署服务的页面，详细参数填写请参见[模型部署简介](模型部署简介.md)的相关指导。

