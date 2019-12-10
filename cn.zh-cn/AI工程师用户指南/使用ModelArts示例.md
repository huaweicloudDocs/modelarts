# 使用ModelArts示例<a name="modelarts_23_0036"></a>

ModelArts提供了Notebook示例，方便初学者通过示例，快速了解如何使用ModelArts Notebook。

>![](public_sys-resources/icon-note.gif) **说明：**   
>Jupyter Notebook示例使用nbexamples扩展，有关nbexamples扩展的更多信息，请参阅[https://github.com/danielballan/nbexamples](https://github.com/danielballan/nbexamples)。  

## 预览ModelArts Examples<a name="section660215533344"></a>

1.  在Notebook列表中，创建并打开一个Notebook，或者直接打开已有的Notebook。
2.  在Jupyter页面中，单击“ModelArts Examples“页签，此页面罗列了“Machine Learning Introduction“和“ModelArts Python Sdk“的示例。ModelArts提供的所有示例说明如[表1](#table718212719302)和[表2](#table8618152103019)所示。每个示例提供了详细的说明，您可以单击右侧的“Preview“预览示例。

    **图 1**  进入ModelArts Examples<a name="fig11846161253913"></a>  
    ![](figures/进入ModelArts-Examples.png "进入ModelArts-Examples")

    **表 1**  Machine learning introduction示例

    <a name="table718212719302"></a>
    <table><thead align="left"><tr id="row122957773019"><th class="cellrowborder" valign="top" width="36.78%" id="mcps1.2.3.1.1"><p id="p1229516793016"><a name="p1229516793016"></a><a name="p1229516793016"></a><strong id="b11605161314319"><a name="b11605161314319"></a><a name="b11605161314319"></a>示例名称</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="63.22%" id="mcps1.2.3.1.2"><p id="p1429515714306"><a name="p1429515714306"></a><a name="p1429515714306"></a><strong id="b12950773019"><a name="b12950773019"></a><a name="b12950773019"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1629557183020"><td class="cellrowborder" valign="top" width="36.78%" headers="mcps1.2.3.1.1 "><p id="p9295117163018"><a name="p9295117163018"></a><a name="p9295117163018"></a>mxnet_mnist_digit_recognition_train.ipynb</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.22%" headers="mcps1.2.3.1.2 "><p id="p62951274300"><a name="p62951274300"></a><a name="p62951274300"></a>本示例介绍使用MXNet实现MNIST数据集的手写数字图像识别应用，主要是完成训练脚本的开发。</p>
    </td>
    </tr>
    <tr id="row102959715304"><td class="cellrowborder" valign="top" width="36.78%" headers="mcps1.2.3.1.1 "><p id="p72951719309"><a name="p72951719309"></a><a name="p72951719309"></a>mxnet_object_detection.ipynb</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.22%" headers="mcps1.2.3.1.2 "><p id="p1229620718308"><a name="p1229620718308"></a><a name="p1229620718308"></a>本示例基于MXNet引擎搭建目标检测yolo-v3模型， 将其应用到华为云吉祥物"云宝"的检测中。</p>
    </td>
    </tr>
    <tr id="row192968793017"><td class="cellrowborder" valign="top" width="36.78%" headers="mcps1.2.3.1.1 "><p id="p162961376301"><a name="p162961376301"></a><a name="p162961376301"></a>sklearn_bank_loan_prediction_bayes_classification.ipynb</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.22%" headers="mcps1.2.3.1.2 "><p id="p22967743017"><a name="p22967743017"></a><a name="p22967743017"></a>本示例基于XGBoost-Sklearn的Naive Bayes（朴素贝叶斯）分类器，预测客户是否有银行贷款的意向。</p>
    </td>
    </tr>
    <tr id="row1296117163014"><td class="cellrowborder" valign="top" width="36.78%" headers="mcps1.2.3.1.1 "><p id="p18296773308"><a name="p18296773308"></a><a name="p18296773308"></a>sklearn_collaborative_filtering_for_movie_recommender.ipynb</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.22%" headers="mcps1.2.3.1.2 "><p id="p42965718309"><a name="p42965718309"></a><a name="p42965718309"></a>本示例基于XGBoost-Sklearn引擎计算相似矩阵，结合影评数据集实现电影推荐系统。</p>
    </td>
    </tr>
    <tr id="row20296575305"><td class="cellrowborder" valign="top" width="36.78%" headers="mcps1.2.3.1.1 "><p id="p132962714303"><a name="p132962714303"></a><a name="p132962714303"></a>sklearn_diabetes_prediciton_logistic_regression.ipynb</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.22%" headers="mcps1.2.3.1.2 "><p id="p229613718307"><a name="p229613718307"></a><a name="p229613718307"></a>本示例基于XGBoost-Sklearn逻辑回归（Logistic Regression）, 预测人们是否患糖尿病。</p>
    </td>
    </tr>
    <tr id="row1829613723015"><td class="cellrowborder" valign="top" width="36.78%" headers="mcps1.2.3.1.1 "><p id="p52961713302"><a name="p52961713302"></a><a name="p52961713302"></a>sklearn_image_compression_k-means_clustering.ipynb</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.22%" headers="mcps1.2.3.1.2 "><p id="p929610718301"><a name="p929610718301"></a><a name="p929610718301"></a>本示例基于XGBoost-Sklearn聚类算法k-means实现对图像的压缩。</p>
    </td>
    </tr>
    <tr id="row92965763017"><td class="cellrowborder" valign="top" width="36.78%" headers="mcps1.2.3.1.1 "><p id="p1129715714307"><a name="p1129715714307"></a><a name="p1129715714307"></a>tensorflow_image_segmentation_with_mask_rcnn_py36.ipynb</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.22%" headers="mcps1.2.3.1.2 "><p id="p13297178306"><a name="p13297178306"></a><a name="p13297178306"></a>本示例基于TensorFlow实现对Mask-RCNN模型进行训练，实现图像分割。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2**  ModelArts Python SDK示例

    <a name="table8618152103019"></a>
    <table><thead align="left"><tr id="row8702185213015"><th class="cellrowborder" valign="top" width="36.75%" id="mcps1.2.3.1.1"><p id="p7702652113015"><a name="p7702652113015"></a><a name="p7702652113015"></a><strong id="b207231823116"><a name="b207231823116"></a><a name="b207231823116"></a>示例名称</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="63.24999999999999%" id="mcps1.2.3.1.2"><p id="p177021852143020"><a name="p177021852143020"></a><a name="p177021852143020"></a><strong id="b3702175218309"><a name="b3702175218309"></a><a name="b3702175218309"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1170245218304"><td class="cellrowborder" valign="top" width="36.75%" headers="mcps1.2.3.1.1 "><p id="p57028524309"><a name="p57028524309"></a><a name="p57028524309"></a>mxnet_face_recognition.ipynb</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.24999999999999%" headers="mcps1.2.3.1.2 "><p id="p5702165216304"><a name="p5702165216304"></a><a name="p5702165216304"></a>本示例基于Modelarts SDK功能，利用MXNet引擎，端到端实现人脸识别项目的一站式开发。</p>
    </td>
    </tr>
    <tr id="row170275253020"><td class="cellrowborder" valign="top" width="36.75%" headers="mcps1.2.3.1.1 "><p id="p2070212524308"><a name="p2070212524308"></a><a name="p2070212524308"></a>mxnet_mnist_digit_recognition.ipynb</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.24999999999999%" headers="mcps1.2.3.1.2 "><p id="p57031052183016"><a name="p57031052183016"></a><a name="p57031052183016"></a>本示例基于Modelarts SDK功能，利用MXNet引擎，端到端实现手写数字识别项目的一站式开发，包括数据管理、提交训练作业、导入模型、部署在线服务和在线预测。</p>
    </td>
    </tr>
    <tr id="row170375219304"><td class="cellrowborder" valign="top" width="36.75%" headers="mcps1.2.3.1.1 "><p id="p1070318522308"><a name="p1070318522308"></a><a name="p1070318522308"></a>obs_management_with_sdk.ipynb</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.24999999999999%" headers="mcps1.2.3.1.2 "><p id="p10703352183015"><a name="p10703352183015"></a><a name="p10703352183015"></a>本示例基于Modelarts SDK的OBS管理功能，展示SDK对OBS的增删改等操作。</p>
    </td>
    </tr>
    <tr id="row177031052103014"><td class="cellrowborder" valign="top" width="36.75%" headers="mcps1.2.3.1.1 "><p id="p117039521303"><a name="p117039521303"></a><a name="p117039521303"></a>pytorch_text_sentiment_analysis_py36.ipynb</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.24999999999999%" headers="mcps1.2.3.1.2 "><p id="p12703165293016"><a name="p12703165293016"></a><a name="p12703165293016"></a>本示例基于PyTorch引擎训练模型，实现文本情感分析。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 使用ModelArts Examples<a name="section179798012258"></a>

在Jupyter界面中使用或查看Notebook示例。

1.  在Notebook列表中，创建并打开一个Notebook，或者直接打开已有的Notebook。
2.  在Jupyter页面中，单击“ModelArts Examples“页签，选择需要使用的示例，单击示例右侧的“Use“。
3.  在弹出的“Create a copy in your home directory“对话框中，设置新的“ipynb“文件名称，也可以直接使用默认文件，然后单击“Create copy“保存并打开新的“ipynb“文件。打开的示例文件如[图3](#fig32848815484)所示。

    使用示例是指将示例文件创建一个副本，其代码内容与示例一致。

    **图 2**  创建示例副本<a name="fig113948242468"></a>  
    ![](figures/创建示例副本.png "创建示例副本")

    **图 3**  打开示例文件<a name="fig32848815484"></a>  
    ![](figures/打开示例文件.png "打开示例文件")


