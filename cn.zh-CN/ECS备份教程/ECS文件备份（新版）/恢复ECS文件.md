# 恢复ECS文件

您可以将备份的文件恢复到同地域的原ECS实例中，或者将同仓库中其他ECS实例或本地备份客户端备份的文件恢复到当前ECS实例。

## 前提条件

已完成ECS文件备份。详情请参见[备份ECS文件](/cn.zh-CN/ECS备份教程/ECS文件备份（新版）/备份ECS文件.md)。

## 新建恢复任务

1.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。

2.  在左侧导航栏，选择**备份** \> **ECS文件备份** \> **新版**。

3.  在**备份计划**页签下，单击任意已完成的备份计划左侧的![+](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2303552061/p172225.jpg)图标。

    ![1](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2303552061/p172251.jpg)

4.  单击可用的历史备份点，选择**恢复**。

    您还可以选择**浏览**，查看要恢复的客户端下的所有文件。

    ![2](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9544794061/p172253.jpg)

5.  在**选择目的实例**页签，选中要恢复的客户端，然后单击**下一步**。

6.  在**配置恢复规则**页签，填写**恢复路径**，选择**恢复规则**。

    恢复规则包含以下三项：

    -   **包含所有文件**：将恢复源客户端中的所有文件。
    -   **包含下列文件**或**排除下列文件**：在输入文件列表框中手动填写文件列表，将按照规则恢复所选源客户端下指定的文件。

        文件列表每行填写一个路径，且每一行只能以源备份路径最后一个文件夹开头，如备份路径folder/test/data，要恢复data里的file.txt和abc.png，请按如下格式填写路径。

        ```
        /data/file.txt
        /data/abc.png
        ```

7.  单击**开始恢复**。

    恢复任务创建后，可以在恢复任务页签的**状态**栏查看恢复任务进度。


