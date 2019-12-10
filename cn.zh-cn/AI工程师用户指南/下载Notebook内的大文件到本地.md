# 下载Notebook内的大文件到本地<a name="modelarts_23_0190"></a>

Notebook内只允许下载100MB以内的文件到本地。您可以根据创建Notebook时选择存储位置的不同，分场景进行操作。

## 挂载EVS的Notebook实例<a name="section1272531313361"></a>

对于挂载EVS的Notebook实例，您可以执行以下操作将大文件下载到本地：

1.  在“Jupyter Notebook“页面右上角，单击“New“，新建一个“ipynb“文件，使用[MoXing](https://github.com/huaweicloud/ModelArts-Lab/blob/master/docs/moxing_api_doc/MoXing_API_File.md)先将大文件从Notebook上传到OBS中，示例代码如下：

    ```
    import moxing as mox
    mox.file.copy('/home/ma-user/work/obs_file.txt', 'obs://bucket_name/obs_file.txt')
    ```

    其中“/home/ma-user/work/obs\_file.txt“为文件在Notebook中的存储路径，“obs://bucket\_name/obs\_file.txt“为该文件上传到OBS的存储路径。

2.  使用OBS Browser或ModelArts SDK将OBS中的文件下载到本地。
    -   方式一：使用OBS Browser进行下载

        使用OBS Browser下载文件的操作指导：[下载文件](https://support.huaweicloud.com/clientogw-obs/obs_03_0025.html)，可以将样例中的“obs\_file.txt“下载到本地。

    -   方式二：使用ModelArts SDK进行下载
        1.  在您的本地环境[下载并安装ModelArts SDK](https://support.huaweicloud.com/sdkreference-modelarts/modelarts_04_0004.html)。
        2.  完成ModelArts SDK的[Session鉴权](https://support.huaweicloud.com/sdkreference-modelarts/modelarts_04_0123.html)。
        3.  将OBS中的文件下载到本地，详请参见[从OBS下载数据](https://support.huaweicloud.com/sdkreference-modelarts/modelarts_04_0127.html)。示例代码如下：

            ```
            from modelarts.session import Session
            session=Session(access_key='***',secret_key='***',project_id='***',region_name='***')
            session.download_data(bucket_path="/bucket_name/obs_file.txt",path="/home/user/obs_file.txt")
            ```




## 带OBS存储的Notebook实例<a name="section161631623112"></a>

对于使用OBS存储的Notebook实例，您可以使用OBS Browser或ModelArts SDK将OBS中的文件下载到本地。

-   方式一：使用OBS Browser进行下载

    使用OBS Browser下载文件的操作指导：[下载文件](https://support.huaweicloud.com/clientogw-obs/obs_03_0025.html)，可以将OBS中的文件下载到本地。

-   方式二：使用ModelArts SDK进行下载
    1.  在您的本地环境[下载并安装ModelArts SDK](https://support.huaweicloud.com/sdkreference-modelarts/modelarts_04_0004.html)。
    2.  完成ModelArts SDK的[Session鉴权](https://support.huaweicloud.com/sdkreference-modelarts/modelarts_04_0123.html)。
    3.  将OBS中的文件下载到本地，详请参见[从OBS下载数据](https://support.huaweicloud.com/sdkreference-modelarts/modelarts_04_0127.html)。示例代码如下：

        ```
        from modelarts.session import Session
        session=Session(access_key='***',secret_key='***',project_id='***',region_name='***')
        session.download_data(bucket_path="/bucket_name/obs_file.txt",path="/home/user/obs_file.txt")
        ```



