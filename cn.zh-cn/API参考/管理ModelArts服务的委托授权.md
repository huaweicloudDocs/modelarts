# 管理ModelArts服务的委托授权<a name="modelarts_03_0405"></a>

本节通过调用一系列API，以管理ModelArts服务的委托授权为例介绍ModelArts API的使用流程。

## 概述<a name="section1584656102611"></a>

管理ModelArts服务的委托授权流程如下：

1.  调用[认证鉴权](认证鉴权.md)接口获取用户Token，在后续的请求中需要将Token放到请求消息头中作为认证。
2.  调用[创建ModelArts委托](创建ModelArts委托.md)接口完成包含OBS、SWR、IEF等依赖服务的ModelArts委托。
3.  调用[配置授权](配置授权.md)接口配置ModelArts授权。该接口支持管理员给IAM子用户设置委托，支持设置当前用户的访问密钥。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >若没有授权，ModelArts服务的数据管理、训练管理、开发环境、在线服务等功能将不能正常使用。

4.  调用[查看授权列表](查看授权列表.md)接口查看用户的授权信息。
5.  在管理用户授权时，可以调用[删除授权](删除授权.md)接口删除指定用户的授权或者删除全量用户的授权。

## 前提条件<a name="section8774173316262"></a>

-   已获取[IAM的EndPoint](https://developer.huaweicloud.com/endpoint?IAM)和[ModelArts的EndPoint](终端节点.md)。
-   确认服务的部署区域，[获取项目名称和ID](获取项目ID和名称.md)、[获取帐号名和ID](获取帐号名和帐号ID.md)和[获取用户名和ID](获取用户名和用户ID.md)。

## 操作步骤<a name="section18521459111613"></a>

1.  调用[认证鉴权](认证鉴权.md)接口获取用户的Token。
    1.  请求消息体：

        URI格式：POST https://_**\{iam\_endpoint\}**_/v3/auth/tokens

        请求消息头：Content-Type →application/json

        请求Body：

        ```
        {
          "auth": {
            "identity": {
              "methods": ["password"],
              "password": {
                "user": {
                  "name": "user_name", 
                  "password": "user_password",
                  "domain": {
                    "name": "domain_name"  
                  }
                }
              }
            },
            "scope": {
              "project": {
                "name": "cn-north-1"  
              }
            }
          }
        }
        ```

        其中，加粗的斜体字段需要根据实际值填写：

        -   _**iam\_endpoint**_为IAM的终端节点。
        -   **_user\_name_**为IAM用户名。
        -   **_user\_password_**为用户登录密码。
        -   _**domain\_name**_为用户所属的帐号名。
        -   **_cn-north-1_**为项目名，代表服务的部署区域。

    2.  返回状态码“201 Created“，在响应Header中获取“X-Subject-Token“的值即为Token，如下所示：

        ```
        x-subject-token →MIIZmgYJKoZIhvcNAQcCoIIZizCCGYcCAQExDTALBglghkgBZQMEAgEwgXXXXXX...
        ```

2.  调用[创建ModelArts委托](创建ModelArts委托.md)接口完成包含OBS、SWR、IEF等依赖服务的ModelArts委托。
    1.  请求消息体：

        URI：POST https://_**\{endpoint\}**_/v2/_**\{project\_id\}**_/agency

        请求消息头：

        -   X-auth-Token →**_MIIZmgYJKoZIhvcNAQcCoIIZizCCGYcCAQExDTALBglghkgBZQMEAgEwgXXXXXX..._**
        -   Content-Type →application/json

        请求Body：

        ```
        {
          "agency_name_suffix" : "iam-user01"
        }
        ```

        其中，加粗的斜体字段需要根据实际值填写：

        -   _**endpoint**_为ModelArts的终端节点。
        -   _**project\_id**_为用户的项目ID。
        -   “X-auth-Token“是上一步获取到的Token值。
        -   “agency\_name\_suffix“是自定义的委托名称后缀。

    2.  返回状态码“200 OK“表示委托“ma\_agency\_iam-user01“创建成功，响应Body如下所示：

        ```
        {
            "agency_name": "ma_agency_iam-user01"
        }
        ```

3.  调用[配置授权](配置授权.md)接口配置ModelArts授权。该接口支持管理员给IAM子用户设置委托，支持设置当前用户的访问密钥。
    1.  请求消息体：

        URI：POST https://_**\{endpoint\}**_/v2/_**\{project\_id\}**_/authorizations

        请求消息头：

        -   X-auth-Token →**_MIIZmgYJKoZIhvcNAQcCoIIZizCCGYcCAQExDTALBglghkgBZQMEAgEwgXXXXXX..._**
        -   Content-Type →application/json

        请求Body：

        ```
        {
          "user_id": "****af917080f5d21f55c018ba19****",
          "type": "agency",
          "content": "ma_agency_iam-user01"
        }
        ```

        其中，加粗的斜体字段需要根据实际值填写，“user\_id“为IAM用户ID，“content“为上一步创建的ModelArts委托。

    2.  返回状态码“200 OK“表示配置授权完成，响应Body如下所示：

        ```
        {
            "result": true
        }
        ```

4.  调用[查看授权列表](查看授权列表.md)接口查看用户的授权信息。
    1.  请求消息体：

        URI：GET https://_**\{endpoint\}**_/v2/_**\{project\_id\}**_/authorizations

        请求消息头：X-auth-Token →**_MIIZmgYJKoZIhvcNAQcCoIIZizCCGYcCAQExDTALBglghkgBZQMEAgEwgXXXXXX..._**

        其中，加粗的斜体字段需要根据实际值填写。

    2.  返回状态码“200 OK“，响应Body如下所示：

        ```
        {
          "auth": [
            {
              "create_time": 1622804433221,
              "user_id": "all-users",
              "user_name": "all-users",
              "type": "agency",
              "content": "modelarts_agency"
            },
            {
              "create_time": 1625457065365,
              "user_id": "****af917080f5d21f55c018ba19****",
              "user_name": null,
              "type": "agency",
              "content": "ma_agency_iam-user01"
            }
          ],
          "total_count": 2
        }
        ```

        根据响应可以了解用户的授权信息。

5.  在管理用户授权时，可以调用[删除授权](删除授权.md)接口删除指定用户的授权或者删除全量用户的授权。
    1.  请求消息体：

        URI：DELETE https://_**\{endpoint\}**_/v2/_**\{project\_id\}**_/authorizations?user\_id=_**\*\*\*\*d80fb058844ae8b82aa66d9fe\*\*\*\***_

        请求消息头：X-auth-Token →**_MIIZmgYJKoZIhvcNAQcCoIIZizCCGYcCAQExDTALBglghkgBZQMEAgEwgXXXXXX..._**

        其中，加粗的斜体字段需要根据实际值填写，“\*\*\*\*d80fb058844ae8b82aa66d9fe\*\*\*\*”是指定用户的IAM用户ID。

    2.  返回状态码“200 OK“表示删除成功，响应Body如下所示：

        ```
        {
            "result": true
        }
        ```



