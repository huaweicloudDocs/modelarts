# OBS目录导入数据规范说明<a name="modelarts_23_0008"></a>

导入数据集时，使用存储在OBS的数据时，数据的存储目录以及文件名称需满足ModelArts的规范要求。

当前只有“图像分类“、“物体检测“、“图像分割“、“文本分类“和“声音分类“标注类型支持按标注格式导入。

其中，“表格”类型的数据集，支持从OBS、DWS、DLI和MRS等数据源导入数据。

>![](public_sys-resources/icon-note.gif) **说明：** 
>从OBS目录导入数据时，当前操作用户需具备此OBS路径的读取权限。

## 图像分类<a name="section570816190577"></a>

图像分类的数据支持两种格式：

1）ModelArts imageNet 1.0：目录方式，只支持单标签

-   相同标签的图片放在一个目录里，并且目录名字即为标签名。当存在多层目录时，则以最后一层目录为标签名。

    示例如下所示，其中Cat和Dog分别为标签名。

    ```
    dataset-import-example 
    ├─Cat 
    │      10.jpg 
    │      11.jpg 
    │      12.jpg 
    │ 
    └─Dog 
            1.jpg 
            2.jpg 
            3.jpg
    ```

    2）ModelArts image classification 1.0：txt标签文件，支持多标签

-   当目录下存在对应的txt文件时，以txt文件内容作为图像的标签。

    示例如下所示，import-dir-1和imort-dir-2为导入子目录。

    ```
    dataset-import-example 
    ├─import-dir-1
    │      10.jpg
    │      10.txt    
    │      11.jpg 
    │      11.txt
    │      12.jpg 
    │      12.txt
    └─import-dir-2
            1.jpg 
            1.txt
            2.jpg 
            2.txt
    ```

    单标签的标签文件示例，如1.txt文件内容如下所示：

    ```
    Cat
    ```

    多标签的标签文件示例，如1.txt文件内容如下所示：

    ```
    Cat
    Dog
    ```


-   只支持JPG、JPEG、PNG、BMP格式的图片。单张图片大小不能超过5MB，且单次上传的图片总大小不能超过8MB。

## 物体检测<a name="section1371122614572"></a>

支持两种格式：

1\)ModelArts PASCAL VOC 1.0

