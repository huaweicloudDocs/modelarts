# 将MLS业务迁移至ModelArts<a name="modelarts_23_0129"></a>

由于MLS服务即将下线，建议您在ModelArts服务中使用ML Studio相关的功能。为保证用户的业务数据正常运行，建议您参考如下操作指导完成迁移。

## 数据迁移<a name="section872861153"></a>

MLS专属版支持将数据保存在HDFS，MLS标准版支持将数据保存在数据集和OBS。ML Studio将数据读入写出统一为OBS，因此MLS数据保存的操作需要您手动迁移，需要将原数据上传到OBS。

创建OBS桶和文件夹的操作指导请参见[创建桶](https://support.huaweicloud.com/usermanual-obs/zh-cn_topic_0045829088.html)和[新建文件夹](https://support.huaweicloud.com/usermanual-obs/zh-cn_topic_0045829103.html)。

OBS上传文件的操作指导，请参见[上传文件](https://support.huaweicloud.com/usermanual-obs/zh-cn_topic_0045829661.html)。

>![](public_sys-resources/icon-note.gif) **说明：**   
>为方便业务迁移至ModelArts服务时直接使用，建议您创建OBS桶和文件夹路径与原来MLS服务存放的数据路径一致。  

在OBS服务中创建桶和文件夹，将MLS业务的数据和模型上传至新建的OBS桶中。

## 工作流迁移<a name="section13167207111111"></a>

ML Studio与MLS的工作流能力完全一致。由于支持的数据源有变更，导致数据读入、写出相关的算子有变化，需要用户根据自己工作流所涉及的算子，对涉及到的算子工作流进行重新编排。具体算子变更请参见[表1](#table12524324122013)和[表2](#table1366217523417)。其中“从OBS读取模型”和“保存模型到OBS”只支持“inner“格式的模型。

**表 1**  MLS专属版与ML Studio算子变化

<a name="table12524324122013"></a>
<table><thead align="left"><tr id="row55261424172011"><th class="cellrowborder" valign="top" width="21.27%" id="mcps1.2.4.1.1"><p id="p2018283712449"><a name="p2018283712449"></a><a name="p2018283712449"></a>算子所属类别</p>
</th>
<th class="cellrowborder" valign="top" width="40.71%" id="mcps1.2.4.1.2"><p id="p115261824172013"><a name="p115261824172013"></a><a name="p115261824172013"></a>MLS专属版算子</p>
</th>
<th class="cellrowborder" valign="top" width="38.019999999999996%" id="mcps1.2.4.1.3"><p id="p1352632415207"><a name="p1352632415207"></a><a name="p1352632415207"></a>ML Studio算子</p>
</th>
</tr>
</thead>
<tbody><tr id="row15271247205"><td class="cellrowborder" rowspan="5" valign="top" width="21.27%" headers="mcps1.2.4.1.1 "><p id="p15837358101311"><a name="p15837358101311"></a><a name="p15837358101311"></a>输入</p>
</td>
<td class="cellrowborder" valign="top" width="40.71%" headers="mcps1.2.4.1.2 "><p id="p652792452016"><a name="p652792452016"></a><a name="p652792452016"></a><a name="image1078833782314"></a><a name="image1078833782314"></a><span><img id="image1078833782314" src="figures/zh-cn_image_0182563331.png"></span>读取模型</p>
</td>
<td class="cellrowborder" valign="top" width="38.019999999999996%" headers="mcps1.2.4.1.3 "><p id="p7163668343"><a name="p7163668343"></a><a name="p7163668343"></a><a name="image31639663419"></a><a name="image31639663419"></a><span><img id="image31639663419" src="figures/OBSModelReader.png" width="52.8675" height="52.8675"></span>从OBS读取模型</p>
</td>
</tr>
<tr id="row135272024102013"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p45271524142012"><a name="p45271524142012"></a><a name="p45271524142012"></a><a name="image109557642420"></a><a name="image109557642420"></a><span><img id="image109557642420" src="figures/zh-cn_image_0182563355.png"></span>读取PMML模型文件</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p8527132432018"><a name="p8527132432018"></a><a name="p8527132432018"></a>不支持</p>
</td>
</tr>
<tr id="row115271524112011"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p5527724112014"><a name="p5527724112014"></a><a name="p5527724112014"></a><a name="image1971112375248"></a><a name="image1971112375248"></a><span><img id="image1971112375248" src="figures/zh-cn_image_0182563415.png"></span>读取Hive表</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p55272244208"><a name="p55272244208"></a><a name="p55272244208"></a>不支持</p>
</td>
</tr>
<tr id="row18527824172020"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1952732412014"><a name="p1952732412014"></a><a name="p1952732412014"></a><a name="image1634617215252"></a><a name="image1634617215252"></a><span><img id="image1634617215252" src="figures/zh-cn_image_0182563439.png"></span>读取HDFS文件</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p9902124911510"><a name="p9902124911510"></a><a name="p9902124911510"></a><a name="image5283153322"></a><a name="image5283153322"></a><span><img id="image5283153322" src="figures/OBSReader.png" width="51.870000000000005" height="51.870000000000005"></span>从OBS读取数据</p>
</td>
</tr>
<tr id="row8527524112018"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1252792492016"><a name="p1252792492016"></a><a name="p1252792492016"></a><a name="image215330132515"></a><a name="image215330132515"></a><span><img id="image215330132515" src="figures/zh-cn_image_0182563465.png"></span>读取文本文件</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1935054573518"><a name="p1935054573518"></a><a name="p1935054573518"></a><a name="image1635084515359"></a><a name="image1635084515359"></a><span><img id="image1635084515359" src="figures/OBSTextReader.png" width="50.8725" height="50.8725"></span>从OBS读取文本</p>
</td>
</tr>
<tr id="row05191644143420"><td class="cellrowborder" rowspan="4" valign="top" width="21.27%" headers="mcps1.2.4.1.1 "><p id="p14861142114520"><a name="p14861142114520"></a><a name="p14861142114520"></a>输出</p>
</td>
<td class="cellrowborder" valign="top" width="40.71%" headers="mcps1.2.4.1.2 "><p id="p205191644133413"><a name="p205191644133413"></a><a name="p205191644133413"></a><a name="image4464165018268"></a><a name="image4464165018268"></a><span><img id="image4464165018268" src="figures/zh-cn_image_0182563509.png"></span>保存HDFS文件</p>
</td>
<td class="cellrowborder" valign="top" width="38.019999999999996%" headers="mcps1.2.4.1.3 "><p id="p1243244916371"><a name="p1243244916371"></a><a name="p1243244916371"></a><a name="image44322495378"></a><a name="image44322495378"></a><span><img id="image44322495378" src="figures/OBSWriter.png" width="51.870000000000005" height="51.870000000000005"></span>保存数据到OBS</p>
</td>
</tr>
<tr id="row780245413415"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p17802254133417"><a name="p17802254133417"></a><a name="p17802254133417"></a><a name="image10140331202710"></a><a name="image10140331202710"></a><span><img id="image10140331202710" src="figures/zh-cn_image_0182563594.png"></span>保存PMML模型文件</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p175481225103111"><a name="p175481225103111"></a><a name="p175481225103111"></a>不支持</p>
</td>
</tr>
<tr id="row205139504373"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p951465063715"><a name="p951465063715"></a><a name="p951465063715"></a><a name="image20163572289"></a><a name="image20163572289"></a><span><img id="image20163572289" src="figures/zh-cn_image_0182563577.png"></span>保存模型</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p182555317399"><a name="p182555317399"></a><a name="p182555317399"></a><a name="image21451232134313"></a><a name="image21451232134313"></a><span><img id="image21451232134313" src="figures/zh-cn_image_0182573038.png"></span>保存模型至OBS</p>
</td>
</tr>
<tr id="row53889552379"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p738815523715"><a name="p738815523715"></a><a name="p738815523715"></a><a name="image1010114384287"></a><a name="image1010114384287"></a><span><img id="image1010114384287" src="figures/zh-cn_image_0182563678.png"></span>保存Hive表</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p12308150785"><a name="p12308150785"></a><a name="p12308150785"></a>不支持</p>
</td>
</tr>
</tbody>
</table>

**表 2**  MLS标准版与ML Studio算子变化

<a name="table1366217523417"></a>
<table><thead align="left"><tr id="row8662175254117"><th class="cellrowborder" valign="top" width="23.022302230223023%" id="mcps1.2.4.1.1"><p id="p166632523413"><a name="p166632523413"></a><a name="p166632523413"></a>算子所属类别</p>
</th>
<th class="cellrowborder" valign="top" width="39.49394939493949%" id="mcps1.2.4.1.2"><p id="p366315216415"><a name="p366315216415"></a><a name="p366315216415"></a>MLS标准版算子</p>
</th>
<th class="cellrowborder" valign="top" width="37.48374837483748%" id="mcps1.2.4.1.3"><p id="p366314528419"><a name="p366314528419"></a><a name="p366314528419"></a>ML Studio算子</p>
</th>
</tr>
</thead>
<tbody><tr id="row1318311281873"><td class="cellrowborder" rowspan="4" valign="top" width="23.022302230223023%" headers="mcps1.2.4.1.1 "><p id="p11184228779"><a name="p11184228779"></a><a name="p11184228779"></a>输入</p>
</td>
<td class="cellrowborder" valign="top" width="39.49394939493949%" headers="mcps1.2.4.1.2 "><p id="p155463661017"><a name="p155463661017"></a><a name="p155463661017"></a><a name="image555416368108"></a><a name="image555416368108"></a><span><img id="image555416368108" src="figures/CloudTableReader.png"></span>   从表格存储服务读取数据</p>
</td>
<td class="cellrowborder" valign="top" width="37.48374837483748%" headers="mcps1.2.4.1.3 "><p id="p17184152814720"><a name="p17184152814720"></a><a name="p17184152814720"></a>不支持</p>
</td>
</tr>
<tr id="row1266355214114"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1166325234115"><a name="p1166325234115"></a><a name="p1166325234115"></a><a name="image17215105162912"></a><a name="image17215105162912"></a><span><img id="image17215105162912" src="figures/zh-cn_image_0182564360.png"></span>从数据集读取数据</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p205901198523"><a name="p205901198523"></a><a name="p205901198523"></a><a name="image53979270323"></a><a name="image53979270323"></a><span><img id="image53979270323" src="figures/OBSReader-21.png" width="51.870000000000005" height="51.870000000000005"></span>从OBS读取数据</p>
</td>
</tr>
<tr id="row166325213414"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2663175214419"><a name="p2663175214419"></a><a name="p2663175214419"></a><a name="image1295914614291"></a><a name="image1295914614291"></a><span><img id="image1295914614291" src="figures/zh-cn_image_0182564382.png"></span>读取模型</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1340412341273"><a name="p1340412341273"></a><a name="p1340412341273"></a><a name="image1425613395340"></a><a name="image1425613395340"></a><span><img id="image1425613395340" src="figures/OBSModelReader-22.png" width="52.8675" height="52.8675"></span>从OBS读取模型</p>
</td>
</tr>
<tr id="row66631452184118"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p966318522410"><a name="p966318522410"></a><a name="p966318522410"></a><a name="image1127111117308"></a><a name="image1127111117308"></a><span><img id="image1127111117308" src="figures/zh-cn_image_0182564383.png"></span>从数据集读取文本</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1266315284111"><a name="p1266315284111"></a><a name="p1266315284111"></a><a name="image97928141367"></a><a name="image97928141367"></a><span><img id="image97928141367" src="figures/OBSTextReader-23.png" width="50.8725" height="50.8725"></span>从OBS读取文本</p>
</td>
</tr>
<tr id="row17137717141019"><td class="cellrowborder" rowspan="2" valign="top" width="23.022302230223023%" headers="mcps1.2.4.1.1 "><p id="p146501059193211"><a name="p146501059193211"></a><a name="p146501059193211"></a>输出</p>
</td>
<td class="cellrowborder" valign="top" width="39.49394939493949%" headers="mcps1.2.4.1.2 "><p id="p7137171715106"><a name="p7137171715106"></a><a name="p7137171715106"></a><a name="image1796842617308"></a><a name="image1796842617308"></a><span><img id="image1796842617308" src="figures/zh-cn_image_0182564384.png"></span>保存数据到数据集</p>
</td>
<td class="cellrowborder" valign="top" width="37.48374837483748%" headers="mcps1.2.4.1.3 "><p id="p8733184371117"><a name="p8733184371117"></a><a name="p8733184371117"></a><a name="image17132182183812"></a><a name="image17132182183812"></a><span><img id="image17132182183812" src="figures/OBSWriter-24.png" width="51.870000000000005" height="51.870000000000005"></span>保存数据到OBS</p>
</td>
</tr>
<tr id="row3294122111010"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p8294182114106"><a name="p8294182114106"></a><a name="p8294182114106"></a><a name="image1530775973019"></a><a name="image1530775973019"></a><span><img id="image1530775973019" src="figures/zh-cn_image_0182564176.png"></span>保存模型</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1329416214106"><a name="p1329416214106"></a><a name="p1329416214106"></a><a name="image1196954484315"></a><a name="image1196954484315"></a><span><img id="image1196954484315" src="figures/zh-cn_image_0182573165.png"></span>保存模型到OBS</p>
</td>
</tr>
</tbody>
</table>

## Notebook迁移<a name="section42835485153"></a>

ModelArts Notebook为您提供更好用的代码编辑功能，可将MLS的Notebook脚本下载到本地，然后上传到ModelArts上继续使用。该部分迁移包括Notebook数据迁移和Notebook代码迁移。

**Notebook数据迁移**

MLS专属版Notebook模块将数据保存在HDFS，MLS标准版notebook模块将数据保存在OBS。Notebook需要将原数据上传到OBS。请参见[数据迁移](#section872861153)。

**Notebook代码迁移**

具体步骤如下：

1.  登录ModelArts管理控制台，在左侧菜单栏中选择“开发环境\>Notebook“，进入“Notebook“管理页面。
2.  单击“创建“进入“创建Notebook“页面，如[图1](#fig88718193235)所示，工作环境选择“Python2“，存储配置选择“OBS“。其他参数配置请参见[创建并打开Notebook](创建并打开Notebook.md)。

    **图 1**  创建Notebook示例<a name="fig88718193235"></a>  
    ![](figures/创建Notebook示例.png "创建Notebook示例")

3.  下载MLS服务中的Notebook脚本，格式为“.ipynb“。

    **图 2**  下载Notebook脚本<a name="fig12620121113243"></a>  
    ![](figures/下载Notebook脚本.png "下载Notebook脚本")

4.  上传“.ipynb“文件至Notebook开发环境。

    **图 3**  上传脚本至Notebook<a name="fig742916502517"></a>  
    ![](figures/上传脚本至Notebook.png "上传脚本至Notebook")

5.  单击打开“.ipynb“文件，设置Kernel环境，选择“Conda-python2“。单击“Set Kernel“完成设置，即可使用“.ipynb“文件。

    **图 4**  设置Kernel环境<a name="fig1647451132713"></a>  
    ![](figures/设置Kernel环境.png "设置Kernel环境")


>![](public_sys-resources/icon-note.gif) **说明：**   
>在Notebook开发环境中如何操作OBS中的文件，详请参见[MoXing-公共组件](https://github.com/huaweicloud/ModelArts-Lab/blob/master/docs/moxing_api_doc/MoXing_API_File.md)。  

