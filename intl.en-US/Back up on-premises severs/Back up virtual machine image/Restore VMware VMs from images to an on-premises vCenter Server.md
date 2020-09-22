# Restore VMware VMs from images to an on-premises vCenter Server

This topic describes how to restore VMware virtual machines \(VMs\) from images to an on-premises vCenter Server in the Hybrid Backup Recovery \(HBR\) console.

VMware VM images are backed up. For more information, see [Back up a VMware virtual machine](/intl.en-US/Back up on-premises severs/Back up virtual machine image/Back up a VMware virtual machine.md).

-   You can use the on-premises VMware VM restoration service in the following regions: China \(Beijing\), China \(Shanghai\), China \(Shenzhen\), China \(Hangzhou\), China \(Zhangjiakou-Beijing Winter Olympics\), China \(Hohhot\), China \(Hong Kong\), Singapore \(Singapore\), Indonesia \(Jakarta\), Australia \(Sydney\), US \(Silicon Valley\), and Germany \(Frankfurt\). This service will be available in more regions soon.
-   After you back up the image of a VMware VM, you can use the HBR console to restore the image to an on-premises vCenter Server in the case of VMware VM failure to ensure business continuity.
-   The on-premises VMware VM backup feature of HBR 1.0.13 and later versions allow backup and restore jobs to be managed only in the HBR console. If you have configured on-premises backup plans, re-configure them in the HBR console.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **On-Premises Server Backup**. On the On-Premises Backup page, click **VMware VM**.

3.  Click the **Backups** tab.

4.  On the Backups tab, find the backup plan and click **Restore** in the **Actions** column.

    ![VMware1](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8888449951/p93020.jpg)

5.  In the **Create Restore Job** pane, set parameters in the **Select VMs**, **Select Destination**, **Select Compute Node**, **Select Storage**, and **Select Network** steps, confirm the configurations in the **Confirm Settings** step, and then click **Create**.

    ![vm3](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8888449951/p93031.png)

    After the restore job is created, you can view the information of the job on the **Restore Jobs** tab. The information includes the status of the job and the volume of data that is restored.

    ![vm5](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8888449951/p93048.png)