-   物体检测的简易模式要求用户将标注对象和标注文件存储在同一目录，并且一一对应，如标注对象文件名为“IMG\_20180919\_114745.jpg“，那么标注文件的文件名应为“IMG\_20180919\_114745.xml“。

    物体检测的标注文件需要满足PASCAL VOC格式，格式详细说明请参见[表8](Manifest文件导入规范说明.md#table77167388472)。

    示例：

    ```
    ├─dataset-import-example 
    │      IMG_20180919_114732.jpg 
    │      IMG_20180919_114732.xml 
    │      IMG_20180919_114745.jpg 
    │      IMG_20180919_114745.xml 
    │      IMG_20180919_114945.jpg 
    │      IMG_20180919_114945.xml
    ```

    标注文件的示例如下所示：

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <annotation>
        <folder>NA</folder>
        <filename>bike_1_1593531469339.png</filename>
        <source>
            <database>Unknown</database>
        </source>
        <size>
            <width>554</width>
            <height>606</height>
            <depth>3</depth>
        </size>
        <segmented>0</segmented>
        <object>
            <name>Dog</name>
            <pose>Unspecified</pose>
            <truncated>0</truncated>
            <difficult>0</difficult>
            <occluded>0</occluded>
            <bndbox>
                <xmin>279</xmin>
                <ymin>52</ymin>
                <xmax>474</xmax>
                <ymax>278</ymax>
            </bndbox>
        </object>
        <object>
            <name>Cat</name>
            <pose>Unspecified</pose>
            <truncated>0</truncated>
            <difficult>0</difficult>
            <occluded>0</occluded>
            <bndbox>
                <xmin>279</xmin>
                <ymin>198</ymin>
                <xmax>456</xmax>
                <ymax>421</ymax>
            </bndbox>
        </object>
    </annotation>
    ```

-   只支持JPG、JPEG、PNG、BMP格式的图片，单张图片大小不能超过5MB，且单次上传的图片总大小不能超过8MB。

2）YOLO：

-   YOLO数据集目录应该遵循以下结构，格式不规范将导致导入任务失败。

    ```
    └─ yolo_dataset/
       │
       ├── obj.names  # 标签集文件
       ├── obj.data   # 记录数据集信息的文件及路径信息(相对路径)
       ├── train.txt  # 训练集中各图片路径信息(相对路径)
       ├── valid.txt  # 验证集中各图片路径信息(相对路径)
       │
       ├── obj_train_data/  # 训练集的图片与对应的标注文件所在目录
       │    ├── image1.txt  # image1对应的带标签bbox列表
       │    ├── image1.jpg
       │    ├── image2.txt
       │    ├── image2.jpg
       │    ├── ...
       │
       ├── obj_valid_data/  # 验证集的图片与对应的标注文件所在目录
       │    ├── image101.txt
       │    ├── image101.jpg
       │    ├── image102.txt
       │    ├── image102.jpg
       │    ├── ...
    ```

    YOLO数据集只支持train和valid子集。如果导入的数据集包括除了上述之外的子集，这些其他子集将被忽略。

-   obj.data应包含以下内容，train和valid子集必许至少有一个，其中文件路径均为相对路径。

    ```
    classes = 5 # 可选
    names = <path/to/obj.names>
    train = <path/to/train.txt>
    valid = <path/to/valid.txt>
    backup = backup/ # 可选
    ```

-   obj.names文件记录标签列表。每一行的行标作为该标签的index。

    ```
    label1  # label1的index： 0
    label2  # label2的index： 1
    label3  
    ...
    ```

-   train.txt和valid.txt文件结构如下，其中文件路径均为相对路径，且文件列表与目录下的文件需一一对应：

    ```
    <path/to/image1.jpg>
    <path/to/image2.jpg>
    ...
    ```

-   obj\_train\_data/ 和 obj\_valid\_data/目录下的.txt文件应该包含对应图像的bbox标签信息，每行代表一个bbox标注。

    ```
    # image1.txt:
    # <label_index> <x_center> <y_center> <width> <height>
    0 0.250000 0.400000 0.300000 0.400000
    3 0.600000 0.400000 0.400000 0.266667
    ```

    其中x\_center, y\_center, width, and height分别表示归一化后的目标框中心点x坐标、归一化后的目标框中心点y坐标、归一化后的目标框宽度、归一化后的目标框高度。

-   只支持JPG、JPEG、PNG、BMP格式的图片，单张图片大小不能超过5MB，且单次上传的图片总大小不能超过8MB。

## 图像分割<a name="section1363851815518"></a>

ModelArts image segmentation 1.0：

-   要求用户将标注对象和标注文件存储在同一目录，并且一一对应，如标注对象文件名为“IMG\_20180919\_114746.jpg“，那么标注文件的文件名应为“IMG\_20180919\_114746.xml“。

    图像分割的标注文件基于PASCAL VOC格式增加了字段mask\_source和mask\_color，格式详细说明请参见[表4](Manifest文件导入规范说明.md#table1516151991311)。

    示例：

    ```
    ├─dataset-import-example 
    │      IMG_20180919_114732.jpg 
    │      IMG_20180919_114732.xml 
    │      IMG_20180919_114745.jpg 
    │      IMG_20180919_114745.xml 
    │      IMG_20180919_114945.jpg 
    │      IMG_20180919_114945.xml
    ```

    标注文件的示例如下所示：

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <annotation>
        <folder>NA</folder>
        <filename>image_0006.jpg</filename>
        <source>
            <database>Unknown</database>
        </source>
        <size>
            <width>230</width>
            <height>300</height>
            <depth>3</depth>
        </size>
        <segmented>1</segmented>
        <mask_source>obs://xianao/out/dataset-8153-Jmf5ylLjRmSacj9KevS/annotation/V001/segmentationClassRaw/image_0006.png</mask_source>
        <object>
            <name>bike</name>
            <pose>Unspecified</pose>
            <truncated>0</truncated>
            <difficult>0</difficult>
            <mask_color>193,243,53</mask_color>
            <occluded>0</occluded>
            <polygon>
                <x1>71</x1>
                <y1>48</y1>
                <x2>75</x2>
                <y2>73</y2>
                <x3>49</x3>
                <y3>69</y3>
                <x4>68</x4>
                <y4>92</y4>
                <x5>90</x5>
                <y5>101</y5>
                <x6>45</x6>
                <y6>110</y6>
                <x7>71</x7>
                <y7>48</y7>
            </polygon>
        </object>
    </annotation>
    ```


## 文本分类<a name="section163641141195713"></a>

文本分类支持导入“txt“和“csv“两种文件类型，文本的编码格式支持“UTF-8“和“GBK“。

文本分类的标注对象和标注文件有2种存放模式。

-   ModelArts text classfication combine 1.0：文本和标注合并，文本分类的标注对象和标注内容在一个文本文件内，标注对象与标注内容之间，多个标注内容之间可分别指定分隔符。

    例如，文本文件的内容如下所示。标注对象与标注内容之间采用tab键分隔。

    ```
    手感很好，反应速度很快，不知道以后怎样   positive
    三个月前买了一个用的非常好果断把旧手机替换下来尤其在待机方面秒杀  positive
    没充一会电源怎么也会发热呢音量健不好用回弹不好  negative
    算是给自己的父亲节礼物吧物流很快下单不到24小时就到货了耳机更赞有些低音炮的感觉入耳很紧不会掉棒棒哒  positive
    ```

-   ModelArts text classfication 1.0：文本和标注分离，文本分类的标注对象和标注文件均为文本文件，并且以行数进行对应，如标注文件中的第一行表示的是标注对象文件中的第一行的标注。

    例如，标注对象“COMMENTS\_20180919\_114745.txt“的内容如下所示。

    ```
    手感很好，反应速度很快，不知道以后怎样
    三个月前买了一个用的非常好果断把旧手机替换下来尤其在待机方面秒杀
    没充一会电源怎么也会发热呢音量健不好用回弹不好
    算是给自己的父亲节礼物吧物流很快下单不到24小时就到货了耳机更赞有些低音炮的感觉入耳很紧不会掉棒棒哒
    ```

    标注文件“COMMENTS\_20180919\_114745\_result.txt“的内容。

    ```
    positive
    negative
    negative 
    positive
    ```

    此数据格式要求将标注对象和标注文件存储在同一目录，并且一一对应，如标注对象文件名为“COMMENTS\_20180919\_114745.txt“，那么标注文件名为“COMMENTS \_20180919\_114745\_result.txt“。

    数据文件存储示例：

    ```
    ├─dataset-import-example 
    │      COMMENTS_20180919_114732.txt 
    │      COMMENTS _20180919_114732_result.txt 
    │      COMMENTS _20180919_114745.txt 
    │      COMMENTS _20180919_114745_result.txt 
    │      COMMENTS _20180919_114945.txt 
    │      COMMENTS _20180919_114945_result.txt
    ```


## 声音分类<a name="section1683314458578"></a>

ModelArts audio classfication dir 1.0：要求用户将相同标签的声音文件放在一个目录里，并且目录名字即为标签名。

示例：

```
dataset-import-example 
├─Cat 
│      10.wav 
│      11.wav 
│      12.wav 
│ 
└─Dog 
        1.wav 
        2.wav 
        3.wav
```

## 表格<a name="section118011361754"></a>

支持从OBS导入csv文件，需要选择文件所在目录，其中csv文件的列数需要跟数据集schema一致。支持自动获取csv文件的schema。

```
├─dataset-import-example 
│      table_import_1.csv 
│      table_import_2.csv
│      table_import_3.csv
│      table_import_4.csv
```

