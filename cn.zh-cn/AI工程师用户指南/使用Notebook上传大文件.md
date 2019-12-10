# 使用Notebook上传大文件<a name="modelarts_23_0105"></a>

在“Notebook“页面中，通过单击“Upload“按钮上传文件。当上传文件提示受限时，您可以先将大文件上传到OBS中，OBS上传文件的操作指导，请参见[上传文件](https://support.huaweicloud.com/usermanual-obs/zh-cn_topic_0045829661.html)。然后根据不同场景将大文件下载到Notebook中。

## 对于挂载EVS的Notebook实例下载文件<a name="section1272531313361"></a>

可以使用以下任一方式将大文件下载到Notebook中：

1.  使用ModelArts SDK的OBS接口[从OBS下载数据](https://support.huaweicloud.com/sdkreference-modelarts/modelarts_04_0127.html)将OBS中的文件下载到Notebook后进行操作。
2.  使用[Moxing操作OBS文件](https://github.com/huaweicloud/ModelArts-Lab/blob/master/docs/moxing_api_doc/MoXing_API_File.md)将OBS中的文件同步到Notebook后进行操作。

## 对于带OBS存储的Notebook实例下载文件<a name="section161631623112"></a>

使用[使用Sync OBS功能](使用Sync-OBS功能.md)方式将OBS中的文件同步到Notebook即可。

