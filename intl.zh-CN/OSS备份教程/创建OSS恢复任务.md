# 创建OSS恢复任务

当OSS发生系统故障或者错误操作时，您可以通过OSS恢复任务恢复OSS至对应版本。本文介绍创建OSS恢复任务的操作方法。

已创建OSS备份计划并完成备份。具体操作，请参见[创建OSS备份计划](/intl.zh-CN/OSS备份教程/OSS备份.md)和[使用OSS清单创建大数据量OSS备份计划](/intl.zh-CN/OSS备份教程/使用OSS清单创建大数据量OSS备份计划.md)。

## 操作步骤

您可以将指定的备份源OSS Bucket中的备份数据恢复到源Bucket或指定的其他Bucket中。

1.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。。

2.  在左侧导航栏，选择**备份** \> **OSS备份**。

3.  在顶部菜单栏，选择OSS所在的地域。

4.  在恢复任务页签，右上角单击**创建恢复任务**。

5.  在创建恢复任务面板，选择**备份库**和**已备份的Bucket**，并选择一个可以用来恢复的备份，单击**下一步**。

    ![OSS-创建恢复任务](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9774555261/p291798.png)

6.  在选择恢复文件页签，配置**恢复规则**，单击**下一步**。

    ![恢复规则](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4201129951/p59956.jpg)

    -   **包含所有文件**：将恢复所选Bucket下的所有文件。
    -   **包含下列文件**或**排除下列文件**，在输入文件列表框中手动填写文件列表，将按照规则恢复所选Bucket下指定的文件。

        文件列表每行填写一个路径，且每一行只能以备份时指定的prefix开头。

        -   备份时prefix指定a/b/，要包含（或排除）folder和file.txt，需输入：

            ```
            a/b/folder
            a/b/file.txt
            ```

        -   备份时不指定prefix，要包含（或排除）folder和file.txt，需输入：

            ```
            folder
            file.txt
            ```

7.  在配置恢复目的页签，从**恢复到OSS Bucket**下拉框选择恢复到的指定OSS Bucket，从**恢复到Bucket Prefix**中选择恢复到某个prefix，如果不指定prefix则表示恢复到Bucket根目录。

    ![task](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4201129951/p77332.jpg)

8.  单击**创建**。

    恢复任务创建后，可以在恢复任务页签的**状态**栏查看恢复任务进度。


