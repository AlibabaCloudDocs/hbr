# 云上整机恢复VMware虚拟机

本文为您介绍如何把已备份的VMware虚拟机整机恢复到阿里云ECS上。

## 前提条件

**说明：** VMware云上整机恢复服务不支持系统盘创建在LVM（Logical Volume Manager）卷的Linux虚拟机。

已完成VMware虚拟机备份。详情请参见[备份VMware虚拟机](/intl.zh-CN/本地服务器备份教程/虚拟机备份/备份VMware虚拟机.md)。

## 背景信息

针对某台VMware虚拟机业务中断，通常仅需要通过本地恢复VMware虚拟机的方式恢复业务可用性。但如果VMware虚拟机的基础设施出现了问题，比如ESXi出现宕机，或者数据中心遭遇故障，建议您通过混合云备份管理控制台把已备份的VMware虚拟机整机恢复到阿里云ECS上，以保持业务的连续性及稳定性。

## 操作步骤

您可以按如下步骤把已备份的VMware虚拟机整机恢复到阿里云ECS：

1.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。

2.  单击**容灾** \> **VMware容灾**。

3.  在备份历史页签，找到要恢复的虚拟机备份记录，单击操作栏下的**云上恢复**。

    ![restore1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0808109951/p132725.jpg)

4.  选择一个可以用来恢复的备份，单击**下一步**。

    ![Restore2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1808109951/p132726.jpg)

5.  在创建恢复到ECS的任务页面，配置各项参数，如选择**专有网络**、**交换机**、**实例类型**、**实例规格**等，然后单击**创建**。

    ![Create](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1808109951/p140038.png)

6.  在恢复任务页签，查看恢复的进度。

    待状态显示为**完成**后，单击ECS名称链接，查看恢复出来的ECS详情。

    ![restore3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1808109951/p132727.jpg)


