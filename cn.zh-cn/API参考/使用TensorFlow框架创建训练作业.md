# 使用TensorFlow框架创建训练作业<a name="modelarts_03_0401"></a>

本节通过调用一系列API，以训练模型为例介绍ModelArts API的使用流程。

## 概述<a name="section1584656102611"></a>

使用TensorFlow框架创建训练作业的流程如下：

1.  调用[认证鉴权](认证鉴权.md)接口获取用户Token，在后续的请求中需要将Token放到请求消息头中作为认证。
2.  调用[查询作业资源规格](查询作业资源规格.md)接口获取训练作业支持的资源规格。
3.  调用[查询作业引擎规格](查询作业引擎规格.md)接口查看训练作业的引擎类型和版本。
4.  调用[创建训练作业](创建训练作业.md)接口创建一个训练作业。
5.  调用[查询训练作业版本详情](查询训练作业版本详情.md)接口根据训练作业的ID查询训练作业的创建详情。
6.  调用[获取训练作业日志的文件名](获取训练作业日志的文件名.md)接口获取训练作业日志的文件名。
7.  调用[查询训练作业日志](查询训练作业日志.md)接口查看训练作业的日志详情。
8.  当训练作业使用完成或不再需要时，调用[删除训练作业](删除训练作业.md)接口删除训练作业。

## 前提条件<a name="section8774173316262"></a>

