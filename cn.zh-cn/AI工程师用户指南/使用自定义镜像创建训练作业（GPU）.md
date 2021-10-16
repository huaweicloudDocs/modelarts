# 使用自定义镜像创建训练作业（GPU）<a name="modelarts_23_0087"></a>

用户将自定义镜像制作完成并上传至SWR后，可在ModelArts管理控制台，使用自定义镜像创建训练作业，完成模型训练操作。

## 前提条件<a name="section183424508463"></a>

-   已按照ModelArts规范制作自定义镜像包，使用自定义镜像创建训练作业需遵守的规范请参见[训练作业自定义镜像规范](训练作业自定义镜像规范.md)。
-   已将自定义镜像上传至SWR服务，详细操作指导请参见[制作并上传自定义镜像](示例-使用自定义镜像创建训练作业.md#section5491135613409)。

## 创建训练作业<a name="section111622611416"></a>

进入ModelArts管理控制台，参考[创建训练作业](zh-cn_topic_0171858284.md)操作指导，创建训练作业。在使用自定义镜像创建作业时，需关注“算法来源“、“环境变量“和“资源池“参数的设置。

-   **“算法来源“**

    选择“自定义“页签。

    -   “镜像地址“：镜像上传到SWR后生成的地址。

        **图 1**  SWR镜像地址<a name="fig1610311596365"></a>  
        ![](figures/SWR镜像地址.png "SWR镜像地址")

    -   “代码目录“：训练代码文件存储的OBS路径。
    -   “运行命令“：镜像启动后的运行命令，基本格式如下所示：

        **bash /home/work/run\_train.sh  \{UserCommand\}**

        **bash /home/work/run\_train.sh  \[python/bash/..\] \{file\_location\} \{file\_parameter\}**

        “run\_train.sh“为训练启动引导脚本。执行该脚本后，ModelArts将“代码目录“下的所有内容递归下载到容器本地路径，下载后的容器本地路径为  “/home/work/user-job-dir/$\{“代码目录“的最后一级名称\}/“。

        例如，训练代码文件的OBS路径为“obs://obs-bucket/new/train.py“，“代码目录“选择“obs://obs-bucket/new/“时，则下载后的容器本地代码目录对应为“/home/work/user-job-dir/new/“。下载后的容器本地训练代码路径为“/home/work/user-job-dir/new/train.py“，运行命令可以设置为：**bash /home/work/run\_train.sh  python /home/work/user-job-dir/new/train.py \{python\_file\_parameter\}**

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >使用自定义镜像创建训练作业过程中，ModelArts 允许用户完全自定义“运行命令“。“运行命令“中提到以下两种基本格式：
        >**bash /home/work/run\_train.sh  \{UserCommand\}**
        >**bash /home/work/run\_train.sh  \[python/bash/..\] \{file\_location\} \{file\_parameter\}**
        >其中，“run\_train.sh，“为训练启动引导脚本。用户在制作自定义镜像过程中，可以自主实现训练启动引导脚本，也可以提前将训练代码置于自定义镜像环境中，无需遵循上述两种格式，实现完全的自定义“运行命令“。


-   **“环境变量“**

    容器启动后，除了用户在训练作业中自行增加的“环境变量“外，其它加载的环境变量如[表1](#table341782301619)所示。用户可以根据需求来确认在自己训练脚本的python中是否要使用这些环境变量，也可以通过运行命令中的“\{python\_file\_parameter\}“传入相关参数。

    **表 1**  可选环境变量说明

    <a name="table341782301619"></a>
    <table><thead align="left"><tr id="row441882319161"><th class="cellrowborder" valign="top" width="23.1%" id="mcps1.2.3.1.1"><p id="p94186234169"><a name="p94186234169"></a><a name="p94186234169"></a>环境变量</p>
    </th>
    <th class="cellrowborder" valign="top" width="76.9%" id="mcps1.2.3.1.2"><p id="p3418123121615"><a name="p3418123121615"></a><a name="p3418123121615"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row241812311611"><td class="cellrowborder" valign="top" width="23.1%" headers="mcps1.2.3.1.1 "><p id="p164181323131617"><a name="p164181323131617"></a><a name="p164181323131617"></a>DLS_TASK_INDEX</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.9%" headers="mcps1.2.3.1.2 "><p id="p124185233169"><a name="p124185233169"></a><a name="p124185233169"></a>当前容器索引，容器从0开始编号。</p>
    </td>
    </tr>
    <tr id="row154185239163"><td class="cellrowborder" valign="top" width="23.1%" headers="mcps1.2.3.1.1 "><p id="p241872361615"><a name="p241872361615"></a><a name="p241872361615"></a>DLS_TASK_NUMBER</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.9%" headers="mcps1.2.3.1.2 "><p id="p2418162314161"><a name="p2418162314161"></a><a name="p2418162314161"></a>容器总数。对应<span class="parmname" id="parmname17648115913216"><a name="parmname17648115913216"></a><a name="parmname17648115913216"></a>“计算节点个数”</span>。</p>
    </td>
    </tr>
    <tr id="row1041882313169"><td class="cellrowborder" valign="top" width="23.1%" headers="mcps1.2.3.1.1 "><p id="p18418162310164"><a name="p18418162310164"></a><a name="p18418162310164"></a>DLS_APP_URL</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.9%" headers="mcps1.2.3.1.2 "><p id="p1041815238164"><a name="p1041815238164"></a><a name="p1041815238164"></a>代码目录。对应界面上<span class="parmname" id="parmname1940417410221"><a name="parmname1940417410221"></a><a name="parmname1940417410221"></a>“代码目录”</span>配置，会加上协议名。比如，可直接使用<span class="filepath" id="filepath1992581272213"><a name="filepath1992581272213"></a><a name="filepath1992581272213"></a>“$DLS_APP_URL/*.py”</span>来读取OBS下的文件。</p>
    </td>
    </tr>
    <tr id="row241812361615"><td class="cellrowborder" valign="top" width="23.1%" headers="mcps1.2.3.1.1 "><p id="p9418823141616"><a name="p9418823141616"></a><a name="p9418823141616"></a>DLS_DATA_URL</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.9%" headers="mcps1.2.3.1.2 "><p id="p541882312164"><a name="p541882312164"></a><a name="p541882312164"></a>数据集位置。对应界面上<span class="parmname" id="parmname13774123032218"><a name="parmname13774123032218"></a><a name="parmname13774123032218"></a>“数据来源”</span>，会加上协议名。</p>
    </td>
    </tr>
    <tr id="row20418162313160"><td class="cellrowborder" valign="top" width="23.1%" headers="mcps1.2.3.1.1 "><p id="p194181923161611"><a name="p194181923161611"></a><a name="p194181923161611"></a>DLS_TRAIN_URL</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.9%" headers="mcps1.2.3.1.2 "><p id="p1341812311164"><a name="p1341812311164"></a><a name="p1341812311164"></a>训练输出位置。对应界面上<span class="parmname" id="parmname95459352228"><a name="parmname95459352228"></a><a name="parmname95459352228"></a>“训练输出位置”</span>，会加上协议名。</p>
    </td>
    </tr>
    <tr id="row10418152320162"><td class="cellrowborder" valign="top" width="23.1%" headers="mcps1.2.3.1.1 "><p id="p28426261819"><a name="p28426261819"></a><a name="p28426261819"></a>BATCH_{jobName}.0_HOSTS（单机）</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.9%" headers="mcps1.2.3.1.2 "><p id="p5277131971917"><a name="p5277131971917"></a><a name="p5277131971917"></a>当选择单机时，即计算节点个数为1时，此环境变量为<span class="parmname" id="parmname76051347132219"><a name="parmname76051347132219"></a><a name="parmname76051347132219"></a>“BATCH_{jobName}.0_HOSTS”</span>。</p>
    <p id="p1741832315165"><a name="p1741832315165"></a><a name="p1741832315165"></a>HOSTS环境变量的格式为<span class="parmname" id="parmname151655217221"><a name="parmname151655217221"></a><a name="parmname151655217221"></a>“hostname:port”</span>。一个容器可以看到同一个作业中所有容器的HOSTS，根据索引的不同，分别为<span class="parmname" id="parmname195191256152212"><a name="parmname195191256152212"></a><a name="parmname195191256152212"></a>“BATCH_CUSTOM0_HOSTS”</span>、<span class="parmname" id="parmname17178659202210"><a name="parmname17178659202210"></a><a name="parmname17178659202210"></a>“BATCH_CUSTOM1_HOSTS”</span>等。当资源池为8GPU规格的专属资源池时， 容器的网络类型为主机网络，并且可以使用主机IB网络加速通信。当使用其他资源池时为容器网络。</p>
    <div class="note" id="note0166476271"><a name="note0166476271"></a><a name="note0166476271"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p61667712273"><a name="p61667712273"></a><a name="p61667712273"></a>使用主机IB网络加速通信时，IPoIB特性需要ip_mapper.py工具获取ib0网卡IP地址。</p>
    </div></div>
    </td>
    </tr>
    </tbody>
    </table>


-   **“资源池“**

    当用户选择GPU类型的资源池时，ModelArts会挂载高速固态硬盘（NVME SSD）至“/cache“目录，用户可以使用此目录来储存临时文件。

    **图 2**  创建训练作业<a name="fig1014015465016"></a>  
    ![](figures/创建训练作业.png "创建训练作业")


## 运行自定义镜像训练作业<a name="section16148199871"></a>

用户上传自定义镜像到SWR后，在创建自定义镜像作业时，默认已经授权ModelArts去获取镜像运行。自定义审核镜像第一次运行的时候，先审核镜像，审核内容请参见[训练作业自定义镜像规范](训练作业自定义镜像规范.md)，审核失败的原因见于日志，用户根据日志做相应的修改。

**图 3**  审核镜像失败<a name="fig1367133992411"></a>  
![](figures/审核镜像失败.png "审核镜像失败")

镜像审核成功后，后台就会开始启动用户自定义镜像容器，开始跑自定义镜像训练作业，用户可根据日志来查看训练情况。

>![](public_sys-resources/icon-note.gif) **说明：** 
>审核成功后，再次使用相同镜像创建训练作业的时候，不会再次审核。

**图 4**  运行日志<a name="fig0343710255"></a>  
![](figures/运行日志.png "运行日志")

