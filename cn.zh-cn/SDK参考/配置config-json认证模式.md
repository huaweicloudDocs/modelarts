# 配置config.json认证模式<a name="modelarts_04_0156"></a>

本模式支持SDK所有模块的鉴权。

在用户的“home“目录下创建“.modelarts“目录，在SDK安装后的目录中，找到配置文件示例“config.json“，并拷贝至刚创建的“.modelarts“目录下。

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   在SDK安装后，“config.json“被放在“<python安装目录\>/site-packages/modelarts/config/“目录下，不同操作系统可能略有不同。  
>-   SDK会在安装用户的home目录下自动寻找“config.json“。通常Linux系统下该目录是“/home/<user\>/.modelarts/“；windows系统下该目录是“Driver:\\Users\\<user\>\\.modelarts\\“。  

打开“.modelarts“目录下的“config.json“文件，用真实的帐户名、用户名、密码替换掉account，username，password并保存。非企业用户将account删除即可。

上述内容配置后，即可进行session初始化， 无需输入认证参数。若“config.json“文件放到了其他目录下，在Session初始化时用“config\_file“参数指定即可。

## 示例代码<a name="zh-cn_topic_0173871414_section8531313012"></a>

```
from modelarts.session import Session
session = Session(config_file='/home/user/.modelarts/config.json')
```

