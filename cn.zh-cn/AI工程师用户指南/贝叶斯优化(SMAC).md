# 贝叶斯优化\(SMAC\)<a name="modelarts_23_0297"></a>

贝叶斯优化假设超参和目标函数存在一个函数关系。基于已搜索超参的评估值，通过高斯过程回归来估计其他搜索点处目标函数值的均值和方差。根据均值和方差构造采集函数（Acquisition Function），下一个搜索点为采集函数的极大值点。相比网格搜索，贝叶斯优化会利用之前的评估结果，从而降低迭代次数、缩短搜索时间；缺点是不容易找到全局最优解。

**表 1**  贝叶斯优化的参数说明

<a name="table1794415199457"></a>
<table><thead align="left"><tr id="row3944131954516"><th class="cellrowborder" valign="top" width="20.37203720372037%" id="mcps1.2.4.1.1"><p id="p7177102613458"><a name="p7177102613458"></a><a name="p7177102613458"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="36.203620362036204%" id="mcps1.2.4.1.2"><p id="p1117711260455"><a name="p1117711260455"></a><a name="p1117711260455"></a>说明</p>
</th>
<th class="cellrowborder" valign="top" width="43.42434243424342%" id="mcps1.2.4.1.3"><p id="p194461910453"><a name="p194461910453"></a><a name="p194461910453"></a>取值参考</p>
</th>
</tr>
</thead>
<tbody><tr id="row49441819134520"><td class="cellrowborder" valign="top" width="20.37203720372037%" headers="mcps1.2.4.1.1 "><p id="p1194413198451"><a name="p1194413198451"></a><a name="p1194413198451"></a>num_samples</p>
</td>
<td class="cellrowborder" valign="top" width="36.203620362036204%" headers="mcps1.2.4.1.2 "><p id="p1114418501156"><a name="p1114418501156"></a><a name="p1114418501156"></a>搜索尝试的超参组数</p>
</td>
<td class="cellrowborder" valign="top" width="43.42434243424342%" headers="mcps1.2.4.1.3 "><p id="p694421954511"><a name="p694421954511"></a><a name="p694421954511"></a>int，一般在10-20之间，值越大，搜索时间越长，效果越好</p>
</td>
</tr>
<tr id="row1894412196451"><td class="cellrowborder" valign="top" width="20.37203720372037%" headers="mcps1.2.4.1.1 "><p id="p109444195451"><a name="p109444195451"></a><a name="p109444195451"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="36.203620362036204%" headers="mcps1.2.4.1.2 "><p id="p99442199459"><a name="p99442199459"></a><a name="p99442199459"></a>采集函数类型</p>
</td>
<td class="cellrowborder" valign="top" width="43.42434243424342%" headers="mcps1.2.4.1.3 "><p id="p1494491994513"><a name="p1494491994513"></a><a name="p1494491994513"></a>string，默认为'ucb'，可能取值还有'ei'、'poi'，一般不建议用户修改</p>
</td>
</tr>
<tr id="row694491911456"><td class="cellrowborder" valign="top" width="20.37203720372037%" headers="mcps1.2.4.1.1 "><p id="p129449192454"><a name="p129449192454"></a><a name="p129449192454"></a>kappa</p>
</td>
<td class="cellrowborder" valign="top" width="36.203620362036204%" headers="mcps1.2.4.1.2 "><p id="p179445196459"><a name="p179445196459"></a><a name="p179445196459"></a>采集函数ucb的调节参数，可理解为上置信边界</p>
</td>
<td class="cellrowborder" valign="top" width="43.42434243424342%" headers="mcps1.2.4.1.3 "><p id="p4944191916456"><a name="p4944191916456"></a><a name="p4944191916456"></a>float，一般不建议用户修改</p>
</td>
</tr>
<tr id="row69444198453"><td class="cellrowborder" valign="top" width="20.37203720372037%" headers="mcps1.2.4.1.1 "><p id="p0944719184518"><a name="p0944719184518"></a><a name="p0944719184518"></a>xi</p>
</td>
<td class="cellrowborder" valign="top" width="36.203620362036204%" headers="mcps1.2.4.1.2 "><p id="p1194420196458"><a name="p1194420196458"></a><a name="p1194420196458"></a>采集函数poi和ei的调节参数</p>
</td>
<td class="cellrowborder" valign="top" width="43.42434243424342%" headers="mcps1.2.4.1.3 "><p id="p99448197457"><a name="p99448197457"></a><a name="p99448197457"></a>float，一般不建议用户修改</p>
</td>
</tr>
</tbody>
</table>

