# 使用自定义算法在ModelArts上构建模型<a name="modelarts_10_0080"></a>

本文为用户提供如何将本地的自定义算法通过简单的代码适配，实现在ModelArts上进行模型训练与部署的全流程指导。

开始使用如下样例前，请务必按[准备工作](#section51133584536)指导完成必要操作。本指导以使用TensorFlow实现手写数字图像识别的样例为示例。

1.  **[准备数据](#section336312088)**：获取MNIST数据集，并上传至OBS。
2.  **[适配算法代码](#section43965832218)**：改造本地算法代码适配ModelArts云上训练。
3.  **[上传算法](#section3935113774214)**：将本地开发的算法上传至ModelArts。
4.  **[训练模型](#section42320342266)**：使用上传的算法进行模型训练。
5.  **[部署模型](#section740614592308)**：训练结束后，将模型导入ModelArts，并将模型部署为在线服务。
6.  **[预测结果](#section9961181112311)**：发起预测请求获取预测结果。

## 准备工作<a name="section51133584536"></a>

-   已注册华为云帐号，且在使用ModelArts前检查帐号状态，帐号不能处于欠费或冻结状态。
-   当前帐号已完成访问授权的配置。如未完成，请参考[使用委托授权](https://support.huaweicloud.com/prepare-modelarts/modelarts_08_0007.html)**。**针对之前使用访问密钥授权的用户，建议清空授权，然后使用委托进行授权。
-   已在OBS服务中创建桶和文件夹，用于存放样例数据集以及模型。如下示例中，请创建命名为“test-modelarts“的桶，并创建如[表1](#zh-cn_topic_0168474775_table2061005120337)所示的文件夹。

    创建OBS桶和文件夹的操作指导请参见[创建桶](https://support.huaweicloud.com/usermanual-obs/obs_03_0306.html)和[新建文件夹](https://support.huaweicloud.com/usermanual-obs/obs_03_0316.html)。请确保您使用的OBS与ModelArts在同一区域。

    **表 1**  文件夹列表

    <a name="zh-cn_topic_0168474775_table2061005120337"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0168474775_row1860945116333"><th class="cellrowborder" valign="top" width="31.180000000000003%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0168474775_p10609195123319"><a name="zh-cn_topic_0168474775_p10609195123319"></a><a name="zh-cn_topic_0168474775_p10609195123319"></a>文件夹名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="68.82000000000001%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0168474775_p206091751203312"><a name="zh-cn_topic_0168474775_p206091751203312"></a><a name="zh-cn_topic_0168474775_p206091751203312"></a>用途</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0168474775_row06099518334"><td class="cellrowborder" valign="top" width="31.180000000000003%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0168474775_p13609175110335"><a name="zh-cn_topic_0168474775_p13609175110335"></a><a name="zh-cn_topic_0168474775_p13609175110335"></a><span class="parmvalue" id="zh-cn_topic_0168474775_parmvalue86099516336"><a name="zh-cn_topic_0168474775_parmvalue86099516336"></a><a name="zh-cn_topic_0168474775_parmvalue86099516336"></a>“dataset-mnist”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="68.82000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0168474775_p1609205193315"><a name="zh-cn_topic_0168474775_p1609205193315"></a><a name="zh-cn_topic_0168474775_p1609205193315"></a>用于存储数据集。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0168474775_row1660955118338"><td class="cellrowborder" valign="top" width="31.180000000000003%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0168474775_p3609175193317"><a name="zh-cn_topic_0168474775_p3609175193317"></a><a name="zh-cn_topic_0168474775_p3609175193317"></a><span class="filepath" id="zh-cn_topic_0168474775_filepath1660918516339"><a name="zh-cn_topic_0168474775_filepath1660918516339"></a><a name="zh-cn_topic_0168474775_filepath1660918516339"></a>“mnist-tensorflow-code”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="68.82000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0168474775_p1360910519337"><a name="zh-cn_topic_0168474775_p1360910519337"></a><a name="zh-cn_topic_0168474775_p1360910519337"></a>用于存储训练脚本。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0168474775_row11609185115337"><td class="cellrowborder" valign="top" width="31.180000000000003%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0168474775_p460955193312"><a name="zh-cn_topic_0168474775_p460955193312"></a><a name="zh-cn_topic_0168474775_p460955193312"></a><span class="parmvalue" id="zh-cn_topic_0168474775_parmvalue166091551193319"><a name="zh-cn_topic_0168474775_parmvalue166091551193319"></a><a name="zh-cn_topic_0168474775_parmvalue166091551193319"></a>“mnist-model”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="68.82000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0168474775_p260919518338"><a name="zh-cn_topic_0168474775_p260919518338"></a><a name="zh-cn_topic_0168474775_p260919518338"></a>用于存储训练输出的模型和预测文件。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 准备数据<a name="section336312088"></a>

ModelArts在公共OBS桶中提供了MNIST数据集，命名为“Mnist-Data-Set“，因此，本文的操作示例使用此数据集进行模型构建。您需要执行如下操作，将数据集上传至您的OBS目录下，即准备工作中您创建的OBS目录“test-modelarts/dataset-mnist“。

1.  单击[数据集下载链接](https://modelarts-cnnorth1-market-dataset.obs.cn-north-1.myhuaweicloud.com/dataset-market/Mnist-Data-Set/archiver/Mnist-Data-Set.zip)，将“Mnist-Data-Set“数据集下载至本地。
2.  在本地，将“Mnist-Data-Set.zip“压缩包解压。例如，解压至本地“Mnist-Data-Set“文件夹下。
3.  参考[上传文件](https://support.huaweicloud.com/usermanual-obs/obs_03_0307.html)，使用批量上传方式将“Mnist-Data-Set“文件夹下的所有文件上传至“test-modelarts/dataset-mnist“OBS路径下。

    “Mnist-Data-Set“数据集包含的内容如下所示，其中“.gz“为对应的压缩包。

    -   “t10k-images-idx3-ubyte“：验证集，共包含10000个样本。
    -   “t10k-images-idx3-ubyte.gz“：验证集的压缩包文件。
    -   “t10k-labels-idx1-ubyte“：验证集标签，共包含10000个样本的类别标签。
    -   “t10k-labels-idx1-ubyte.gz“：验证集标签的压缩包文件。
    -   “train-images-idx3-ubyte“：训练集，共包含60000个样本。
    -   “train-images-idx3-ubyte.gz“：训练集的压缩包文件。
    -   “train-labels-idx1-ubyte“：训练集标签，共包含60000个样本的类别标签。
    -   “train-labels-idx1-ubyte.gz“：训练集标签的压缩包文件。


## 适配算法代码<a name="section43965832218"></a>

数据准备完成后，您需要将本地代码进行简单的代码适配，详细操作参见[开发自定义脚本](https://support.huaweicloud.com/engineers-modelarts/modelarts_23_0240.html)指导。

针对此示例，ModelArts提供了部署上线需使用的训练脚本、推理代码和配置文件。请获取示例文件并上传OBS指定路径，详细请参见[表2](#table211713253816)。

1.  在gitee的[ModelArts-Lab](https://gitee.com/ModelArts/ModelArts-Lab)工程中，单击“克隆/下载“，然后单击“下载ZIP“，下载工程。
2.  下载完成后，解压缩“ModelArts-Lab-master.zip“文件，然后在“\\ModelArts-Lab-master\\official\_examples\\Using Custom Algorithms to Build Models on ModelArts\\codes“目录中获取到训练脚本“train\_mnist\_tf.py“、推理代码“customize\_service.py“和配置文件“config.json“，并上传至对应OBS路径。上传文件至OBS的操作指导请参见[上传文件](https://support.huaweicloud.com/usermanual-obs/obs_03_0307.html)。

    **表 2**  上传示例文件至OBS

    <a name="table211713253816"></a>
    <table><thead align="left"><tr id="row51177223814"><th class="cellrowborder" valign="top" width="28.342834283428342%" id="mcps1.2.4.1.1"><p id="p1111712263813"><a name="p1111712263813"></a><a name="p1111712263813"></a>文件名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="20.282028202820282%" id="mcps1.2.4.1.2"><p id="p811715273817"><a name="p811715273817"></a><a name="p811715273817"></a>描述</p>
    </th>
    <th class="cellrowborder" valign="top" width="51.375137513751376%" id="mcps1.2.4.1.3"><p id="p18117192153812"><a name="p18117192153812"></a><a name="p18117192153812"></a>上传至如下OBS路径中</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1311712163811"><td class="cellrowborder" valign="top" width="28.342834283428342%" headers="mcps1.2.4.1.1 "><p id="p81171627380"><a name="p81171627380"></a><a name="p81171627380"></a><span class="filepath" id="filepath1611720215387"><a name="filepath1611720215387"></a><a name="filepath1611720215387"></a>“train_mnist_tf.py”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="20.282028202820282%" headers="mcps1.2.4.1.2 "><p id="p91171213380"><a name="p91171213380"></a><a name="p91171213380"></a>训练脚本。</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.375137513751376%" headers="mcps1.2.4.1.3 "><p id="p1611772153819"><a name="p1611772153819"></a><a name="p1611772153819"></a><span class="parmvalue" id="parmvalue12117122103812"><a name="parmvalue12117122103812"></a><a name="parmvalue12117122103812"></a>“test-modelarts/mnist-tensorflow-code”</span></p>
    </td>
    </tr>
    <tr id="row18117192173817"><td class="cellrowborder" valign="top" width="28.342834283428342%" headers="mcps1.2.4.1.1 "><p id="p9117142153813"><a name="p9117142153813"></a><a name="p9117142153813"></a><span class="filepath" id="filepath1011710243814"><a name="filepath1011710243814"></a><a name="filepath1011710243814"></a>“customize_service.py”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="20.282028202820282%" headers="mcps1.2.4.1.2 "><p id="p121171220384"><a name="p121171220384"></a><a name="p121171220384"></a>推理代码。</p>
    </td>
    <td class="cellrowborder" rowspan="2" valign="top" width="51.375137513751376%" headers="mcps1.2.4.1.3 "><p id="p11171022385"><a name="p11171022385"></a><a name="p11171022385"></a><span class="parmvalue" id="parmvalue141171823385"><a name="parmvalue141171823385"></a><a name="parmvalue141171823385"></a>“test-modelarts/mnist-model/model”</span></p>
    <div class="note" id="note2011712153813"><a name="note2011712153813"></a><a name="note2011712153813"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul911719213387"></a><a name="ul911719213387"></a><ul id="ul911719213387"><li>请在训练作业完成后，再执行上传操作。</li><li>如果训练作业运行多次，将生成不同的版本，<span class="filepath" id="filepath1711702123812"><a name="filepath1711702123812"></a><a name="filepath1711702123812"></a>“mnist-model”</span>目录下将生成多种版本的目录，如<span class="filepath" id="filepath15117152183811"><a name="filepath15117152183811"></a><a name="filepath15117152183811"></a>“V0001”</span>、<span class="filepath" id="filepath19117142153818"><a name="filepath19117142153818"></a><a name="filepath19117142153818"></a>“V0002”</span>，请基于训练作业的版本，将文件上传至对应版本下的<span class="filepath" id="filepath911762193816"><a name="filepath911762193816"></a><a name="filepath911762193816"></a>“model”</span>文件夹内。</li></ul>
    </div></div>
    <p id="p71179220383"><a name="p71179220383"></a><a name="p71179220383"></a></p>
    <p id="p1249244414514"><a name="p1249244414514"></a><a name="p1249244414514"></a></p>
    </td>
    </tr>
    <tr id="row4492114485110"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0168474775_p43122427380"><a name="zh-cn_topic_0168474775_p43122427380"></a><a name="zh-cn_topic_0168474775_p43122427380"></a><span class="filepath" id="zh-cn_topic_0168474775_filepath1541113212394"><a name="zh-cn_topic_0168474775_filepath1541113212394"></a><a name="zh-cn_topic_0168474775_filepath1541113212394"></a>“config.json”</span></p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p10492444155113"><a name="p10492444155113"></a><a name="p10492444155113"></a>配置文件。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 创建算法<a name="section3935113774214"></a>

1.  在ModelArts管理控制台，进入“算法管理\>我的算法“页面，单击左上角的“创建“。
2.  在创建算法页面，请参考[图1](#fig139640311383)和[图2](#fig13964163193817)填写相关信息。
    -   “AI引擎“：Tensorflow,TF-1.8.0-python3.6
    -   “代码目录“：选择[准备工作](#section51133584536)中已创建的代码目录路径“test-modelarts/mnist-tensorflow-code“。
    -   “启动文件“：选择代码目录下上传的训练脚本“train\_mnist\_tf.py“。

        **图 1**  创建算法-填写基本信息<a name="fig139640311383"></a>  
        ![](figures/创建算法-填写基本信息.png "创建算法-填写基本信息")

        **图 2**  创建算法-填写详细信息<a name="fig13964163193817"></a>  
        ![](figures/创建算法-填写详细信息.png "创建算法-填写详细信息")

3.  确认算法的参数信息，确认无误后单击“提交“。
4.  在“我的算法“页面，可单击算法名称，进入算法详情界面查看算法信息。

## 训练模型<a name="section42320342266"></a>

算法创建完成后，您需要使用如下操作训练模型。

1.  在ModelArts管理控制台，进入“训练管理 \> 训练作业（New）“页面，单击左上角的“创建“。
2.  在“创建训练作业“页面，参考[图3](#fig15868125515112)和[图4](#fig12869655141111)填写相关信息。
    -   “训练输入“：选择数据存储位置，然后选择数据集存储的OBS路径“test-modelarts/dataset-mnist“。
    -   “训练输出“：选择[准备工作](#section51133584536)中已创建好的OBS路径“test-modelarts/mnist-model/model“。

        **图 3**  创建训练作业-填写基本信息<a name="fig15868125515112"></a>  
        ![](figures/创建训练作业-填写基本信息.png "创建训练作业-填写基本信息")

        **图 4**  创建训练作业-填写详细参数<a name="fig12869655141111"></a>  
        ![](figures/创建训练作业-填写详细参数.png "创建训练作业-填写详细参数")

3.  确认训练作业的参数信息，确认无误后单击“提交“。
4.  在训练作业管理页面，当训练作业变为“运行成功“时，即完成了模型训练过程。如有问题，可单击作业名称，进入作业详情界面查看训练作业日志信息。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >训练作业需要花费一些时间，预计十几分钟。当训练时间超过一定时间（如1个小时），请及时手动停止，释放资源。否则会导致欠费，尤其对于使用GPU训练的模型项目。


## 部署模型<a name="section740614592308"></a>

模型训练完成后，可以创建预测作业，将模型部署为在线预测服务。在部署模型之前，获取推理代码“customize\_service.py“和配置文件“config.json“并上传至OBS中。此推理代码和配置文件为ModelArts为操作样例提供的示例。您也可以基于[模型包规范](https://support.huaweicloud.com/engineers-modelarts/modelarts_23_0091.html)，开发自己所需的推理代码及配置文件。

1.  在ModelArts管理控制台，单击左侧导航栏中的“模型管理\>模型“，进入“模型“页面，单击“导入“。
2.  在“导入模型“页面，参考[图5](#fig1391183516364)填写相关参数，然后单击“立即创建“。

    在“元模型来源“中，选择“从训练中选择\>训练作业（New）“页签。

    **图 5**  导入模型<a name="fig1391183516364"></a>  
    ![](figures/导入模型.png "导入模型")

    在“模型列表“页面，当模型状态变为“正常“时，表示模型已导入成功。

3.  单击模型名称左侧的小三角，打开此模型下的所有版本。在对应版本所在行，单击操作列“部署\>在线服务“，将模型部署为在线服务。

    在“部署“页面，参考[图6](#fig3534111012408)填写参数，然后根据界面提示完成在线服务创建。

    **图 6**  部署模型<a name="fig3534111012408"></a>  
    ![](figures/部署模型-8.png "部署模型-8")


## 预测结果<a name="section9961181112311"></a>

完成模型部署后，等待服务部署完成，当服务状态显示为“运行中“，表示服务已部署成功。

1.  在“在线服务“页面，单击在线服务名称，进入服务详情页面。
2.  单击“预测“页签，在“选择预测图片文件“右侧，单击“上传“按钮上传示例图片，然后单击“预测“。

    预测完成后，预测结果显示区域将展示预测结果，根据预测结果内容，可识别出此图片的数字是“2“。

    **图 7**  示例图片<a name="fig2405184623119"></a>  
    ![](figures/示例图片.png "示例图片")

    **图 8**  预测结果展示<a name="zh-cn_topic_0168474775_fig2049295319516"></a>  
    ![](figures/预测结果展示.png "预测结果展示")

3.  如果不再需要使用此模型及在线服务，建议清除相关资源，避免产生不必要的费用。
    -   在“在线服务“页面，“停止“或“删除“刚创建的在线服务。
    -   在“模型管理“页面，“删除“刚导入的模型。
    -   在“训练作业“页面，“删除“运行结束的训练作业。
    -   进入OBS，删除本示例使用的OBS桶及文件夹，以及文件夹的文件。


