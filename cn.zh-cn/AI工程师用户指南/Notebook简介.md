# Notebook简介<a name="modelarts_23_0033"></a>

ModelArts集成了基于开源的Jupyter Notebook，可为您提供在线的交互式开发调试工具。您无需关注安装配置，在ModelArts管理控制台直接使用Notebook，编写和调测模型训练代码，然后基于该代码进行模型的训练。

Jupyter Notebook是一个交互式笔记本，支持运行 40 多种编程语言。关于Jupyter Notebook的详细操作指导，请参见[Jupyter Notebook使用文档](https://jupyter.org/documentation)。

ModelArts还提供了华为自研的分布式训练加速框架MoXing，您可以在Notebook中使用MoXing编写训练脚本，让您代码编写更加高效、代码更加简洁。单击查看[MoXing使用手册](https://github.com/huaweicloud/ModelArts-Lab/tree/master/docs/moxing_api_doc)。

## 支持的AI引擎<a name="section191109611479"></a>

每个工作环境多种AI引擎，可以在同一个Notebook实例中使用所有支持的AI引擎，不同的引擎之间可快速、方便的切换，并且有独立的运行环境。其中，Conda-python2不包含任何AI引擎的基础Python2.7环境，Conda-python3不包含任何AI引擎的基础python3.6环境。

>![](public_sys-resources/icon-note.gif) **说明：**   
>由于ModelArts在2019年7月18日上线的多种AI引擎的Notebook，针对7月18日之前创建的Notebook实例，仍然使用的是单引擎类型的Notebook，例如TF-1.8.0-python3.6。针对7月18日之后创建的Notebook，直接采用的是多引擎的Notebook。单引擎Notebook和多引擎Notebook区别如下所示，推荐您将之前的单引擎Notebook实例尽快切换为多引擎Notebook。  
>-   单引擎Notebook：表示一个Notebook实例，只支持使用一种AI引擎。  
>-   多引擎Notebook：表示同一个Notebook实例，可以使用所有支持的AI引擎，不同引擎之间可快速、方便切换。  

**表 1**  AI引擎

<a name="table289615202493"></a>
<table><thead align="left"><tr id="row128981820114912"><th class="cellrowborder" valign="top" width="22.99%" id="mcps1.2.4.1.1"><p id="p5537182434911"><a name="p5537182434911"></a><a name="p5537182434911"></a>工作环境</p>
</th>
<th class="cellrowborder" valign="top" width="23.14%" id="mcps1.2.4.1.2"><p id="p1262117484495"><a name="p1262117484495"></a><a name="p1262117484495"></a>AI引擎</p>
</th>
<th class="cellrowborder" valign="top" width="53.87%" id="mcps1.2.4.1.3"><p id="p158981120164915"><a name="p158981120164915"></a><a name="p158981120164915"></a>版本</p>
</th>
</tr>
</thead>
<tbody><tr id="row989832016498"><td class="cellrowborder" rowspan="7" valign="top" width="22.99%" headers="mcps1.2.4.1.1 "><p id="p168601634124919"><a name="p168601634124919"></a><a name="p168601634124919"></a><strong id="b1470174312133"><a name="b1470174312133"></a><a name="b1470174312133"></a>Python2</strong></p>
</td>
<td class="cellrowborder" valign="top" width="23.14%" headers="mcps1.2.4.1.2 "><p id="p16865459194919"><a name="p16865459194919"></a><a name="p16865459194919"></a><span class="parmname" id="parmname2086515914491"><a name="parmname2086515914491"></a><a name="parmname2086515914491"></a>“TensorFlow”</span></p>
</td>
<td class="cellrowborder" valign="top" width="53.87%" headers="mcps1.2.4.1.3 "><a name="ul276016499121"></a><a name="ul276016499121"></a><ul id="ul276016499121"><li>TensorFlow-1.13.1</li><li>TensorFlow-1.8</li></ul>
</td>
</tr>
<tr id="row1898152017493"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p586595924911"><a name="p586595924911"></a><a name="p586595924911"></a><span class="parmname" id="parmname19865659204917"><a name="parmname19865659204917"></a><a name="parmname19865659204917"></a>“MXNet”</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p12898320174917"><a name="p12898320174917"></a><a name="p12898320174917"></a>MXNet-1.2.1</p>
</td>
</tr>
<tr id="row789882018493"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p13866125914499"><a name="p13866125914499"></a><a name="p13866125914499"></a><span class="parmname" id="parmname133219373564"><a name="parmname133219373564"></a><a name="parmname133219373564"></a>“Caffe”</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p8898720204913"><a name="p8898720204913"></a><a name="p8898720204913"></a>Caffe-1.0.0</p>
</td>
</tr>
<tr id="row10898162014912"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p686695920491"><a name="p686695920491"></a><a name="p686695920491"></a><span class="parmname" id="parmname1686685984914"><a name="parmname1686685984914"></a><a name="parmname1686685984914"></a>“Spark”</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p6898172024913"><a name="p6898172024913"></a><a name="p6898172024913"></a>PySpark-2.3.2</p>
</td>
</tr>
<tr id="row108981920184912"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p486645944918"><a name="p486645944918"></a><a name="p486645944918"></a><span class="parmname" id="parmname4866105944915"><a name="parmname4866105944915"></a><a name="parmname4866105944915"></a>“Scikit-learn &amp; XGBoost”</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p10898112010490"><a name="p10898112010490"></a><a name="p10898112010490"></a>XGBoost-Sklearn</p>
</td>
</tr>
<tr id="row889842024910"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1866759204916"><a name="p1866759204916"></a><a name="p1866759204916"></a><span class="parmname" id="parmname118661659154910"><a name="parmname118661659154910"></a><a name="parmname118661659154910"></a>“PyTorch”</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p489822074916"><a name="p489822074916"></a><a name="p489822074916"></a>PyTorch-1.0.0</p>
</td>
</tr>
<tr id="row112212387494"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p162217481498"><a name="p162217481498"></a><a name="p162217481498"></a><span class="parmname" id="parmname0768745773"><a name="parmname0768745773"></a><a name="parmname0768745773"></a>“Conda”</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p121231738154914"><a name="p121231738154914"></a><a name="p121231738154914"></a>Conda-python2</p>
</td>
</tr>
<tr id="row14123143894917"><td class="cellrowborder" rowspan="6" valign="top" width="22.99%" headers="mcps1.2.4.1.1 "><p id="p11123173816497"><a name="p11123173816497"></a><a name="p11123173816497"></a><strong id="b1283124312130"><a name="b1283124312130"></a><a name="b1283124312130"></a>Python3</strong></p>
</td>
<td class="cellrowborder" valign="top" width="23.14%" headers="mcps1.2.4.1.2 "><p id="p162264884913"><a name="p162264884913"></a><a name="p162264884913"></a><span class="parmname" id="parmname193351341566"><a name="parmname193351341566"></a><a name="parmname193351341566"></a>“TensorFlow”</span></p>
</td>
<td class="cellrowborder" valign="top" width="53.87%" headers="mcps1.2.4.1.3 "><a name="ul199881726566"></a><a name="ul199881726566"></a><ul id="ul199881726566"><li>TensorFlow-1.13.1</li><li>TensorFlow-1.8</li></ul>
</td>
</tr>
<tr id="row191231738164911"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p7622124864914"><a name="p7622124864914"></a><a name="p7622124864914"></a><span class="parmname" id="parmname4205183615611"><a name="parmname4205183615611"></a><a name="parmname4205183615611"></a>“MXNet”</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1123538134914"><a name="p1123538134914"></a><a name="p1123538134914"></a>MXNet-1.2.1</p>
</td>
</tr>
<tr id="row1912353815494"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p56221848174916"><a name="p56221848174916"></a><a name="p56221848174916"></a><span class="parmname" id="parmname1814164918563"><a name="parmname1814164918563"></a><a name="parmname1814164918563"></a>“Spark”</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p101231638174916"><a name="p101231638174916"></a><a name="p101231638174916"></a>PySpark-2.3.2</p>
</td>
</tr>
<tr id="row16436204116498"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1622144894914"><a name="p1622144894914"></a><a name="p1622144894914"></a><span class="parmname" id="parmname55521751155619"><a name="parmname55521751155619"></a><a name="parmname55521751155619"></a>“Scikit-learn &amp; XGBoost”</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p194363418499"><a name="p194363418499"></a><a name="p194363418499"></a>XGBoost-Sklearn</p>
</td>
</tr>
<tr id="row5436134115491"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p106221548104920"><a name="p106221548104920"></a><a name="p106221548104920"></a><span class="parmname" id="parmname1878135415561"><a name="parmname1878135415561"></a><a name="parmname1878135415561"></a>“PyTorch”</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p6436104117494"><a name="p6436104117494"></a><a name="p6436104117494"></a>PyTorch-1.0.0</p>
</td>
</tr>
<tr id="row0436841184918"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p662218488493"><a name="p662218488493"></a><a name="p662218488493"></a><span class="parmname" id="parmname1640833816123"><a name="parmname1640833816123"></a><a name="parmname1640833816123"></a>“Conda”</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p144369411497"><a name="p144369411497"></a><a name="p144369411497"></a>Conda-python3</p>
</td>
</tr>
</tbody>
</table>

## 使用限制<a name="section282863817439"></a>

-   出于安全因素考虑，ModelArts集成的Notebook暂不开放用户root权限，可使用非特权用户jovyan或者ma-user（Multi-Engine引擎）进行操作，因此暂不能使用apt-get安装操作系统软件。
-   针对当前的AI引擎框架，Notebook仅支持单机模式训练模型。如果需要使用分布式模式训练模型，建议使用ModelArts训练作业，资源池设置多节点的方式实现。

