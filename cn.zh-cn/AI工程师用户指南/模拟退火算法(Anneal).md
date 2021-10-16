# 模拟退火算法\(Anneal\)<a name="modelarts_23_0304"></a>

模拟退火算法即Anneal算法，是随机搜索中一个简单但有效的变体，它利用了响应曲面中的平滑度。退火速率不自适应。Anneal算法从先前采样的一个试验点作为起点，然后从与先验分布相似的分布中采样每组超参数，但其密度更集中在我们选择的试验点周围。随着时间推移，算法会倾向于从越来越接近最佳点处采样。在采样过程中，算法可能绘制一个次佳试验作为最佳试验，以一定概率跳出局部最优解。

**表 1**  模拟退火算法的参数说明

<a name="table322512401477"></a>
<table><thead align="left"><tr id="row522584013716"><th class="cellrowborder" valign="top" width="20.49204920492049%" id="mcps1.2.4.1.1"><p id="p18225204010715"><a name="p18225204010715"></a><a name="p18225204010715"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="46.17461746174617%" id="mcps1.2.4.1.2"><p id="p102257401372"><a name="p102257401372"></a><a name="p102257401372"></a>说明</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p109579561683"><a name="p109579561683"></a><a name="p109579561683"></a>取值参考</p>
</th>
</tr>
</thead>
<tbody><tr id="row122257401874"><td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.1 "><p id="p52259405719"><a name="p52259405719"></a><a name="p52259405719"></a>num_samples</p>
</td>
<td class="cellrowborder" valign="top" width="46.17461746174617%" headers="mcps1.2.4.1.2 "><p id="p1082016192096"><a name="p1082016192096"></a><a name="p1082016192096"></a>搜索尝试的超参组数</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p5660635196"><a name="p5660635196"></a><a name="p5660635196"></a>int，一般在10-20之间，值越大，搜索时间越长，效果越好</p>
</td>
</tr>
<tr id="row18225104016718"><td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.1 "><p id="p178718113918"><a name="p178718113918"></a><a name="p178718113918"></a>avg_best_idx</p>
</td>
<td class="cellrowborder" valign="top" width="46.17461746174617%" headers="mcps1.2.4.1.2 "><p id="p162258401714"><a name="p162258401714"></a><a name="p162258401714"></a>要探索试验的几何分布平均，从按照分数排序的试验中选择</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p94471738493"><a name="p94471738493"></a><a name="p94471738493"></a>float，一般不建议用户修改</p>
</td>
</tr>
<tr id="row152251040073"><td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.1 "><p id="p358012517911"><a name="p358012517911"></a><a name="p358012517911"></a>shrink_coef</p>
</td>
<td class="cellrowborder" valign="top" width="46.17461746174617%" headers="mcps1.2.4.1.2 "><p id="p1919733113914"><a name="p1919733113914"></a><a name="p1919733113914"></a>随着更多的点被探索，邻域采样大小的减少率</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1342734017910"><a name="p1342734017910"></a><a name="p1342734017910"></a>float，一般不建议用户修改</p>
</td>
</tr>
</tbody>
</table>

