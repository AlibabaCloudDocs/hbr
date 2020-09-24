# Restore a VMware VM to an ECS instance

This topic describes how to restore a VMware virtual machine \(VM\) to an Elastic Compute Service \(ECS\) instance.

## Prerequisites

A VMware VM is backed up. For more information, see [Back up VMware VM images](/intl.en-US/Back up on-premises severs/Back up virtual machine image/Back up VMware VM images.md).

## Background information

To ensure service continuity and stability of a VMware VM, you can restore the VM to an on-premises vCenter Server. However, if an infrastructure error occurs, such as an ESXi host failure or a data center failure, we recommend that you use the Hybrid Backup Recovery \(HBR\) console to restore the backup VM to an ECS instance.

## Procedure

To restore a VMware VM to an ECS instance, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Disaster Recovery** \> **VMware Disaster Recovery**.

3.  On the VMware Disaster Recovery page, click the Backup History tab. On this tab, find the backup plan and click **Cloud Restore** in the Actions column.

    ![restore1](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7024190061/p132725.jpg)

4.  In the Restore to ECS pane, select a VM that you want to restore, and click **Next**.

    ![Restore2](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7024190061/p132726.jpg)

5.  In the Configure Restore Policy step, set the **VPC**, **Switch**, **Instance Type**, **Instance Family**, and other parameters. Then, click **Create**.

    ![Create](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7024190061/p140038.png)

6.  After the restore job is created, view the restoration progress on the Restore Jobs tab.

    After the status of the restore job changes to **Mounted**, click the link in the Destination column to view the information about the ECS instance to which the VMware VM is restored.

    ![restore3](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7024190061/p132727.jpg)


