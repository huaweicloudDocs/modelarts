# 打开Notebook实例<a name="modelarts_30_0005"></a>

针对创建好的Notebook实例（即状态为“运行中“的实例），可以打开Notebook并在开发环境中启动编码。

基于不同AI引擎创建的Notebook实例，打开方式不一样，具体详情如[表1](#table473944511422)所示。

**表 1**  AI引擎

<a name="table473944511422"></a>
<table><thead align="left"><tr id="modelarts_30_0001_row1073994515422"><th class="cellrowborder" valign="top" width="25.320000000000004%" id="mcps1.2.5.1.1"><p id="modelarts_30_0001_p167391245124218"><a name="modelarts_30_0001_p167391245124218"></a><a name="modelarts_30_0001_p167391245124218"></a>镜像名称</p>
</th>
<th class="cellrowborder" valign="top" width="24.190000000000005%" id="mcps1.2.5.1.2"><p id="modelarts_30_0001_p173826451699"><a name="modelarts_30_0001_p173826451699"></a><a name="modelarts_30_0001_p173826451699"></a>镜像描述</p>
</th>
<th class="cellrowborder" valign="top" width="30.410000000000004%" id="mcps1.2.5.1.3"><p id="p103495431718"><a name="p103495431718"></a><a name="p103495431718"></a>Notebook实例打开方式</p>
</th>
<th class="cellrowborder" valign="top" width="20.080000000000002%" id="mcps1.2.5.1.4"><p id="modelarts_30_0001_p1841912239237"><a name="modelarts_30_0001_p1841912239237"></a><a name="modelarts_30_0001_p1841912239237"></a>操作参考</p>
</th>
</tr>
</thead>
<tbody><tr id="modelarts_30_0001_row8739124511421"><td class="cellrowborder" valign="top" width="25.320000000000004%" headers="mcps1.2.5.1.1 "><p id="modelarts_30_0001_p985410561716"><a name="modelarts_30_0001_p985410561716"></a><a name="modelarts_30_0001_p985410561716"></a><span>pytorch1.4-cuda10.1-cudnn7-ubuntu18.04</span></p>
</td>
<td class="cellrowborder" valign="top" width="24.190000000000005%" headers="mcps1.2.5.1.2 "><p id="modelarts_30_0001_p138210451890"><a name="modelarts_30_0001_p138210451890"></a><a name="modelarts_30_0001_p138210451890"></a>CPU、GPU通用算法开发和训练基础镜像，预置AI引擎<span>PyTorch1.4</span></p>
</td>
<td class="cellrowborder" valign="top" width="30.410000000000004%" headers="mcps1.2.5.1.3 "><a name="ul1729165315116"></a><a name="ul1729165315116"></a><ul id="ul1729165315116"><li>本地IDE使用PyCharm/VSCode通过SSH远程访问</li><li>在线JupyterLab访问</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20.080000000000002%" headers="mcps1.2.5.1.4 "><a name="ul16624195320511"></a><a name="ul16624195320511"></a><ul id="ul16624195320511"><li><a href="使用本地IDE开发模型.md">使用本地IDE开发模型</a></li><li><a href="使用JupyterLab开发模型.md">使用JupyterLab开发模型</a></li></ul>
</td>
</tr>
<tr id="modelarts_30_0001_row13809241817"><td class="cellrowborder" valign="top" width="25.320000000000004%" headers="mcps1.2.5.1.1 "><p id="modelarts_30_0001_p14807241788"><a name="modelarts_30_0001_p14807241788"></a><a name="modelarts_30_0001_p14807241788"></a><span>tensorflow2.1-cuda10.1-cudnn7-ubuntu18.04</span></p>
</td>
<td class="cellrowborder" valign="top" width="24.190000000000005%" headers="mcps1.2.5.1.2 "><p id="modelarts_30_0001_p146151150151011"><a name="modelarts_30_0001_p146151150151011"></a><a name="modelarts_30_0001_p146151150151011"></a>CPU、GPU通用算法开发和训练基础镜像，预置AI引擎<span>TensorFlow2.1</span></p>
</td>
<td class="cellrowborder" valign="top" width="30.410000000000004%" headers="mcps1.2.5.1.3 "><a name="ul1633132810416"></a><a name="ul1633132810416"></a><ul id="ul1633132810416"><li>本地IDE使用PyCharm/VSCode通过SSH远程访问</li><li>在线JupyterLab访问</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20.080000000000002%" headers="mcps1.2.5.1.4 "><a name="ul105915161665"></a><a name="ul105915161665"></a><ul id="ul105915161665"><li><a href="使用本地IDE开发模型.md">使用本地IDE开发模型</a></li><li><a href="使用JupyterLab开发模型.md">使用JupyterLab开发模型</a></li></ul>
</td>
</tr>
<tr id="modelarts_30_0001_row14536830155913"><td class="cellrowborder" valign="top" width="25.320000000000004%" headers="mcps1.2.5.1.1 "><p id="modelarts_30_0001_p17151735205914"><a name="modelarts_30_0001_p17151735205914"></a><a name="modelarts_30_0001_p17151735205914"></a><span>mindspore1.2.0-openmpi2.1.1-ubuntu18.04</span></p>
</td>
<td class="cellrowborder" valign="top" width="24.190000000000005%" headers="mcps1.2.5.1.2 "><p id="modelarts_30_0001_p171523512591"><a name="modelarts_30_0001_p171523512591"></a><a name="modelarts_30_0001_p171523512591"></a>CPU算法开发和训练基础镜像，预置AI引擎<span>MindSpore1.2.0-CPU</span></p>
</td>
<td class="cellrowborder" valign="top" width="30.410000000000004%" headers="mcps1.2.5.1.3 "><a name="ul58413013419"></a><a name="ul58413013419"></a><ul id="ul58413013419"><li>本地IDE使用PyCharm/VSCode通过SSH远程访问</li><li>在线JupyterLab访问</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20.080000000000002%" headers="mcps1.2.5.1.4 "><a name="ul1755112171611"></a><a name="ul1755112171611"></a><ul id="ul1755112171611"><li><a href="使用本地IDE开发模型.md">使用本地IDE开发模型</a></li><li><a href="使用JupyterLab开发模型.md">使用JupyterLab开发模型</a></li></ul>
</td>
</tr>
<tr id="modelarts_30_0001_row374024516426"><td class="cellrowborder" valign="top" width="25.320000000000004%" headers="mcps1.2.5.1.1 "><p id="modelarts_30_0001_p37406459426"><a name="modelarts_30_0001_p37406459426"></a><a name="modelarts_30_0001_p37406459426"></a><span>mindspore1.2.0-cuda10.1-cudnn7-ubuntu18.04</span></p>
</td>
<td class="cellrowborder" valign="top" width="24.190000000000005%" headers="mcps1.2.5.1.2 "><p id="modelarts_30_0001_p1738219452913"><a name="modelarts_30_0001_p1738219452913"></a><a name="modelarts_30_0001_p1738219452913"></a>GPU算法开发和训练基础镜像，预置AI引擎<span>MindSpore1.2.0-GPU</span></p>
</td>
<td class="cellrowborder" valign="top" width="30.410000000000004%" headers="mcps1.2.5.1.3 "><a name="ul087414311942"></a><a name="ul087414311942"></a><ul id="ul087414311942"><li>本地IDE使用PyCharm/VSCode通过SSH远程访问</li><li>在线JupyterLab访问</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20.080000000000002%" headers="mcps1.2.5.1.4 "><a name="ul566141820617"></a><a name="ul566141820617"></a><ul id="ul566141820617"><li><a href="使用本地IDE开发模型.md">使用本地IDE开发模型</a></li><li><a href="使用JupyterLab开发模型.md">使用JupyterLab开发模型</a></li></ul>
</td>
</tr>
<tr id="modelarts_30_0001_row17990104634617"><td class="cellrowborder" valign="top" width="25.320000000000004%" headers="mcps1.2.5.1.1 "><p id="modelarts_30_0001_p29231724105814"><a name="modelarts_30_0001_p29231724105814"></a><a name="modelarts_30_0001_p29231724105814"></a>mlstudio-pyspark2.3.2-ubuntu16.04</p>
</td>
<td class="cellrowborder" valign="top" width="24.190000000000005%" headers="mcps1.2.5.1.2 "><p id="modelarts_30_0001_p670018105129"><a name="modelarts_30_0001_p670018105129"></a><a name="modelarts_30_0001_p670018105129"></a>CPU算法开发和训练基础镜像，包含可以图形化机器学习算法开发和调测MLStudio工具，并预置PySpark2.3.2</p>
</td>
<td class="cellrowborder" valign="top" width="30.410000000000004%" headers="mcps1.2.5.1.3 "><a name="ul1128519459215"></a><a name="ul1128519459215"></a><ul id="ul1128519459215"><li>在线JupyterLab打开MLS Editer访问</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20.080000000000002%" headers="mcps1.2.5.1.4 "><p id="p167835613513"><a name="p167835613513"></a><a name="p167835613513"></a><a href="使用可视化工具ML-Studio开发模型.md">使用可视化工具ML Studio开发模型</a></p>
</td>
</tr>
<tr id="modelarts_30_0001_row1520012221524"><td class="cellrowborder" valign="top" width="25.320000000000004%" headers="mcps1.2.5.1.1 "><p id="modelarts_30_0001_p86530221743"><a name="modelarts_30_0001_p86530221743"></a><a name="modelarts_30_0001_p86530221743"></a>mindstudio3.0.1-ascend910-cann3.3.0-ubuntu18.04-aarch64</p>
</td>
<td class="cellrowborder" valign="top" width="24.190000000000005%" headers="mcps1.2.5.1.2 "><p id="modelarts_30_0001_p172001722821"><a name="modelarts_30_0001_p172001722821"></a><a name="modelarts_30_0001_p172001722821"></a>Ascend算子开发基础镜像，预置专业级算子开发工具MindStudio，仅支持SSH链接</p>
</td>
<td class="cellrowborder" valign="top" width="30.410000000000004%" headers="mcps1.2.5.1.3 "><p id="p133495431417"><a name="p133495431417"></a><a name="p133495431417"></a>本地使用MobaXterm通过SSH远程访问</p>
</td>
<td class="cellrowborder" valign="top" width="20.080000000000002%" headers="mcps1.2.5.1.4 "><p id="p178212615517"><a name="p178212615517"></a><a name="p178212615517"></a><a href="使用MindStudio开发Ascend算子.md">使用MindStudio开发Ascend算子</a></p>
</td>
</tr>
<tr id="modelarts_30_0001_row15991114610463"><td class="cellrowborder" valign="top" width="25.320000000000004%" headers="mcps1.2.5.1.1 "><p id="modelarts_30_0001_p399174611468"><a name="modelarts_30_0001_p399174611468"></a><a name="modelarts_30_0001_p399174611468"></a><span>tensorflow1.15-mindspore1.2.0-cann20.2-euler2.8-aarch64</span></p>
</td>
<td class="cellrowborder" valign="top" width="24.190000000000005%" headers="mcps1.2.5.1.2 "><p id="modelarts_30_0001_p438215452918"><a name="modelarts_30_0001_p438215452918"></a><a name="modelarts_30_0001_p438215452918"></a>Ascend+ARM算法开发和训练基础镜像，预置AI引擎<span>TensorFlow1.15和MindSpore1.2.0</span></p>
</td>
<td class="cellrowborder" valign="top" width="30.410000000000004%" headers="mcps1.2.5.1.3 "><a name="ul662412401743"></a><a name="ul662412401743"></a><ul id="ul662412401743"><li>本地IDE使用PyCharm/VSCode通过SSH远程访问</li><li>在线JupyterLab访问</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20.080000000000002%" headers="mcps1.2.5.1.4 "><a name="ul13478754662"></a><a name="ul13478754662"></a><ul id="ul13478754662"><li><a href="使用本地IDE开发模型.md">使用本地IDE开发模型</a></li><li><a href="使用JupyterLab开发模型.md">使用JupyterLab开发模型</a></li></ul>
</td>
</tr>
<tr id="row2278202910344"><td class="cellrowborder" valign="top" width="25.320000000000004%" headers="mcps1.2.5.1.1 "><p id="p14421125131620"><a name="p14421125131620"></a><a name="p14421125131620"></a><span>modelbox1.0.9.2-tensorrt7.1.3-pytorch1.8.1-cuda10.2-cudnn8-euler2.8-aarch64</span></p>
</td>
<td class="cellrowborder" valign="top" width="24.190000000000005%" headers="mcps1.2.5.1.2 "><p id="p196227153137"><a name="p196227153137"></a><a name="p196227153137"></a>AI应用开发基础镜像，预置AI应用编排引擎ModelBox、AI引擎PyTorch、TensorRT和TensorFlow，仅支持SSH连接</p>
</td>
<td class="cellrowborder" valign="top" width="30.410000000000004%" headers="mcps1.2.5.1.3 "><p id="p176221115101312"><a name="p176221115101312"></a><a name="p176221115101312"></a>在本地IDE使用VSCode插件远程访问</p>
</td>
<td class="cellrowborder" valign="top" width="20.080000000000002%" headers="mcps1.2.5.1.4 "><p id="p17939153143518"><a name="p17939153143518"></a><a name="p17939153143518"></a><a href="配置本地IDE（VSCode-ToolKit连接）.md">配置本地IDE（VSCode ToolKit连接）</a></p>
</td>
</tr>
<tr id="row1967714119346"><td class="cellrowborder" valign="top" width="25.320000000000004%" headers="mcps1.2.5.1.1 "><p id="p426910266160"><a name="p426910266160"></a><a name="p426910266160"></a><span>rlstudio1.0.0-ray1.3.0--cuda10.1-ubuntu18.04</span></p>
</td>
<td class="cellrowborder" valign="top" width="24.190000000000005%" headers="mcps1.2.5.1.2 "><p id="p16545822151313"><a name="p16545822151313"></a><a name="p16545822151313"></a>CPU、GPU强化学习算法开发和训练基础镜像，预置AI引擎.</p>
</td>
<td class="cellrowborder" valign="top" width="30.410000000000004%" headers="mcps1.2.5.1.3 "><a name="ul1726716564351"></a><a name="ul1726716564351"></a><ul id="ul1726716564351"><li>本地IDE使用PyCharm/VSCode通过SSH远程访问</li><li>在线JupyterLab访问</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20.080000000000002%" headers="mcps1.2.5.1.4 "><a name="ul4748169133615"></a><a name="ul4748169133615"></a><ul id="ul4748169133615"><li><a href="使用本地IDE开发模型.md">使用本地IDE开发模型</a></li><li><a href="使用JupyterLab开发模型.md">使用JupyterLab开发模型</a></li></ul>
</td>
</tr>
<tr id="row15461174410343"><td class="cellrowborder" valign="top" width="25.320000000000004%" headers="mcps1.2.5.1.1 "><p id="p2085232661617"><a name="p2085232661617"></a><a name="p2085232661617"></a><span>cylp0.91.4-cbcpy2.10-cplex20.1.0-ubuntu18.04</span></p>
</td>
<td class="cellrowborder" valign="top" width="24.190000000000005%" headers="mcps1.2.5.1.2 "><p id="p1289182018138"><a name="p1289182018138"></a><a name="p1289182018138"></a><span>CPU运筹优化求解器开发基础镜像，预置cylp，cbcpy，ortools及cplex.</span></p>
</td>
<td class="cellrowborder" valign="top" width="30.410000000000004%" headers="mcps1.2.5.1.3 "><a name="ul17542105863510"></a><a name="ul17542105863510"></a><ul id="ul17542105863510"><li>本地IDE使用PyCharm/VSCode通过SSH远程访问</li><li>在线JupyterLab访问</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20.080000000000002%" headers="mcps1.2.5.1.4 "><a name="ul19656131018360"></a><a name="ul19656131018360"></a><ul id="ul19656131018360"><li><a href="使用本地IDE开发模型.md">使用本地IDE开发模型</a></li><li><a href="使用JupyterLab开发模型.md">使用JupyterLab开发模型</a></li></ul>
</td>
</tr>
</tbody>
</table>

