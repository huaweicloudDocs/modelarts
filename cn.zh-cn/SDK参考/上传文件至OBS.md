# 上传文件至OBS<a name="modelarts_04_0126"></a>

## 示例代码<a name="zh-cn_topic_0173848862_section20261580353"></a>

```
from modelarts.session import Session
session = Session()
```

-   上传单个文件

    ```
    session.upload_data(bucket_path="/bucket_name/dir1/", path="/home/user/sdk/sdk.txt")
    ```


-   上传多个文件

    ```
    local_file_list = ["/home/user/sdk1.txt", "/opt/sdk2.txt", "/etc/sdk3.txt"]
    session.upload_data(bucket_path="/bucket_name/dir1/", path=local_file_list)
    ```


## 参数说明<a name="zh-cn_topic_0173848862_section520413412065"></a>

**表 1**  请求参数说明

<a name="zh-cn_topic_0173848862_table155461191218"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173848862_row254817912212"><th class="cellrowborder" valign="top" width="19.869999999999997%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0173848862_p12549899214"><a name="zh-cn_topic_0173848862_p12549899214"></a><a name="zh-cn_topic_0173848862_p12549899214"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="11.32%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0173848862_p3552101193813"><a name="zh-cn_topic_0173848862_p3552101193813"></a><a name="zh-cn_topic_0173848862_p3552101193813"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="14.32%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0173848862_p1755169172118"><a name="zh-cn_topic_0173848862_p1755169172118"></a><a name="zh-cn_topic_0173848862_p1755169172118"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="54.49%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0173848862_p55521998211"><a name="zh-cn_topic_0173848862_p55521998211"></a><a name="zh-cn_topic_0173848862_p55521998211"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173848862_row8893215413"><td class="cellrowborder" valign="top" width="19.869999999999997%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0173848862_p6891421842"><a name="zh-cn_topic_0173848862_p6891421842"></a><a name="zh-cn_topic_0173848862_p6891421842"></a>modelarts_session</p>
</td>
<td class="cellrowborder" valign="top" width="11.32%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173848862_p68972047"><a name="zh-cn_topic_0173848862_p68972047"></a><a name="zh-cn_topic_0173848862_p68972047"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.32%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173848862_p158912219419"><a name="zh-cn_topic_0173848862_p158912219419"></a><a name="zh-cn_topic_0173848862_p158912219419"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="54.49%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0173848862_p1689152543"><a name="zh-cn_topic_0173848862_p1689152543"></a><a name="zh-cn_topic_0173848862_p1689152543"></a>会话对象。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173848862_row1530181931"><td class="cellrowborder" valign="top" width="19.869999999999997%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0173848862_p8675871731"><a name="zh-cn_topic_0173848862_p8675871731"></a><a name="zh-cn_topic_0173848862_p8675871731"></a>bucket_path</p>
</td>
<td class="cellrowborder" valign="top" width="11.32%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173848862_p6675978319"><a name="zh-cn_topic_0173848862_p6675978319"></a><a name="zh-cn_topic_0173848862_p6675978319"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.32%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173848862_p46751171339"><a name="zh-cn_topic_0173848862_p46751171339"></a><a name="zh-cn_topic_0173848862_p46751171339"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.49%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0173848862_p467516712319"><a name="zh-cn_topic_0173848862_p467516712319"></a><a name="zh-cn_topic_0173848862_p467516712319"></a>OBS桶路径。格式为：<span class="filepath" id="filepath1435244614914"><a name="filepath1435244614914"></a><a name="filepath1435244614914"></a>“/bucket_name/dir1/”</span>，其中<span class="parmvalue" id="parmvalue89030542090"><a name="parmvalue89030542090"></a><a name="parmvalue89030542090"></a>“bucket_name”</span>为OBS桶名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173848862_row167932713277"><td class="cellrowborder" valign="top" width="19.869999999999997%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0173848862_p5794079274"><a name="zh-cn_topic_0173848862_p5794079274"></a><a name="zh-cn_topic_0173848862_p5794079274"></a>path</p>
</td>
<td class="cellrowborder" valign="top" width="11.32%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0173848862_p77948710279"><a name="zh-cn_topic_0173848862_p77948710279"></a><a name="zh-cn_topic_0173848862_p77948710279"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.32%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0173848862_p3794167192716"><a name="zh-cn_topic_0173848862_p3794167192716"></a><a name="zh-cn_topic_0173848862_p3794167192716"></a>String/List</p>
</td>
<td class="cellrowborder" valign="top" width="54.49%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0173848862_p461991742117"><a name="zh-cn_topic_0173848862_p461991742117"></a><a name="zh-cn_topic_0173848862_p461991742117"></a>当上传单个文件时，path为本地文件路径； 当上传多个文件时，将本地文件路径放入List中传入。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  失败响应参数说明

<a name="zh-cn_topic_0173848862_table55928961173927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173848862_row40618446173927"><th class="cellrowborder" valign="top" width="24.86%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0173848862_p1631242217407"><a name="zh-cn_topic_0173848862_p1631242217407"></a><a name="zh-cn_topic_0173848862_p1631242217407"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20.75%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0173848862_p5427574117407"><a name="zh-cn_topic_0173848862_p5427574117407"></a><a name="zh-cn_topic_0173848862_p5427574117407"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="54.39000000000001%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0173848862_p12364118914"><a name="zh-cn_topic_0173848862_p12364118914"></a><a name="zh-cn_topic_0173848862_p12364118914"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173848862_row11062410173927"><td class="cellrowborder" valign="top" width="24.86%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173848862_p688954611624"><a name="zh-cn_topic_0173848862_p688954611624"></a><a name="zh-cn_topic_0173848862_p688954611624"></a>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="20.75%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173848862_p3804851211624"><a name="zh-cn_topic_0173848862_p3804851211624"></a><a name="zh-cn_topic_0173848862_p3804851211624"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.39000000000001%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173848862_p156551524172412"><a name="zh-cn_topic_0173848862_p156551524172412"></a><a name="zh-cn_topic_0173848862_p156551524172412"></a>调用失败时的错误码。</p>
<p id="zh-cn_topic_0173848862_p6203060911624"><a name="zh-cn_topic_0173848862_p6203060911624"></a><a name="zh-cn_topic_0173848862_p6203060911624"></a>调用成功时无此字段。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173848862_row52351653173927"><td class="cellrowborder" valign="top" width="24.86%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0173848862_p4368550411624"><a name="zh-cn_topic_0173848862_p4368550411624"></a><a name="zh-cn_topic_0173848862_p4368550411624"></a>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20.75%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0173848862_p6574380911624"><a name="zh-cn_topic_0173848862_p6574380911624"></a><a name="zh-cn_topic_0173848862_p6574380911624"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.39000000000001%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0173848862_p1277593619"><a name="zh-cn_topic_0173848862_p1277593619"></a><a name="zh-cn_topic_0173848862_p1277593619"></a>调用失败时的错误信息。</p>
<p id="zh-cn_topic_0173848862_p2364831411624"><a name="zh-cn_topic_0173848862_p2364831411624"></a><a name="zh-cn_topic_0173848862_p2364831411624"></a>调用成功时无此字段。</p>
</td>
</tr>
</tbody>
</table>