-   已获取[IAM的EndPoint](https://developer.huaweicloud.com/endpoint?IAM)和[ModelArts的EndPoint](终端节点.md)。
-   确认服务的部署区域，[获取项目名称和ID](获取项目ID和名称.md)、[获取帐号名和ID](获取帐号名和帐号ID.md)和[获取用户名和ID](获取用户名和用户ID.md)。

-   已准备好TensorFlow框架的训练代码，例如将启动文件“train\_mnist\_tf.py“存放在OBS的“/test-modelarts/mnist-tensorflow-code/”目录下。
-   已经准备好训练作业的数据集，例如将训练数据集存放在OBS的“/test-modelarts/dataset-mnist/“目录下。
-   已经创建好训练作业的输出位置，例如“/test-modelarts/mnist-model/output/“。

## 操作步骤<a name="section161491156162615"></a>

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

2.  <a name="li384513468342"></a>调用[查询作业资源规格](查询作业资源规格.md)接口获取训练作业支持的资源规格。
    1.  请求消息体：

        URI格式：GET https://_**\{ma\_endpoint\}**_/v1/_**\{project\_id\}**_/job/resource-specs?job\_type=train

        请求消息头：X-auth-Token →**_MIIZmgYJKoZIhvcNAQcCoIIZizCCGYcCAQExDTALBglghkgBZQMEAgEwgXXXXXX..._**

        其中，加粗的斜体字段需要根据实际值填写：

        -   _**ma\_endpoint**_为ModelArts的终端节点。
        -   _**project\_id**_为用户的项目ID。
        -   “X-auth-Token“的值是上一步获取到的Token值。

    2.  返回状态码“200 OK“，响应Body如下所示：

        ```
        {
          "specs": [
            ......
            {
              "spec_id": 7,
              "core": "2",
              "cpu": "8",
              "gpu_num": 0,
              "gpu_type": "",
              "spec_code": "modelarts.vm.cpu.2u",
              "unit_num": 1,
              "max_num": 1,
              "storage": "",
              "interface_type": 1,
              "no_resource": false
            },
            {
              "spec_id": 27,
              "core": "8",
              "cpu": "32",
              "gpu_num": 0,
              "gpu_type": "",
              "spec_code": "modelarts.vm.cpu.8u",
              "unit_num": 1,
              "max_num": 1,
              "storage": "",
              "interface_type": 1,
              "no_resource": false
            }
          ],
          "is_success": true,
          "spec_total_count": 5
        }
        ```

        -   根据“spec\_code“字段选择并记录创建训练作业时需要的规格类型，本章以“modelarts.vm.cpu.8u“为例，并记录“max\_num“字段的值为“1“。
        -   “no\_resource“字段用于判断规格资源是否充足，“false“代表有资源。

3.  <a name="li12845104623418"></a>调用[查询作业引擎规格](查询作业引擎规格.md)接口查看训练作业的引擎类型和版本。
    1.  请求消息体：

        URI格式：GET https://_**\{ma\_endpoint\}**_/v1/_**\{project\_id\}**_/job/ai-engines?job\_type=train

        请求消息头：X-auth-Token →**_MIIZmgYJKoZIhvcNAQcCoIIZizCCGYcCAQExDTALBglghkgBZQMEAgEwgXXXXXX..._**

        其中，加粗的斜体字段需要根据实际值填写。

    2.  返回状态码“200 OK“，响应Body如下所示：

        ```
        {
          "engines": [
            {
              "engine_type": 13,
              "engine_name": "Ascend-Powered-Engine",
              "engine_id": 130,
              "engine_version": "TF-1.15-python3.7-aarch64"
            },
            ......
            {
              "engine_type": 1,
              "engine_name": "TensorFlow",
              "engine_id": 3,
              "engine_version": "TF-1.8.0-python2.7"
            },
            {
              "engine_type": 1,
              "engine_name": "TensorFlow",
              "engine_id": 4,
              "engine_version": "TF-1.8.0-python3.6"
            },
            ......
            {
              "engine_type": 9,
              "engine_name": "XGBoost-Sklearn",
              "engine_id": 100,
              "engine_version": "XGBoost-0.80-Sklearn-0.18.1-python3.6"
            }
          ],
          "is_success": true
        }
        ```

        根据“engine\_name“和“engine\_version“字段选择创建训练作业时需要的引擎规格，并记录对应的“engine\_id“，本章以TensorFlow引擎为例创建作业，记录“engine\_id“为“4“。

4.  <a name="li5845144683416"></a>调用[创建训练作业](创建训练作业.md)接口创建一个基于TensorFlow框架的名称为“jobtest\_TF“的训练作业。
    1.  请求消息体：

        URI格式：POST https://_**\{ma\_endpoint\}**_/v1/_**\{project\_id\}**_/training-jobs

        请求消息头：

        -   X-auth-Token →**_MIIZmgYJKoZIhvcNAQcCoIIZizCCGYcCAQExDTALBglghkgBZQMEAgEwgXXXXXX..._**
        -   Content-Type →application/json

        请求Body：

        ```
        {
            "job_name": "jobtest_TF",
            "job_desc": "TF识别手写数字",
            "config": {
                "worker_server_num": 1,
                "parameter": [],
                "flavor": {
                    "code": "modelarts.vm.cpu.8u"
                },
                "train_url": "/test-modelarts/mnist-model/output/",
                "engine_id": 4,
                "app_url": "/test-modelarts/mnist-tensorflow-code/",
                "boot_file_url": "/test-modelarts/mnist-tensorflow-code/train_mnist_tf.py",
                "data_source": [
                    {
                        "type": "obs",
                        "data_url": "/test-modelarts/dataset-mnist/"
                    }
                ]
            },
            "notification": {
                "topic_urn": "",
                "events": []
            },
            "workspace_id": "0"
        }
        ```

        其中，加粗的斜体字段需要根据实际值填写：

        -   “job\_name“和“job\_desc“填写训练作业的名称和描述。
        -   “worker\_server\_num“和“code“填写[2](#li384513468342)获取的“max\_num“和“spec\_code“的值。
        -   “engine\_id“填写[3](#li12845104623418)获取的引擎ID。
        -   “train\_url“填写训练作业的输出目录。
        -   “app\_url“和“boot\_file\_url“填写训练作业的代码目录和代码启动文件。
        -   “data\_url“填写训练作业使用的数据集目录。

    2.  返回状态码“200 OK“，表示训练作业创建成功，响应Body如下所示：

        ```
        {
          "version_name": "V0001",
          "job_name": "jobtest_TF",
          "create_time": 1609121837000,
          "job_id": 567524,
          "resource_id": "jobaedef089",
          "version_id": 1108482,
          "is_success": true,
          "status": 1
        }
        ```

        -   记录“job\_id“（训练作业的任务ID）和“version\_id“（训练作业的版本ID）字段的值便于后续步骤使用。
        -   “status“为“1“表示训练作业在初始化状态中。

5.  调用[查询训练作业版本详情](查询训练作业版本详情.md)接口根据训练作业的ID查询训练作业的创建详情。
    1.  请求消息体：

        URI格式：GET https://_**\{ma\_endpoint\}**_/v1/_**\{project\_id\}**_/training-jobs/**_\{job\_id\}_**/versions/_**\{version\_id\}**_

        请求消息头：X-auth-Token →**_MIIZmgYJKoZIhvcNAQcCoIIZizCCGYcCAQExDTALBglghkgBZQMEAgEwgXXXXXX..._**

        其中，加粗的斜体字段需要根据实际值填写：

        -   “job\_id“为[4](#li5845144683416)记录的训练作业的任务ID。
        -   “version\_id“为[4](#li5845144683416)记录的训练作业的版本ID。

    2.  返回状态码“200 OK“，响应Body如下所示：

        ```
        {
          "dataset_name": null,
          "duration": 1326,
          "spec_code": "modelarts.vm.cpu.8u",
          "parameter": [],
          "start_time": 1609121913000,
          "model_outputs": [],
          "engine_name": "TensorFlow",
          "error_result": null,
          "gpu_type": "",
          "user_frame_image": null,
          "gpu": null,
          "dataset_id": null,
          "nas_mount_path": null,
          "task_summary": {},
          "max_num": 1,
          "model_metric_list": "{}",
          "is_zombie": null,
          "flavor_code": "modelarts.vm.cpu.8u",
          "gpu_num": 0,
          "train_url": "/test-modelarts/mnist-model/output/",
          "engine_type": 1,
          "job_name": "jobtest_TF",
          "nas_type": "efs",
          "outputs": null,
          "job_id": 567524,
          "data_url": "/test-modelarts/dataset-mnist/",
          "log_url": null,
          "boot_file_url": "/test-modelarts/mnist-tensorflow-code/train_mnist_tf.py",
          "volumes": null,
          "dataset_version_id": null,
          "algorithm_id": null,
          "worker_server_num": 1,
          "pool_type": "SYSTEM_DEFINED",
          "autosearch_config": null,
          "job_desc": "TF识别手写数字",
          "inputs": null,
          "model_id": null,
          "dataset_version_name": null,
          "pool_name": "hec-train-pub-cpu",
          "engine_version": "TF-1.8.0-python3.6",
          "system_metric_list": {
            "recvBytesRate": [
              "0",
              "0"
            ],
            "cpuUsage": [
              "0",
              "0"
            ],
            "sendBytesRate": [
              "0",
              "0"
            ],
            "memUsage": [
              "0",
              "0"
            ],
            "gpuUtil": [
              "0",
              "0"
            ],
            "gpuMemUsage": [
              "0",
              "0"
            ],
            "interval": 1,
            "diskWriteRate": [
              "0",
              "0"
            ],
            "diskReadRate": [
              "0",
              "0"
            ]
          },
          "retrain_model_id": null,
          "version_name": "V0001",
          "pod_version": "1.8.0-cp36",
          "engine_id": 4,
          "status": 10,
          "cpu": "32",
          "user_image_url": null,
          "spec_id": 27,
          "is_success": true,
          "storage": "",
          "nas_share_addr": null,
          "version_id": 1108482,
          "no_resource": false,
          "user_command": null,
          "resource_id": "jobaedef089",
          "core": "8",
          "npu_info": null,
          "app_url": "/test-modelarts/mnist-tensorflow-code/",
          "data_source": [
            {
              "type": "obs",
              "data_url": "/test-modelarts/dataset-mnist/"
            }
          ],
          "pre_version_id": null,
          "create_time": 1609121837000,
          "job_type": 1,
          "pool_id": "pool7d1e384a"
        }
        ```

        根据响应可以了解训练作业的版本详情，其中“status“为“10“表示训练作业已经运行成功。

6.  <a name="li52217241518"></a>调用[获取训练作业日志的文件名](获取训练作业日志的文件名.md)接口获取训练作业日志的文件名。
    1.  请求消息体：

        URI格式：GET https://_**\{ma\_endpoint\}**_/v1/_**\{project\_id\}**_/training-jobs/**_\{job\_id\}_**/versions/_**\{version\_id\}**_/log/file-names

        请求消息头：X-auth-Token →**_MIIZmgYJKoZIhvcNAQcCoIIZizCCGYcCAQExDTALBglghkgBZQMEAgEwgXXXXXX..._**

        其中，加粗的斜体字段需要根据实际值填写。

    2.  返回状态码“200 OK“，响应Body如下所示：

        ```
        {
          "is_success": true,
          "log_file_list": [
            "job-jobtest-tf.0"
          ]
        }
        ```

        表示只存在一个名称为“job-jobtest-tf.0“的日志文件。

7.  调用[查询训练作业日志](查询训练作业日志.md)向下查询8行训练作业日志文件的详细信息。
    1.  请求消息体：

        URI格式：GET https://_**\{ma\_endpoint\}**_/v1/_**\{project\_id\}**_/training-jobs/**_\{job\_id\}_**/versions/_**\{version\_id\}**_/aom-log?log\_file=**_job-jobtest-tf.0_**&lines=**_8_**&order=_**desc**_

        请求消息头：X-auth-Token →**_MIIZmgYJKoZIhvcNAQcCoIIZizCCGYcCAQExDTALBglghkgBZQMEAgEwgXXXXXX..._**

        其中，加粗的斜体字段需要根据实际值填写：

        -   “log\_file“填写[6](#li52217241518)获取的日志文件名。
        -   “lines“填写需要获取的日志长度。
        -   “order“填写日志查询方向。

    2.  返回状态码“200 OK“，响应Body如下所示：

        ```
        {
          "start_line": "1609121886518240330",
          "lines": 8,
          "is_success": true,
          "end_line": "1609121900042593083",
          "content": "Done exporting!\n\n[Modelarts Service Log]Training completed.\n\n[ModelArts Service Log]modelarts-pipe: will create log file /tmp/log/jobtest_TF.log\n\n[ModelArts Service Log]modelarts-pipe: will create log file /tmp/log/jobtest_TF.log\n\n[ModelArts Service Log]modelarts-pipe: will write log file /tmp/log/jobtest_TF.log\n\n[ModelArts Service Log]modelarts-pipe: param for max log length: 1073741824\n\n[ModelArts Service Log]modelarts-pipe: param for whether exit on overflow: 0\n\n[ModelArts Service Log]modelarts-pipe: total length: 23303\n"
        }
        ```

8.  当训练作业使用完成或不再需要时，调用[删除训练作业](删除训练作业.md)接口删除训练作业。
    1.  请求消息体：

        URI格式：GET https://_**\{ma\_endpoint\}**_/v1/_**\{project\_id\}**_/training-jobs/**_\{job\_id\}_**

        请求消息头：X-auth-Token →**_MIIZmgYJKoZIhvcNAQcCoIIZizCCGYcCAQExDTALBglghkgBZQMEAgEwgXXXXXX..._**

        其中，加粗的斜体字段需要根据实际值填写。

    2.  返回状态码“200 OK“表示作业删除成功，响应示例如下：

        ```
        {
          "is_success": true
        }
        ```



