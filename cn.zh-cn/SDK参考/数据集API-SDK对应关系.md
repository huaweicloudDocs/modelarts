# 数据集API&SDK对应关系<a name="modelarts_04_0019"></a>

<a name="table38711346123618"></a>
<table><thead align="left"><tr id="row16664714366"><th class="cellrowborder" valign="top" width="18.98%" id="mcps1.1.4.1.1"><p id="p1674715365"><a name="p1674715365"></a><a name="p1674715365"></a>Class</p>
</th>
<th class="cellrowborder" valign="top" width="33.57%" id="mcps1.1.4.1.2"><p id="p2610473369"><a name="p2610473369"></a><a name="p2610473369"></a>Method</p>
</th>
<th class="cellrowborder" valign="top" width="47.449999999999996%" id="mcps1.1.4.1.3"><p id="p061747153616"><a name="p061747153616"></a><a name="p061747153616"></a>API</p>
</th>
</tr>
</thead>
<tbody><tr id="row6664763620"><td class="cellrowborder" rowspan="14" valign="top" width="18.98%" headers="mcps1.1.4.1.1 "><p id="p1323434514135"><a name="p1323434514135"></a><a name="p1323434514135"></a>DatasetApi</p>
<p id="p1924951010715"><a name="p1924951010715"></a><a name="p1924951010715"></a></p>
<p id="p4376214178"><a name="p4376214178"></a><a name="p4376214178"></a></p>
</td>
<td class="cellrowborder" valign="top" width="33.57%" headers="mcps1.1.4.1.2 "><p id="p136842526136"><a name="p136842526136"></a><a name="p136842526136"></a>create_dataset</p>
</td>
<td class="cellrowborder" valign="top" width="47.449999999999996%" headers="mcps1.1.4.1.3 "><p id="p999411147168"><a name="p999411147168"></a><a name="p999411147168"></a>POST /v1/{project_id}/datasets</p>
</td>
</tr>
<tr id="row1066479361"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p161778447104"><a name="p161778447104"></a><a name="p161778447104"></a>query_dataset</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1772334651"><a name="p1772334651"></a><a name="p1772334651"></a>GET /v1/{project_id}/datasets</p>
</td>
</tr>
<tr id="row1644713368"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p623164420103"><a name="p623164420103"></a><a name="p623164420103"></a>update_dataset</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p166391430121616"><a name="p166391430121616"></a><a name="p166391430121616"></a>PUT /v1/{project_id}/datasets/{dataset_id</p>
</td>
</tr>
<tr id="row6610478363"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p96549442108"><a name="p96549442108"></a><a name="p96549442108"></a>delete_dataset</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p174290340519"><a name="p174290340519"></a><a name="p174290340519"></a>DELETE /v1/{project_id}/datasets/{dataset_id}</p>
</td>
</tr>
<tr id="row13834141901412"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p148351419101410"><a name="p148351419101410"></a><a name="p148351419101410"></a>create_dataset_version</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p6835101921418"><a name="p6835101921418"></a><a name="p6835101921418"></a>POST /v1/{project_id}/datasets/{dataset_id}/versions</p>
</td>
</tr>
<tr id="row114871251143"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p14487132531412"><a name="p14487132531412"></a><a name="p14487132531412"></a>get_history_dataset_version</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p11487125111411"><a name="p11487125111411"></a><a name="p11487125111411"></a>GET /v1/{project_id}/datasets/{dataset_id}/versions</p>
</td>
</tr>
<tr id="row72001244111417"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p42001344121414"><a name="p42001344121414"></a><a name="p42001344121414"></a>search_dataset_version</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p820013448149"><a name="p820013448149"></a><a name="p820013448149"></a>GET /v1/{project_id}/datasets/{dataset_id}/versions/{version_id}</p>
</td>
</tr>
<tr id="row15870182814148"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p11870112814146"><a name="p11870112814146"></a><a name="p11870112814146"></a>compare_datasets</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1187062817149"><a name="p1187062817149"></a><a name="p1187062817149"></a>GET /v1/{project_id}/datasets/{dataset_id}/versions/difference</p>
</td>
</tr>
<tr id="row150153171413"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p85016315145"><a name="p85016315145"></a><a name="p85016315145"></a>checkout_dataset_version</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1250116313144"><a name="p1250116313144"></a><a name="p1250116313144"></a>PUT /v1/{project_id}/datasets/{dataset_id}/versions/current</p>
</td>
</tr>
<tr id="row18754123351412"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p12754833191413"><a name="p12754833191413"></a><a name="p12754833191413"></a>sync_dataset</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p97541333111417"><a name="p97541333111417"></a><a name="p97541333111417"></a>POST /v1/{project_id}/datasets/{dataset_id}/sync</p>
</td>
</tr>
<tr id="row18781036121418"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1978143611140"><a name="p1978143611140"></a><a name="p1978143611140"></a>delete_file_from_obs</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1978153610147"><a name="p1978153610147"></a><a name="p1978153610147"></a>DELETE /v1/{project_id}/datasets/{dataset_id}/files</p>
</td>
</tr>
<tr id="row354613816147"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p6546238171412"><a name="p6546238171412"></a><a name="p6546238171412"></a>get_task_status</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p154603812147"><a name="p154603812147"></a><a name="p154603812147"></a>GET /v1/{project_id}/datasets/task/{task_id}</p>
</td>
</tr>
<tr id="row1424914104716"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1724914107710"><a name="p1724914107710"></a><a name="p1724914107710"></a>get_dataset</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p2249810871"><a name="p2249810871"></a><a name="p2249810871"></a>GET /v1/{project_id}/datasets/{dataset_id}</p>
</td>
</tr>
<tr id="row1637616141470"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p113765143713"><a name="p113765143713"></a><a name="p113765143713"></a>delete_file_in_version</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1376161414712"><a name="p1376161414712"></a><a name="p1376161414712"></a>PUT /v1/{project_id}/datasets/{dataset_id}/versions/{version_id}</p>
</td>
</tr>
</tbody>
</table>

