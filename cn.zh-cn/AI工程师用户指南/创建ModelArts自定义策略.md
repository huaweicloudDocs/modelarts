# 创建ModelArts自定义策略<a name="modelarts_23_0080"></a>

如果系统预置的ModelArts权限，不满足您的授权要求，可以创建自定义策略。自定义策略中可以添加的授权项（Action）请参考[《ModelArts API参考》\>权限策略和授权项](https://support.huaweicloud.com/api-modelarts/modelarts_03_0146.html)。

目前华为云支持以下两种方式创建自定义策略：

-   可视化视图创建自定义策略：无需了解策略语法，按可视化视图导航栏选择云服务、操作、资源、条件等策略内容，可自动生成策略。
-   JSON视图创建自定义策略：可以在选择策略模板后，根据具体需求编辑策略内容；也可以直接在编辑框内编写JSON格式的策略内容。

具体创建步骤请参见：[创建自定义策略](https://support.huaweicloud.com/usermanual-iam/iam_01_0605.html)。本章为您介绍常用的[ModelArts依赖的OBS权限自定义策略样例](#section3734428121013)和[ModelArts自定义策略样例](#section1493518251395)。

## 注意事项<a name="section989464119514"></a>

-   由于ModelArts的使用权限依赖OBS服务的授权，您需要为用户授予OBS的系统权限。
-   如果一个自定义策略中包含多个服务的授权语句，这些服务必须是同一属性，即都是“全局级服务“或者“项目级服务“。
-   如果需要同时设置全局服务和项目级服务的自定义策略，请创建两条自定义策略，“作用范围“别为“全局级服务“以及“项目级服务“，然后给用户同时授予这两条自定义策略。
-   针对当前帐号下创建的IAM用户，默认具备ModelArts的所有操作权限，当需要对IAM用户进行权限控制，如拒绝某用户使用某功能的权限时，可通过创建ModelArts自定义策略实现。

## ModelArts依赖的OBS权限自定义策略样例<a name="section3734428121013"></a>

由于ModelArts为“项目级服务“，OBS为“全局级服务“，因此需要分别创建自定义策略然后授予用户。如下示例为ModelArts依赖OBS服务的最小化权限项，包含OBS桶和OBS对象的权限。授予示例中的权限您可以通过ModelArts正常访问OBS不受限制。

```
{
    "Version": "1.1",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "obs:object:PutObjectAcl",
                "obs:bucket:PutBucketAcl",
                "obs:bucket:PutBucketPolicy",
                "obs:bucket:HeadBucket",
                "obs:bucket:ListAllMyBuckets",
                "obs:bucket:ListBucket",
                "obs:object:DeleteObjectVersion",
                "obs:object:AbortMultipartUpload",
                "obs:object:DeleteObject",
                "obs:object:PutObject",
                "obs:bucket:CreateBucket",
                "obs:object:GetObject",
                "obs:bucket:GetBucketLocation",
                "obs:object:GetObjectVersionAcl",
                "obs:bucket:GetBucketAcl",
                "obs:object:ListMultipartUploadParts",
                "obs:bucket:ListBucketVersions",
                "obs:object:GetObjectVersion",
                "obs:object:GetObjectAcl",
                "obs:bucket:GetBucketPolicy"
            ]
        }
    ]
}
```

## ModelArts自定义策略样例<a name="section1493518251395"></a>

针对当前帐号下创建的IAM用户，默认具备ModelArts的所有操作权限，当需要对IAM用户进行权限控制，如拒绝某用户使用某功能的权限时，可参考如下样例进行配置。

-   示例：拒绝用户删除自动学习项目

    拒绝策略需要同时配合其他策略使用，否则没有实际作用。用户被授予的策略中，一个授权项的作用如果同时存在Allow和Deny，则遵循Deny优先。

    如果您给用户授予ModelArts FullAccess的系统策略，但不希望用户拥有ModelArts FullAccess中定义的删除自动学习项目权限，您可以创建一条拒绝删除自动学习项目的自定义策略，然后同时将ModelArts FullAccess和拒绝策略授予用户，根据Deny优先原则，则用户可以对ModelArts执行除了删除自动学习项目外的所有操作。拒绝策略示例如下：

    ```
    { 
          "Version": "1.1", 
          "Statement": [ 
                { 
    		  "Effect": "Deny", 
                      "Action": [ 
                            "modelarts:exemlProject:delete" 
                      ] 
                } 
          ] 
    }
    ```

-   示例：拒绝用户使用开发环境功能

    此用户的策略配置示例如下所示：

    ```
    { 
        "Version": "1.1", 
        "Statement": [ 
    
            { 
                "Effect": "Deny", 
                "Action": [ 
                    "modelarts:notebook:list", 
                    "modelarts:notebook:create" ,
                    "modelarts:notebook:get" ,
                    "modelarts:notebook:update" ,
                    "modelarts:notebook:delete" ,
                    "modelarts:notebook:action" ,
                    "modelarts:notebook:access" 
                ] 
            } 
        ] 
    }
    ```


