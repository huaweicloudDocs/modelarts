# 人工标注API&SDK对应关系<a name="modelarts_04_0034"></a>

<a name="table38711346123618"></a>
<table><thead align="left"><tr id="row16664714366"><th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.1.4.1.1"><p id="p1674715365"><a name="p1674715365"></a><a name="p1674715365"></a>Class</p>
</th>
<th class="cellrowborder" valign="top" width="31.313131313131308%" id="mcps1.1.4.1.2"><p id="p2610473369"><a name="p2610473369"></a><a name="p2610473369"></a>Method</p>
</th>
<th class="cellrowborder" valign="top" width="46.464646464646464%" id="mcps1.1.4.1.3"><p id="p061747153616"><a name="p061747153616"></a><a name="p061747153616"></a>API</p>
</th>
</tr>
</thead>
<tbody><tr id="row261347193611"><td class="cellrowborder" rowspan="10" valign="top" width="22.222222222222225%" headers="mcps1.1.4.1.1 "><p id="p6809184372513"><a name="p6809184372513"></a><a name="p6809184372513"></a>DataAnnotationsApi</p>
</td>
<td class="cellrowborder" valign="top" width="31.313131313131308%" headers="mcps1.1.4.1.2 "><p id="p13809104342517"><a name="p13809104342517"></a><a name="p13809104342517"></a>show_images_by_tag</p>
</td>
<td class="cellrowborder" valign="top" width="46.464646464646464%" headers="mcps1.1.4.1.3 "><p id="p328831933415"><a name="p328831933415"></a><a name="p328831933415"></a>GET /v1/{project_id}/data-annotations/{data_annotation_id}/images</p>
</td>
</tr>
<tr id="row4614475368"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1899282021517"><a name="p1899282021517"></a><a name="p1899282021517"></a>modify_image_info</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p739881812411"><a name="p739881812411"></a><a name="p739881812411"></a>PUT /v1/{project_id}/data-annotations/{data_annotation_id}/images</p>
</td>
</tr>
<tr id="row4774715365"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p6645102111155"><a name="p6645102111155"></a><a name="p6645102111155"></a>delete_selected_image</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p177082201848"><a name="p177082201848"></a><a name="p177082201848"></a>DELETE /v1/{project_id}/data-annotations/{data_annotation_id}/images/{image_id}</p>
</td>
</tr>
<tr id="row167134753620"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p7792192116150"><a name="p7792192116150"></a><a name="p7792192116150"></a>delete_selected_images</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p38127215411"><a name="p38127215411"></a><a name="p38127215411"></a>POST /v1/{project_id}/data-annotations/{data_annotation_id}/images/delete</p>
</td>
</tr>
<tr id="row1571747123618"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1038312615357"><a name="p1038312615357"></a><a name="p1038312615357"></a>get_image_info_by_id</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p24171141294"><a name="p24171141294"></a><a name="p24171141294"></a>GET /v1/{project_id}/data-annotations/{data_annotation_id}/images/{image_id}/tags</p>
</td>
</tr>
<tr id="row0712475364"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p3118441288"><a name="p3118441288"></a><a name="p3118441288"></a>get_image_info_by_ids</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p734941512914"><a name="p734941512914"></a><a name="p734941512914"></a>POST /v1/{project_id}/data-annotations/{data_annotation_id}/tags/show</p>
</td>
</tr>
<tr id="row97174703612"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p49991543132811"><a name="p49991543132811"></a><a name="p49991543132811"></a>query_tag_list</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1082842016920"><a name="p1082842016920"></a><a name="p1082842016920"></a>Get /v1/{project_id}/data-annotations/{data_annotation_id}/tags</p>
</td>
</tr>
<tr id="row107194753615"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p387645318264"><a name="p387645318264"></a><a name="p387645318264"></a>get_tag_statistics</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p178245266360"><a name="p178245266360"></a><a name="p178245266360"></a>GET /v1/{project_id1}/data-annotations/{data_annotation_id}/tags/stats</p>
</td>
</tr>
<tr id="row9954714363"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p11081846273"><a name="p11081846273"></a><a name="p11081846273"></a>sync_obs</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1797328183711"><a name="p1797328183711"></a><a name="p1797328183711"></a>POST /v1/{project_id}/data-annotations/{data_annotation_id}/obs/sync</p>
</td>
</tr>
<tr id="row09104714364"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p13901104114285"><a name="p13901104114285"></a><a name="p13901104114285"></a>sync_obs_status</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p15621101811370"><a name="p15621101811370"></a><a name="p15621101811370"></a>GET /v1/{project_id}/data-annotations/{data_annotation_id}/obs/sync-status</p>
</td>
</tr>
<tr id="row31287371755"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.1.4.1.1 "><p id="p14129737954"><a name="p14129737954"></a><a name="p14129737954"></a>LabelApi</p>
</td>
<td class="cellrowborder" valign="top" width="31.313131313131308%" headers="mcps1.1.4.1.2 "><p id="p131291537851"><a name="p131291537851"></a><a name="p131291537851"></a>query_validation</p>
</td>
<td class="cellrowborder" valign="top" width="46.464646464646464%" headers="mcps1.1.4.1.3 "><p id="p267372013119"><a name="p267372013119"></a><a name="p267372013119"></a>GET /v1/{ project _id}/annotation-jobs/{job_id}/validation</p>
</td>
</tr>
</tbody>
</table>

