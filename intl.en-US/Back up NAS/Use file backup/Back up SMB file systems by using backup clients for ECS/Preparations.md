# Preparations

You can use Hybrid Backup Recovery \(HBR\) to back up files from Server Message Block \(SMB\) file systems of Apsara File Storage NAS. You can then restore the files if needed. This topic describes the preparations that you must make before backup.

## Step 1: Authorize roles

Before using HBR to back up files from ECS instances, you must authorize the AliyunHBRDefaultRole and AliyunECSAccessingHBRRole roles to access your cloud resources. Follow these steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS File Backup**.

3.  In the authorization dialog boxes that appear one by one, authorize the two roles to access your cloud resources as prompted.


## Step 2: Install and configure Cloud Assistant

A backup client for ECS requires interaction with Cloud Assistant. By default, Cloud Assistant is installed on ECS instances that are created after December 1, 2017. However, you must [manually install Cloud Assistant](/intl.en-US/Deployment & Maintenance/Cloud assistant/Configure the Cloud Assistant client/Install the Cloud Assistant client.md) on ECS instances that are created before December 1, 2017.

## Step 3: Create a mount target

Log on to the [NAS console](https://nas.console.aliyun.com) and create a VPC mount target for the SMB file system that you want to back up. For more information, see [Create a mount target]().

After the mount target is created, you can perform the following steps to view the path to the mount target: Find the SMB file system in the NAS console, and click **Management** in the Operations column. In the left-side navigation pane of the page that appears, click Mounting Use. You can view the path on the Mount Target page.

![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0631549951/p50654.png)

## Step 4: Create an ECS instance

Create an ECS instance in the VPC where the mount target of the SMB file system resides. For more information, see [Create an instance by using the provided wizard](/intl.en-US/Instance/Create an instance/Create an instance by using the provided wizard.md).

**Note:** We recommend that you create an ECS instance that runs Windows 2012. If the created ECS instance runs Windows 2016, you must use HBR as the administrator due to permission control of the operating system.

![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8649370061/p50677.png)

