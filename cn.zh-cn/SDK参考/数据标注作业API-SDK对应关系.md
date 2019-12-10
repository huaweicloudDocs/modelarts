# 数据标注作业API&SDK对应关系<a name="modelarts_04_0111"></a>

<a name="table38711346123618"></a>
<table><thead align="left"><tr id="row16664714366"><th class="cellrowborder" valign="top" width="16%" id="mcps1.1.4.1.1"><p id="p1674715365"><a name="p1674715365"></a><a name="p1674715365"></a>Class</p>
</th>
<th class="cellrowborder" valign="top" width="32%" id="mcps1.1.4.1.2"><p id="p2610473369"><a name="p2610473369"></a><a name="p2610473369"></a>Method</p>
</th>
<th class="cellrowborder" valign="top" width="52%" id="mcps1.1.4.1.3"><p id="p061747153616"><a name="p061747153616"></a><a name="p061747153616"></a>API</p>
</th>
</tr>
</thead>
<tbody><tr id="row6664763620"><td class="cellrowborder" rowspan="5" valign="top" width="16%" headers="mcps1.1.4.1.1 "><p id="p1439314065119"><a name="p1439314065119"></a><a name="p1439314065119"></a>LabelApi</p>
<p id="p18567647164720"><a name="p18567647164720"></a><a name="p18567647164720"></a></p>
<p id="p129591249114720"><a name="p129591249114720"></a><a name="p129591249114720"></a></p>
</td>
<td class="cellrowborder" valign="top" width="32%" headers="mcps1.1.4.1.2 "><p id="p1688215573514"><a name="p1688215573514"></a><a name="p1688215573514"></a>create_label_job</p>
</td>
<td class="cellrowborder" valign="top" width="52%" headers="mcps1.1.4.1.3 "><p id="p921686165410"><a name="p921686165410"></a><a name="p921686165410"></a>POST /v1/{project_id}/annotation-jobs</p>
</td>
</tr>
<tr id="row1066479361"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p988135795119"><a name="p988135795119"></a><a name="p988135795119"></a>query_label_jobs</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1933213149546"><a name="p1933213149546"></a><a name="p1933213149546"></a>GET /v1/{ project _id}/annotation-jobs?offset=x&amp;limit=y&amp;sort_by=name&amp;order=desc&amp;search_content=%s%</p>
</td>
</tr>
<tr id="row1644713368"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p2880125765114"><a name="p2880125765114"></a><a name="p2880125765114"></a>delete_label_job</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p13939833105419"><a name="p13939833105419"></a><a name="p13939833105419"></a>DELETE /v1/{ project _id}/annotation-jobs/{job_id}</p>
</td>
</tr>
<tr id="row8567047194716"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1156712475478"><a name="p1156712475478"></a><a name="p1156712475478"></a>mod_label_job</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p356719472473"><a name="p356719472473"></a><a name="p356719472473"></a>PUT /v1/{ project _id}/annotation-jobs/{job_id}</p>
</td>
</tr>
<tr id="row1095974912475"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1095924919471"><a name="p1095924919471"></a><a name="p1095924919471"></a>save_validation</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p29599492473"><a name="p29599492473"></a><a name="p29599492473"></a>POST /v1/{ project _id}/annotation-jobs/{job_id}/validation</p>
</td>
</tr>
</tbody>
</table>

