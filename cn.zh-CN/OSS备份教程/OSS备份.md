# OSS备份 {#concept_1664266 .concept}

您可以使用混合云备份HBR来保护阿里云对象存储OSS的数据，并可以在数据丢失或受损时及时恢复。

## 准备工作 {#section_qa6_w9c_rj5 .section}

使用混合云备份HBR备份及恢复对象存储OSS中数据时，您需要先创建标准存储类型的存储空间（Bucket），详情请参考[创建存储空间](../../../../cn.zh-CN/控制台用户指南/管理存储空间/创建存储空间.md#)。

**说明：** 目前HBR仅支持备份及恢复标准存储类型的Bucket。

## 创建备份计划 {#section_aj8_h2q_1s2 .section}

请按如下步骤创建OSS备份计划：

1.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。
2.  在左侧导航栏，选择**OSS备份**。
3.  在备份计划页签，单击右上角的**创建备份计划**。
4.  在新建备份计划弹出框，按照以下说明填写各项参数，然后单击**创建**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1319194/156594402955140_zh-CN.jpg)

    |参数|说明|
    |:-|:-|
    |备份仓库名称|为该备份仓库命名。可不填，默认名字随机分配。 您也可以选择已创建的备份仓库。

 |
    |OSS Bucket|下拉选择已创建的标准存储类型的Bucket。|
    |OSS Prefix|选择或者输入的指定的OSS Prefix。如果不选择此项，默认备份Bucket中的所有文件。|
    |备份计划名称|为该备份计划命名。可不填，默认名字随机分配。|
    |备份起始时间|选择备份开始执行的时间。时间精确到秒。|
    |备份执行间隔|选择增量备份的频率。时间单位：天、周。|
    |备份保留时间|选择保留该备份的时间。时间单位：天、周、月、年。|


备份计划创建完成后，将按照指定的备份起始时间、备份执行间隔进行OSS备份任务。您还可以在备份计划页签进行如下相关操作：

-   单击操作下的**立即执行**，开始执行备份任务。
-   单击操作下的**![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1319194/156594402955166_zh-CN.jpg)** \> **暂停计划**，暂停执行中的备份任务。如需再次启动备份任务，单击操作下的**![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1319194/156594402955166_zh-CN.jpg)** \> **继续计划**。
-   单击操作下的**![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1319194/156594402955166_zh-CN.jpg)** \> **删除计划**，删除执行中的备份任务。备份计划删除后，该备份计划不会继续执行，但仍保留已备份的数据。

## 创建恢复任务 {#section_8oi_uhf_0lj .section}

您可以将指定的备份源OSS Bucket中的备份数据恢复到源Bucket或指定的其他Bucket中。

1.  在恢复任务页签，单击**创建恢复任务**。
2.  在新建恢复任务弹出框，选择**备份源OSS Bucket**、备份时间段选择**近3个月备份**或**所有历史备份**，**选择一个可以用来恢复的备份**，单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1319194/156594402955175_zh-CN.jpg)

3.  在配置恢复规则页签，选择**OSS Bucket**、选择或输入**OSS Prefix**（OSS Prefix为可选项）：

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1319194/156594402955553_zh-CN.jpg)

    -   恢复规则选择**包含所有文件**，将恢复所选Bucket下的所有文件。
    -   恢复规则选择**包含下列文件**或**排除下列文件**，在输入文件列表框中手动填写文件列表，将按照规则恢复所选Bucket下指定的文件。
    文件列表每行填写一个路径，且每一行只能以源备份路径最后一个文件夹开头，如备份路径 C:\\Windows\\data, 要恢复data里的file.txt和test，需输入：

    ``` {#codeblock_y1h_87p_lzd}
    \data\file.txt
    \data\test
    ```

4.  单击**创建**。

    恢复任务创建后，可以在恢复任务页签的**状态**栏查看恢复任务进度。


