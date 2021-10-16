# TPE算法<a name="modelarts_23_0303"></a>

TPE算法全称Tree-structured Parzen Estimator，是一种利用高斯混合模型来学习超参模型的算法。在每次试验中，对于每个超参，TPE为与最佳目标值相关的超参维护一个高斯混合模型l\(x\)，为剩余的超参维护另一个高斯混合模型g\(x\)，选择l\(x\)/g\(x\)最大化时对应的超参作为下一组搜索值。

**表 1**  TPE算法的参数说明

<a name="table1126512180615"></a>
<table><thead align="left"><tr id="row112652188612"><th class="cellrowborder" valign="top" width="20.72207220722072%" id="mcps1.2.4.1.1"><p id="p15265318869"><a name="p15265318869"></a><a name="p15265318869"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="45.944594459445945%" id="mcps1.2.4.1.2"><p id="p198261546167"><a name="p198261546167"></a><a name="p198261546167"></a>说明</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p1526519187619"><a name="p1526519187619"></a><a name="p1526519187619"></a>取值参考</p>
</th>
</tr>
</thead>
<tbody><tr id="row1926591817620"><td class="cellrowborder" valign="top" width="20.72207220722072%" headers="mcps1.2.4.1.1 "><p id="p35621651468"><a name="p35621651468"></a><a name="p35621651468"></a>num_samples</p>
</td>
<td class="cellrowborder" valign="top" width="45.944594459445945%" headers="mcps1.2.4.1.2 "><p id="p236620581612"><a name="p236620581612"></a><a name="p236620581612"></a>搜索尝试的超参组数</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p68534517711"><a name="p68534517711"></a><a name="p68534517711"></a>int，一般在10-20之间，值越大，搜索时间越长，效果越好</p>
</td>
</tr>
<tr id="row1265191811611"><td class="cellrowborder" valign="top" width="20.72207220722072%" headers="mcps1.2.4.1.1 "><p id="p826521812612"><a name="p826521812612"></a><a name="p826521812612"></a>n_initial_points</p>
</td>
<td class="cellrowborder" valign="top" width="45.944594459445945%" headers="mcps1.2.4.1.2 "><p id="p29231801710"><a name="p29231801710"></a><a name="p29231801710"></a>采用TPE接近目标函数之前，对目标函数的随机评估数</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p748213817712"><a name="p748213817712"></a><a name="p748213817712"></a>int，一般不建议用户修改</p>
</td>
</tr>
<tr id="row626516181769"><td class="cellrowborder" valign="top" width="20.72207220722072%" headers="mcps1.2.4.1.1 "><p id="p6919155513613"><a name="p6919155513613"></a><a name="p6919155513613"></a>gamma</p>
</td>
<td class="cellrowborder" valign="top" width="45.944594459445945%" headers="mcps1.2.4.1.2 "><p id="p152655188612"><a name="p152655188612"></a><a name="p152655188612"></a>TPE算法的一定分位数，用于划分l(x)和g(x)</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p273341015717"><a name="p273341015717"></a><a name="p273341015717"></a>float，范围(0,1)，一般不建议用户修改</p>
</td>
</tr>
</tbody>
</table>

