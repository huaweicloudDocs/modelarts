# yaml配置文件说明<a name="modelarts_23_0155"></a>

如果用户需要使用超参搜索的话，必须编写一个符合ModelArts规范的yaml配置文件。

## yaml配置文件示例<a name="section8745159165510"></a>

```
trainingInput:
  verbose: 1
  hyperparameters:
    enableTrialEarlyStopping: false
    searchAlgorithm: hyperopt
    searchAlgorithmMetric: loss
    searchAlgorithmMode: min
    scheduler: async_hyperband
    schedulerMetric: loss
    schedulerMode: min
    maxTrials: 16
    maxParallelTrials: 8
    cpuPerTrial: 2
    gpuPerTrial: 1
    maxIterations: 1000
    params:
      - parameterName: learning_rate
        type: float
        scaleType: DEFAULT
        minValue: 0.0001
        maxValue: 0.0015
        priorBestValue: 0.0001
```

## yaml配置文件的参数说明<a name="section925641975610"></a>

**表 1**  yaml配置文件的参数说明

<a name="table3953511538"></a>
<table><thead align="left"><tr id="row119635165317"><th class="cellrowborder" valign="top" width="29.87%" id="mcps1.2.3.1.1"><p id="p17107353537"><a name="p17107353537"></a><a name="p17107353537"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="70.13000000000001%" id="mcps1.2.3.1.2"><p id="p181073512535"><a name="p181073512535"></a><a name="p181073512535"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1101335175316"><td class="cellrowborder" valign="top" width="29.87%" headers="mcps1.2.3.1.1 "><p id="p131011358530"><a name="p131011358530"></a><a name="p131011358530"></a>verbose</p>
</td>
<td class="cellrowborder" valign="top" width="70.13000000000001%" headers="mcps1.2.3.1.2 "><p id="p169766114542"><a name="p169766114542"></a><a name="p169766114542"></a>日志打印级别，取值范围为0～２。</p>
<a name="ul681412117546"></a><a name="ul681412117546"></a><ul id="ul681412117546"><li>0代表无超参相关日志打印。</li><li>1代表只打印关键日志。</li><li>2代表全量日志打印。</li></ul>
</td>
</tr>
<tr id="row12104359537"><td class="cellrowborder" valign="top" width="29.87%" headers="mcps1.2.3.1.1 "><p id="p610113513539"><a name="p610113513539"></a><a name="p610113513539"></a>hyperparameters</p>
</td>
<td class="cellrowborder" valign="top" width="70.13000000000001%" headers="mcps1.2.3.1.2 "><p id="p191013512538"><a name="p191013512538"></a><a name="p191013512538"></a>定义超参搜索算法的相关配置，详细参数说明请参见<a href="#table671892015198">表2</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  hyperparameters参数说明

