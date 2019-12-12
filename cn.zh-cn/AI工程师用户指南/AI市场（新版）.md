# AI市场（新版）<a name="modelarts_23_0171"></a>

ModelArts的AI市场（新版）提供了其他用户共享的模型，您可以使用他人分享的信息快速构建模型。同时，您也可以将自己的模型发布至AI市场，共享知识。

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   AI市场（新版）中，当前仅支持了“ModelHub“功能、“HoloSens Store“和“HiLens技能“，未来即将上线“数据集“、“Ipython笔记“、“挑战“、“委托令“、“品评“等功能。  
>-   其中“ModelHub“市场中共享了模型，用于ModelArts平台。“HoloSens Store“用于智能安防行业，详细指导请参见《[智能安防资料书架](https://support.huawei.com/enterprise/zh/category/video-surveillance-pid-1482615596259?submodel=7919735)》。“HiLens技能“为HiLens服务的技能市场功能，详细指导请参见《[HiLens用户指南](https://support.huaweicloud.com/usermanual-hilens/hilens_02_0036.html)》。  

## 新版与旧版的区别<a name="section14111144365217"></a>

为保证老用户能够继续使用AI市场及其完整的功能，新版和旧版在将“华北-北京一“区域同时存在一段时间。您可以根据自身情况，选择使用新版或旧版，由于新版的AI市场，其性能和体验更佳，推荐您优先选择使用新版。本章节介绍新版的说明和使用介绍，关于旧版的使用指导，请参见[AI市场](zh-cn_topic_0121803214.md)。

**表 1**  新版与旧版AI市场的区别说明

<a name="table7984191415318"></a>
<table><thead align="left"><tr id="row1798511147531"><th class="cellrowborder" valign="top" width="28.992899289928992%" id="mcps1.2.4.1.1"><p id="p19985814115310"><a name="p19985814115310"></a><a name="p19985814115310"></a>区别项</p>
</th>
<th class="cellrowborder" valign="top" width="33.73337333733373%" id="mcps1.2.4.1.2"><p id="p119851414185316"><a name="p119851414185316"></a><a name="p119851414185316"></a>新版</p>
</th>
<th class="cellrowborder" valign="top" width="37.27372737273727%" id="mcps1.2.4.1.3"><p id="p99851914185314"><a name="p99851914185314"></a><a name="p99851914185314"></a>旧版</p>
</th>
</tr>
</thead>
<tbody><tr id="row119851314155319"><td class="cellrowborder" valign="top" width="28.992899289928992%" headers="mcps1.2.4.1.1 "><p id="p139859148535"><a name="p139859148535"></a><a name="p139859148535"></a>哪些区域的ModelArts可以使用</p>
</td>
<td class="cellrowborder" valign="top" width="33.73337333733373%" headers="mcps1.2.4.1.2 "><p id="p498541419539"><a name="p498541419539"></a><a name="p498541419539"></a>华北-北京一</p>
<p id="p1313174405315"><a name="p1313174405315"></a><a name="p1313174405315"></a>华北-北京四</p>
</td>
<td class="cellrowborder" valign="top" width="37.27372737273727%" headers="mcps1.2.4.1.3 "><p id="p89855145535"><a name="p89855145535"></a><a name="p89855145535"></a>华北-北京一</p>
</td>
</tr>
<tr id="row9985191416538"><td class="cellrowborder" valign="top" width="28.992899289928992%" headers="mcps1.2.4.1.1 "><p id="p1498541415537"><a name="p1498541415537"></a><a name="p1498541415537"></a>通用类型</p>
</td>
<td class="cellrowborder" valign="top" width="33.73337333733373%" headers="mcps1.2.4.1.2 "><a name="ul119646323224"></a><a name="ul119646323224"></a><ul id="ul119646323224"><li>发布（支持）</li><li>订阅（支持）</li><li>计费（即将支持）</li></ul>
</td>
<td class="cellrowborder" valign="top" width="37.27372737273727%" headers="mcps1.2.4.1.3 "><a name="ul9763111922215"></a><a name="ul9763111922215"></a><ul id="ul9763111922215"><li>发布（不支持）</li><li>订阅（支持）</li><li>计费（不支持）</li></ul>
</td>
</tr>
<tr id="row1998541425319"><td class="cellrowborder" valign="top" width="28.992899289928992%" headers="mcps1.2.4.1.1 "><p id="p13985101418533"><a name="p13985101418533"></a><a name="p13985101418533"></a>API</p>
</td>
<td class="cellrowborder" valign="top" width="33.73337333733373%" headers="mcps1.2.4.1.2 "><a name="ul1145364632216"></a><a name="ul1145364632216"></a><ul id="ul1145364632216"><li>发布（即将支持）</li><li>订阅（即将支持）</li><li>计费（即将支持）</li></ul>
</td>
<td class="cellrowborder" valign="top" width="37.27372737273727%" headers="mcps1.2.4.1.3 "><a name="ul17210105522218"></a><a name="ul17210105522218"></a><ul id="ul17210105522218"><li>发布（支持）</li><li>订阅（支持）</li><li>计费（不支持）</li></ul>
</td>
</tr>
<tr id="row1798541475314"><td class="cellrowborder" valign="top" width="28.992899289928992%" headers="mcps1.2.4.1.1 "><p id="p1498561419533"><a name="p1498561419533"></a><a name="p1498561419533"></a>数据集</p>
</td>
<td class="cellrowborder" valign="top" width="33.73337333733373%" headers="mcps1.2.4.1.2 "><a name="ul1949211915236"></a><a name="ul1949211915236"></a><ul id="ul1949211915236"><li>发布（即将支持）</li><li>下载（即将支持）</li></ul>
</td>
<td class="cellrowborder" valign="top" width="37.27372737273727%" headers="mcps1.2.4.1.3 "><a name="ul886315555226"></a><a name="ul886315555226"></a><ul id="ul886315555226"><li>发布（不支持）</li><li>下载（支持）</li></ul>
</td>
</tr>
<tr id="row1298514149531"><td class="cellrowborder" valign="top" width="28.992899289928992%" headers="mcps1.2.4.1.1 "><p id="p8986214115317"><a name="p8986214115317"></a><a name="p8986214115317"></a>其他</p>
</td>
<td class="cellrowborder" valign="top" width="33.73337333733373%" headers="mcps1.2.4.1.2 "><a name="ul138011436202318"></a><a name="ul138011436202318"></a><ul id="ul138011436202318"><li>汉化（支持）</li><li>跨Region（支持）</li></ul>
</td>
<td class="cellrowborder" valign="top" width="37.27372737273727%" headers="mcps1.2.4.1.3 "><a name="ul1153183815231"></a><a name="ul1153183815231"></a><ul id="ul1153183815231"><li>汉化（支持）</li><li>跨Region（不支持）</li></ul>
</td>
</tr>
</tbody>
</table>

## 如何进入AI市场（新版）<a name="section211522285916"></a>

进入ModelArts管理控制台，在左侧菜单栏中选择“AI市场“。如果您的ModelArts所在区域为“华北-北京一“，那么会同时存在新版和旧版，您可以在弹出的对话框中选择您需要的版本，进入AI市场。如果您的ModelArts所在区域为“华北-北京四“，那么将直接进入新版AI市场。

对于首次使用AI市场的用户，需要在AI市场中完成注册后再使用其功能。

1.  单击页面内任意模型，界面将自动跳转至“注册“页面。
2.  根据界面信息填写“昵称“和“邮箱“，在“邮箱“填写完成后，单击“获取验证码“。

    等待几分钟后，您填写的邮箱将收到华为云发送的邮件，邮件内容中包含验证码。将验证码填写至注册信息中，根据实际情况勾选“接收推送和更新，您可以随时退订“，然后单击“确定“完成注册。

    **图 1**  注册AI市场的账号<a name="fig165798584540"></a>  
    ![](figures/注册AI市场的账号.png "注册AI市场的账号")


## 公共<a name="section1146019364595"></a>

进入AI市场（新版），界面自动进入“公共“页签，展示AI市场内其他人共享的模型。

-   **查找模型**

    在“公共“页签下，您可以通过如下三种方式快速查找所需模型。

    -   方式1：在搜索框中，输入关键词，AI市场会自动在所有的模型中搜索与关键词相关的模型。
    -   方式2：在左侧的导航栏中，通过“类别“或“供应商“过滤模型，筛选出您想要的模型。
    -   方式3：在右上角的分类下拉框中，选择你所需的分类，筛选出您想要的模型。目前有“最近更新“、“最近发布“、“最多收藏“、“最多浏览“和“最多订阅“五种类别。

    **图 2**  查找模型<a name="fig82631345436"></a>  
    ![](figures/查找模型.png "查找模型")

-   **查看模型详情**

    在“公共“、“我的模型“、“收藏夹“等页签下，仅展示模型的基本信息，如果想要了解详细信息，可单击模型所在区块进入详情页面。

    在模型详情页面，将展示此模型的描述、价格、版本、Demo、品评等信息，详细内容请从界面获取。

-   **订阅模型**

    在模型详情页面中，单击“订阅“，进入“订单详情“页面，根据界面提示填写详细配置，如“模型版本“、“配置目标副本“等。模型订阅成功后，您可以从“AI市场用户中心“的“我的购买“页面查看此订阅的模型。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >针对ModelArts提供的官方模型，订阅费用为0。针对其他用户发布至AI市场的模型，会根据发布者的设置收取相应的费用，请通过模型详情了解具体费用，也可以在订阅过程的订单中了解详细费用。  

    **图 3**  配置订阅信息<a name="fig1169519123319"></a>  
    ![](figures/配置订阅信息.png "配置订阅信息")

-   **收藏模型**

    在模型详情页面中，单击右上角的![](figures/icon_37.png)，收藏此模型。模型收藏成功后，您可以在“ModelHub \> 收藏夹“页签下查看您收藏的所有模型。


## 分享或查看我的模型<a name="section1727217378401"></a>

-   **在AI市场分享模型**
    1.  在“ModelHub \> 公共“页面，单击“新建“可新建一个模型，即将您的模型分享至AI市场中。
    2.  在“新建云端模型“页面，填写相关信息，然后单击立即创建。

        **图 4**  新建云端模型<a name="fig127735201602"></a>  
        ![](figures/新建云端模型.png "新建云端模型")

        **表 2**  参数说明

        <a name="table1480764012018"></a>
        <table><thead align="left"><tr id="row20808104016011"><th class="cellrowborder" valign="top" width="30.81%" id="mcps1.2.3.1.1"><p id="p1780817401008"><a name="p1780817401008"></a><a name="p1780817401008"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="69.19%" id="mcps1.2.3.1.2"><p id="p8808340709"><a name="p8808340709"></a><a name="p8808340709"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row980818401207"><td class="cellrowborder" valign="top" width="30.81%" headers="mcps1.2.3.1.1 "><p id="p188081740709"><a name="p188081740709"></a><a name="p188081740709"></a><span class="parmname" id="parmname119428381124"><a name="parmname119428381124"></a><a name="parmname119428381124"></a>“商品类别”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="69.19%" headers="mcps1.2.3.1.2 "><a name="ul193331553110"></a><a name="ul193331553110"></a><ul id="ul193331553110"><li>ModelArts：表示新建的模型可用于ModelArts。</li><li>HoloSens：表示新建的模型可用于SDC。</li></ul>
        </td>
        </tr>
        <tr id="row680812405014"><td class="cellrowborder" valign="top" width="30.81%" headers="mcps1.2.3.1.1 "><p id="p280819401004"><a name="p280819401004"></a><a name="p280819401004"></a><span class="parmname" id="parmname570055119404"><a name="parmname570055119404"></a><a name="parmname570055119404"></a>“商品标题”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="69.19%" headers="mcps1.2.3.1.2 "><p id="p128085406010"><a name="p128085406010"></a><a name="p128085406010"></a>在市场显示的模型名称，建议按照您的模型实现目的设置。</p>
        </td>
        </tr>
        <tr id="row1180854020018"><td class="cellrowborder" valign="top" width="30.81%" headers="mcps1.2.3.1.1 "><p id="p18082401408"><a name="p18082401408"></a><a name="p18082401408"></a><span class="parmname" id="parmname127025516402"><a name="parmname127025516402"></a><a name="parmname127025516402"></a>“Modelarts区域”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="69.19%" headers="mcps1.2.3.1.2 "><p id="p158085405013"><a name="p158085405013"></a><a name="p158085405013"></a>目前ModelArts只支持<span class="parmname" id="parmname206199231620"><a name="parmname206199231620"></a><a name="parmname206199231620"></a>“华北-北京一”</span>和<span class="parmname" id="parmname0142726420"><a name="parmname0142726420"></a><a name="parmname0142726420"></a>“华北-北京四”</span>，因此此参数的可选值只有这两个。</p>
        </td>
        </tr>
        <tr id="row1080813401901"><td class="cellrowborder" valign="top" width="30.81%" headers="mcps1.2.3.1.1 "><p id="p68088401018"><a name="p68088401018"></a><a name="p68088401018"></a><span class="parmname" id="parmname970410518404"><a name="parmname970410518404"></a><a name="parmname970410518404"></a>“模型名称”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="69.19%" headers="mcps1.2.3.1.2 "><p id="p18808440007"><a name="p18808440007"></a><a name="p18808440007"></a>输入模型的名称，从ModelArts的<span class="parmname" id="parmname17912413124120"><a name="parmname17912413124120"></a><a name="parmname17912413124120"></a>“模型管理”</span>中搜索对应的模型，并快速获取您分享的模型。</p>
        </td>
        </tr>
        <tr id="row1680812401003"><td class="cellrowborder" valign="top" width="30.81%" headers="mcps1.2.3.1.1 "><p id="p138084401105"><a name="p138084401105"></a><a name="p138084401105"></a><span class="parmname" id="parmname1270525164015"><a name="parmname1270525164015"></a><a name="parmname1270525164015"></a>“模型版本”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="69.19%" headers="mcps1.2.3.1.2 "><p id="p580817401201"><a name="p580817401201"></a><a name="p580817401201"></a>在选择对应的模型后，您可以选择其版本。此处的<span class="parmname" id="parmname12748813410"><a name="parmname12748813410"></a><a name="parmname12748813410"></a>“模型版本”</span>和<span class="parmname" id="parmname14634135954020"><a name="parmname14634135954020"></a><a name="parmname14634135954020"></a>“模型名称”</span>与ModelArts的<span class="parmname" id="parmname145072058411"><a name="parmname145072058411"></a><a name="parmname145072058411"></a>“模型管理”</span>页面一致。</p>
        </td>
        </tr>
        <tr id="row554416315215"><td class="cellrowborder" valign="top" width="30.81%" headers="mcps1.2.3.1.1 "><p id="p1545103114212"><a name="p1545103114212"></a><a name="p1545103114212"></a><span class="parmname" id="parmname67071651194015"><a name="parmname67071651194015"></a><a name="parmname67071651194015"></a>“模型ID”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="69.19%" headers="mcps1.2.3.1.2 "><p id="p1054514311622"><a name="p1054514311622"></a><a name="p1054514311622"></a>系统自动定义，根据您选择<span class="parmname" id="parmname1516384524014"><a name="parmname1516384524014"></a><a name="parmname1516384524014"></a>“模型名称”</span>和<span class="parmname" id="parmname114214924018"><a name="parmname114214924018"></a><a name="parmname114214924018"></a>“模型版本”</span>会显示其详细对应的ID。</p>
        </td>
        </tr>
        <tr id="row155461531623"><td class="cellrowborder" valign="top" width="30.81%" headers="mcps1.2.3.1.1 "><p id="p75467319219"><a name="p75467319219"></a><a name="p75467319219"></a><span class="parmname" id="parmname1570845154011"><a name="parmname1570845154011"></a><a name="parmname1570845154011"></a>“拥有者”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="69.19%" headers="mcps1.2.3.1.2 "><p id="p14546031828"><a name="p14546031828"></a><a name="p14546031828"></a>此模型的拥有者名称，即您的账户名。此处不可编辑。</p>
        </td>
        </tr>
        <tr id="row115461931427"><td class="cellrowborder" valign="top" width="30.81%" headers="mcps1.2.3.1.1 "><p id="p165461531622"><a name="p165461531622"></a><a name="p165461531622"></a><span class="parmname" id="parmname070918513404"><a name="parmname070918513404"></a><a name="parmname070918513404"></a>“权限”</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="69.19%" headers="mcps1.2.3.1.2 "><p id="p954613314218"><a name="p954613314218"></a><a name="p954613314218"></a>设置此模型的公开权限。可选：<span class="parmname" id="parmname1174820824017"><a name="parmname1174820824017"></a><a name="parmname1174820824017"></a>“公开”</span>、<span class="parmname" id="parmname0210151174013"><a name="parmname0210151174013"></a><a name="parmname0210151174013"></a>“私有”</span>或者<span class="parmname" id="parmname1739313924012"><a name="parmname1739313924012"></a><a name="parmname1739313924012"></a>“白名单用户组”</span>。</p>
        <a name="ul1391317012413"></a><a name="ul1391317012413"></a><ul id="ul1391317012413"><li><span class="parmname" id="parmname1864732110405"><a name="parmname1864732110405"></a><a name="parmname1864732110405"></a>“公开”</span>：表示所有可以使用AI市场的用户都可以看到并使用您的模型。</li><li><span class="parmname" id="parmname695042394020"><a name="parmname695042394020"></a><a name="parmname695042394020"></a>“私有”</span>：表示只有当前账号可以使用此模型。</li><li><span class="parmname" id="parmname1776913613404"><a name="parmname1776913613404"></a><a name="parmname1776913613404"></a>“白名单用户组”</span>：针对ModelArts白名单列表的用户，都可以使用您新建的模型。</li></ul>
        </td>
        </tr>
        </tbody>
        </table>

    3.  模型创建成功后，将罗列在“ModelHub \> 公共“页面。

-   **查看我的模型**

    如果您已经有将模型分享至AI市场，那么您可以进入“ModelHub \> 我的模型“页面，查看您分享的模型。可单击模型进入模型详情页。


