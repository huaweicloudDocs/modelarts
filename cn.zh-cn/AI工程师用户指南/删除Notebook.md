# 删除Notebook<a name="modelarts_23_0042"></a>

针对不再使用的Notebook，您可以删除Notebook以释放资源。

1.  登录ModelArts管理控制台，在左侧菜单栏中选择“开发环境\>Notebook“，进入“Notebook“管理页面。
2.  在Notebook列表中，单击操作列的删除，在弹出的确认对话框中，确认信息无误，然后单击确定完成删除操作。

    只有处于“停止“或“错误“状态的Notebook才可以执行删除操作。如果Notebook处于运行中，请先执行停止Notebook操作。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >Notebook删除后不可恢复，请谨慎操作。但是Notebook中创建的文件仍然存储在创建Notebook时指定的OBS中。如果Notebook使用EVS存储，那么删除后，数据也将一并删除，请谨慎操作。  