<a name="table671892015198"></a>
<table><thead align="left"><tr id="row17977120161913"><th class="cellrowborder" valign="top" width="23.200000000000003%" id="mcps1.2.4.1.1"><p id="p113788715355"><a name="p113788715355"></a><a name="p113788715355"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="26.3%" id="mcps1.2.4.1.2"><p id="p1497772016194"><a name="p1497772016194"></a><a name="p1497772016194"></a>取值范围</p>
</th>
<th class="cellrowborder" valign="top" width="50.5%" id="mcps1.2.4.1.3"><p id="p1997732071919"><a name="p1997732071919"></a><a name="p1997732071919"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1997852012190"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p1337816711351"><a name="p1337816711351"></a><a name="p1337816711351"></a>enableTrialEarlyStopping</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p1176863112582"><a name="p1176863112582"></a><a name="p1176863112582"></a>True</p>
<p id="p797812201191"><a name="p797812201191"></a><a name="p797812201191"></a>False</p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p52892188373"><a name="p52892188373"></a><a name="p52892188373"></a>是否允许在某次超参效果非常差的情况下提前结束该组超参的训练。</p>
</td>
</tr>
<tr id="row3866174212361"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p188679422363"><a name="p188679422363"></a><a name="p188679422363"></a>searchAlgorithm</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p168671942173618"><a name="p168671942173618"></a><a name="p168671942173618"></a>hyperopt</p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p332121753718"><a name="p332121753718"></a><a name="p332121753718"></a>搜索算法，目前仅支持使用hyperopt。</p>
</td>
</tr>
<tr id="row189782020111917"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p10378177133514"><a name="p10378177133514"></a><a name="p10378177133514"></a>searchAlgorithmMetric</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p1697822011196"><a name="p1697822011196"></a><a name="p1697822011196"></a>任意string，例如loss，meanap等</p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p932111793710"><a name="p932111793710"></a><a name="p932111793710"></a>用于超参搜索的评价指标，需要在每次迭代结束后，调用hpsearch.METRICS进行反馈。</p>
</td>
</tr>
<tr id="row1797812061910"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p21323164397"><a name="p21323164397"></a><a name="p21323164397"></a>searchAlgorithmMode</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p1619191515112"><a name="p1619191515112"></a><a name="p1619191515112"></a>min</p>
<p id="p8978920131910"><a name="p8978920131910"></a><a name="p8978920131910"></a>max</p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p13978120121913"><a name="p13978120121913"></a><a name="p13978120121913"></a>超参搜索时的评价指标的优化方向，最大化或最小化。</p>
</td>
</tr>
<tr id="row72391443104113"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p1424084310414"><a name="p1424084310414"></a><a name="p1424084310414"></a>scheduler</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p1261412816435"><a name="p1261412816435"></a><a name="p1261412816435"></a>async_hyperband</p>
<p id="p6146195834117"><a name="p6146195834117"></a><a name="p6146195834117"></a></p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p189551458134118"><a name="p189551458134118"></a><a name="p189551458134118"></a>调度算法，调度控制当前尝试是否需要停止，以及下次尝试哪组备选超参，目前仅支持使用async_hyperband。</p>
</td>
</tr>
<tr id="row697812207196"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p1537811712356"><a name="p1537811712356"></a><a name="p1537811712356"></a>schedulerMetric</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p5743531194418"><a name="p5743531194418"></a><a name="p5743531194418"></a>任意string，例如loss，meanap等</p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p518903910537"><a name="p518903910537"></a><a name="p518903910537"></a>用于超参搜索的评价指标，与searchAlgorithmMetric相同。</p>
</td>
</tr>
<tr id="row1978182031914"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p2037816733517"><a name="p2037816733517"></a><a name="p2037816733517"></a>schedulerMode</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p822765117116"><a name="p822765117116"></a><a name="p822765117116"></a>min</p>
<p id="p1786103714442"><a name="p1786103714442"></a><a name="p1786103714442"></a>max</p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p2593185744314"><a name="p2593185744314"></a><a name="p2593185744314"></a>调度器控制的优化方向，与searchAlgorithmMetric相同。</p>
</td>
</tr>
<tr id="row3978520161919"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p943881664512"><a name="p943881664512"></a><a name="p943881664512"></a>maxTrials</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p99791206194"><a name="p99791206194"></a><a name="p99791206194"></a>（Integer）</p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p1297972011919"><a name="p1297972011919"></a><a name="p1297972011919"></a>超参测试的最大组数。</p>
</td>
</tr>
<tr id="row1397972015199"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p68101020194511"><a name="p68101020194511"></a><a name="p68101020194511"></a>maxParallelTrials</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p397920206190"><a name="p397920206190"></a><a name="p397920206190"></a>（Integer）</p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p129792020121914"><a name="p129792020121914"></a><a name="p129792020121914"></a>超参测试的最大并行数量，由GPU资源限制决定。</p>
</td>
</tr>
<tr id="row11979420201912"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p44171942124512"><a name="p44171942124512"></a><a name="p44171942124512"></a>cpuPerTrial</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p797932017198"><a name="p797932017198"></a><a name="p797932017198"></a>（Integer）</p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p1597913201190"><a name="p1597913201190"></a><a name="p1597913201190"></a>每组超参测试时CPU的使用量。</p>
</td>
</tr>
<tr id="row19798208194"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p25314514515"><a name="p25314514515"></a><a name="p25314514515"></a>gpuPerTrial</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p17979182016191"><a name="p17979182016191"></a><a name="p17979182016191"></a>（Integer）</p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p12979132016191"><a name="p12979132016191"></a><a name="p12979132016191"></a>每组超参测试时GPU的使用量。</p>
</td>
</tr>
<tr id="row8979620111914"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p8379177113517"><a name="p8379177113517"></a><a name="p8379177113517"></a>maxIterations</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p13979152012199"><a name="p13979152012199"></a><a name="p13979152012199"></a>（Integer）</p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p697922051912"><a name="p697922051912"></a><a name="p697922051912"></a>每组超参测试时最大迭代次数，用户代码调用hpsearch.METRICS反馈一次指标则视为迭代一次。</p>
</td>
</tr>
<tr id="row29797202194"><td class="cellrowborder" valign="top" width="23.200000000000003%" headers="mcps1.2.4.1.1 "><p id="p37981233164619"><a name="p37981233164619"></a><a name="p37981233164619"></a>params</p>
</td>
<td class="cellrowborder" valign="top" width="26.3%" headers="mcps1.2.4.1.2 "><p id="p49791820181915"><a name="p49791820181915"></a><a name="p49791820181915"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50.5%" headers="mcps1.2.4.1.3 "><p id="p11979020181916"><a name="p11979020181916"></a><a name="p11979020181916"></a>配置需要搜索的参数信息，详细说明请参见<a href="#table13801946145619">表3</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  params参数说明

