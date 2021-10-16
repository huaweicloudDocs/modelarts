# SDK简介<a name="modelarts_04_0002"></a>

ModelArts服务软件开发工具包（ModelArts SDK）是对ModelArts服务提供的REST API进行的Python封装，以简化用户的开发工作。用户直接调用ModelArts SDK即可轻松管理数据集、启动AI训练以及生成模型并将其部署上线。

ModelArts SDK目前只提供Python语言的SDK，同时支持Python 2.7、Python 3.6和Python 3.7。

## SDK版本说明<a name="section780610424503"></a>

**表 1**  ModelArts SDK版本说明

<a name="table978915214500"></a>
<table><thead align="left"><tr id="row13790165275013"><th class="cellrowborder" valign="top" width="16.67166716671667%" id="mcps1.2.4.1.1"><p id="p179016522507"><a name="p179016522507"></a><a name="p179016522507"></a>发布时间</p>
</th>
<th class="cellrowborder" valign="top" width="17.17171717171717%" id="mcps1.2.4.1.2"><p id="p1679017521507"><a name="p1679017521507"></a><a name="p1679017521507"></a>版本号</p>
</th>
<th class="cellrowborder" valign="top" width="66.15661566156615%" id="mcps1.2.4.1.3"><p id="p679011528508"><a name="p679011528508"></a><a name="p679011528508"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row9804173311138"><td class="cellrowborder" valign="top" width="16.67166716671667%" headers="mcps1.2.4.1.1 "><p id="p1018503224"><a name="p1018503224"></a><a name="p1018503224"></a>2019-08-08</p>
</td>
<td class="cellrowborder" valign="top" width="17.17171717171717%" headers="mcps1.2.4.1.2 "><p id="p1818515313219"><a name="p1818515313219"></a><a name="p1818515313219"></a>1.1.3（推荐使用）</p>
</td>
<td class="cellrowborder" valign="top" width="66.15661566156615%" headers="mcps1.2.4.1.3 "><p id="p19805193341319"><a name="p19805193341319"></a><a name="p19805193341319"></a>1.1.3版本在SDK旧版本基础上优化集成，主要包括session、OBS管理、作业管理、模型管理、服务管理。本版本SDK的历史修改记录如下所示。</p>
<a name="ul153933551576"></a><a name="ul153933551576"></a><ul id="ul153933551576"><li>2020.04：新增OBS相关操作接口。新增支持TensorFlow本地推理。</li></ul>
</td>
</tr>
</tbody>
</table>

## 支持的区域<a name="section5643134104713"></a>

当前支持的“region\_name“包括华北-北京一（cn-north-1）、华北-北京四（cn-north-4）、华东-上海一（cn-east-3）、华南-广州（cn-south-1）。

