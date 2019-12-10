# 开发环境API&SDK对应关系<a name="modelarts_04_0120"></a>

<a name="table38711346123618"></a>
<table><thead align="left"><tr id="row16664714366"><th class="cellrowborder" valign="top" width="16%" id="mcps1.1.4.1.1"><p id="p1674715365"><a name="p1674715365"></a><a name="p1674715365"></a>Class</p>
</th>
<th class="cellrowborder" valign="top" width="32%" id="mcps1.1.4.1.2"><p id="p2610473369"><a name="p2610473369"></a><a name="p2610473369"></a>Method</p>
</th>
<th class="cellrowborder" valign="top" width="52%" id="mcps1.1.4.1.3"><p id="p061747153616"><a name="p061747153616"></a><a name="p061747153616"></a>API</p>
</th>
</tr>
</thead>
<tbody><tr id="row6664763620"><td class="cellrowborder" rowspan="7" valign="top" width="16%" headers="mcps1.1.4.1.1 "><p id="p1323434514135"><a name="p1323434514135"></a><a name="p1323434514135"></a>InstanceApi</p>
</td>
<td class="cellrowborder" valign="top" width="32%" headers="mcps1.1.4.1.2 "><p id="p136842526136"><a name="p136842526136"></a><a name="p136842526136"></a>get_instance_token</p>
</td>
<td class="cellrowborder" valign="top" width="52%" headers="mcps1.1.4.1.3 "><p id="p1779135015217"><a name="p1779135015217"></a><a name="p1779135015217"></a>GET /v1/{project_id}/demanager/instances/{instance_id}/token</p>
</td>
</tr>
<tr id="row1066479361"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p161778447104"><a name="p161778447104"></a><a name="p161778447104"></a>create_instance</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p11172550192116"><a name="p11172550192116"></a><a name="p11172550192116"></a>POST /v1/{project_id}/demanager/instances</p>
</td>
</tr>
<tr id="row1644713368"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p623164420103"><a name="p623164420103"></a><a name="p623164420103"></a>get_instance_list</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p14328115018211"><a name="p14328115018211"></a><a name="p14328115018211"></a>GET /v1/{project_id}/demanager/instances?de_type={de_type}&amp;provision_type={provision_type}&amp;status={status}&amp;sortby={sortby}&amp;order={order}&amp;offset={offset}&amp;limit={limit}</p>
</td>
</tr>
<tr id="row6610478363"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p96549442108"><a name="p96549442108"></a><a name="p96549442108"></a>get_instance</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p34616504217"><a name="p34616504217"></a><a name="p34616504217"></a>GET /v1/{project_id}/demanager/instances/{instance_id}</p>
</td>
</tr>
<tr id="row13834141901412"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p148351419101410"><a name="p148351419101410"></a><a name="p148351419101410"></a>update_instance</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p79591836105810"><a name="p79591836105810"></a><a name="p79591836105810"></a>PUT /v1/{project_id}/demanager/instances/{instance_id}</p>
</td>
</tr>
<tr id="row114871251143"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p14487132531412"><a name="p14487132531412"></a><a name="p14487132531412"></a>delete_instance</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p19640185014212"><a name="p19640185014212"></a><a name="p19640185014212"></a>DELETE /v1/{project_id}/demanager/instances/{instance_id}</p>
</td>
</tr>
<tr id="row72001244111417"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p42001344121414"><a name="p42001344121414"></a><a name="p42001344121414"></a>change_instance_status</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1189215042114"><a name="p1189215042114"></a><a name="p1189215042114"></a>POST /v1/{project_id}/demanager/instances/{instance_id}/action</p>
</td>
</tr>
</tbody>
</table>

