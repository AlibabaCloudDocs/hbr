# 备份MongoDB {#concept_hl4_fzb_wfb .concept}

本文主要介绍如何使用混合云备份服务（HBR）备份MongoDB。

## 前提条件 {#section_gq2_2k3_yfb .section}

您已经完成了[准备工作](intl.zh-CN/用户指南/基于workflow的备份/准备工作.md)。

## 步骤一 创建workflow.env文件 {#section_jfl_hgc_wfb .section}

1.  打开混合云备份客户端的安装路径。在`client`的子目录下，创建文件`workflow.env` 。

    **说明：** `workflow.env`的位置与`hybridebackup`及`ids`可执行程序级别相同。

2.  在`workflow.env`文件中输入备份源的用户名和密码。格式如以下示例。

    ```
    	USERNAME=root
    	PASSWORD=****
    ```


## 步骤二 配置备份脚本 {#section_kll_y33_yfb .section}

**备份前脚本**

1.  [下载MongoDB的备份前脚本](../../../../intl.zh-CN/HBR 隐藏/数据库备份脚本.md)。

2.  配置下载的脚本，然后保存配置好的脚本。

    以下是配置MongoDB备份前脚本的基本配置说明。请根据业务需要配置其他参数。

    -   Windows系统

        |参数|说明|
        |:-|:-|
        |BackupDir|数据库本地备份的路径，将备份源设置成该本地路径|
        |MongoDBInstallDir|数据库的安装目录|
        |DBHOST|127.0.0.1|
        |DBPORT|数据库服务端口|

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64702/154442435632662_zh-CN.png)

    -   Linux系统

        |参数|说明|
        |:-|:-|
        |BackupDir|数据库本地备份的路径，将备份源设置成该本地路径|
        |MongoDBInstallDir|数据库的安装目录|
        |DBHOST|127.0.0.1|
        |DBPORT|数据库服务端口|

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64700/154442435732647_zh-CN.png)


**备份后脚本**

[下载MongoDB的备份后脚本](../../../../intl.zh-CN/HBR 隐藏/数据库备份脚本.md)，将脚本中的路径配置成MongoDB的本地备份路径。保存脚本。

## 步骤三 创建备份工作流 {#section_tjk_bj3_yfb .section}

1.  打开混合云备份客户端，在页面右上角，单击**创建备份工作流**。

2.  在备份任务列表/创建备份工作流页面，单击**备份前脚本**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64539/154442435732506_zh-CN.png)

3.  在备份前脚本窗口，输入步骤二中配置好的备份前脚本文件路径。

    **说明：** 脚本路径最多为250个字符。

4.  单击**预览**核验脚本内容，然后单击**确定**。

5.  在备份任务列表/创建备份工作流页面，单击**备份计划**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64539/154442435732522_zh-CN.png)

6.  在弹出的窗口中，按照以下说明进行选择，然后单击**确定**。

    -   如有定期备份计划，单击**计划备份**。在备份策略下拉框，选择创建好的备份策略。
    -   如没有定期备份计划，单击**立即备份**。
7.  在备份任务列表/创建备份工作流页面，单击**备份数据源**。

8.  在备份数据源窗口按照以下说明进行配置。然后单击**确定**。

    |参数|说明|
    |:-|:-|
    |源地址|     -   输入备份源的路径，最多可以输入8个路径，即最多支持8个文件目录同时备份。
    -   该路径为workflow备份专用，您需要选择一个空文件夹。
    -   支持UNC路径。
    -   每个路径使用回车分隔。
 |
    |使用VSS（Volume Shadow\(Copy\)Service，仅限Windows系统）|     -   如果备份源中有数据更改，需要确保备份数据与源数据的一致，勾选此项。
    -   此功能仅在Windows系统中支持。
    -   勾选此项后，不支持多个备份源同时备份。
 |

9.  （可选）在备份任务列表/创建备份工作流页面，单击**网络限流**。

    **说明：** 网络限流可以帮助您在业务高峰期，控制备份的流量，以免影响正常业务。如无此需要，跳过此步骤及下一步。

10. （可选）在弹出的网络限流窗口，根据需要选择**限流时间段**以及**最大流量**，单击**添加**。确认限流信息后，单击**确定**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64539/154442435732524_zh-CN.png)

11. 在备份任务列表/创建备份工作流页面，单击**备份后脚本**。在备份后脚本窗口，输入步骤二中配置好的备份后脚本文件路径。单击**确定**。

    **说明：** 脚本路径最多为250个字符。

12. 在备份任务列表/创建备份工作流页面，单击**提交**开始备份。


**说明：** 

-   如需取消当前的备份任务，在备份列表中，找到正在进行的备份任务，单击**取消**。
-   如备份任务失败，在备份列表中，找到正在进行的备份任务，单击**重试**。您还可以单击**错误数**，下载并查看错误报告。

## 相关操作 {#section_ckm_kk3_yfb .section}

[恢复备份](intl.zh-CN/用户指南/基于workflow的备份/恢复备份.md)

[备份搜索](intl.zh-CN/用户指南/基于workflow的备份/备份搜索.md)