<a name="table13801946145619"></a>
<table><thead align="left"><tr id="row580174625613"><th class="cellrowborder" valign="top" width="29.18%" id="mcps1.2.3.1.1"><p id="p198028464562"><a name="p198028464562"></a><a name="p198028464562"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="70.82000000000001%" id="mcps1.2.3.1.2"><p id="p2802114685611"><a name="p2802114685611"></a><a name="p2802114685611"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1480214675612"><td class="cellrowborder" valign="top" width="29.18%" headers="mcps1.2.3.1.1 "><p id="p1594591115710"><a name="p1594591115710"></a><a name="p1594591115710"></a>parameterName</p>
</td>
<td class="cellrowborder" valign="top" width="70.82000000000001%" headers="mcps1.2.3.1.2 "><p id="p19764121695714"><a name="p19764121695714"></a><a name="p19764121695714"></a>参数名称。</p>
<p id="p177917259570"><a name="p177917259570"></a><a name="p177917259570"></a>string（eg: lr, momentum, lr_decay, weight_decay）</p>
</td>
</tr>
<tr id="row1280211466564"><td class="cellrowborder" valign="top" width="29.18%" headers="mcps1.2.3.1.1 "><p id="p1594611195712"><a name="p1594611195712"></a><a name="p1594611195712"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="70.82000000000001%" headers="mcps1.2.3.1.2 "><p id="p147641416195713"><a name="p147641416195713"></a><a name="p147641416195713"></a>参数类型，取值范围为DOUBLE、INT。</p>
</td>
</tr>
<tr id="row5802846155610"><td class="cellrowborder" valign="top" width="29.18%" headers="mcps1.2.3.1.1 "><p id="p15946121115714"><a name="p15946121115714"></a><a name="p15946121115714"></a>minValue</p>
</td>
<td class="cellrowborder" rowspan="2" valign="top" width="70.82000000000001%" headers="mcps1.2.3.1.2 "><p id="p1776481625717"><a name="p1776481625717"></a><a name="p1776481625717"></a>参数取值范围，设置范围的最大值和最小值。必须设置。</p>
</td>
</tr>
<tr id="row180244675613"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p2094651113576"><a name="p2094651113576"></a><a name="p2094651113576"></a>maxValue</p>
</td>
</tr>
<tr id="row041610775710"><td class="cellrowborder" valign="top" width="29.18%" headers="mcps1.2.3.1.1 "><p id="p1494616117577"><a name="p1494616117577"></a><a name="p1494616117577"></a>priorBestValue</p>
</td>
<td class="cellrowborder" valign="top" width="70.82000000000001%" headers="mcps1.2.3.1.2 "><p id="p1764191685717"><a name="p1764191685717"></a><a name="p1764191685717"></a>在搜索前用户所用先验参数值。</p>
</td>
</tr>
</tbody>
</table>

