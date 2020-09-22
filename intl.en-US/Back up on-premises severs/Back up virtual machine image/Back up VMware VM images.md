# Back up VMware VM images

This topic describes how to back up images of VMware virtual machines \(VMs\). HBR provides the two types of backup plans for on-premises VMware VMs: instant and scheduled. HBR supports incremental backup for scheduled backup plans. In this way, HBR maximizes the safety of your data.

## Background information

You can use the on-premises VMware VM backup service in the following regions: China \(Beijing\), China \(Shanghai\), China \(Shenzhen\), China \(Hangzhou\), China \(Qingdao\), China \(Zhangjiakou-Beijing Winter Olympics\), China \(Hohhot\), China \(Hong Kong\), Singapore \(Singapore\), US \(Silicon Valley\), Indonesia \(Jakarta\), Malaysia \(Kuala Lumpur\), Australia \(Sydney\), Germany \(Frankfurt\), and Japan \(Tokyo\). This service will be available in more regions soon.

## Add a vCenter Server

Before you back up on-premises VMware VMs, you must add a vCenter Server in the HBR console.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **On-Premises Backup** \> **VMware VM**.

3.  Click the **vCenter Servers** tab. In the upper-right corner of the vCenter Servers tab, click **Add vCenter Server**.

4.  In the Add vCenter Server pane, set the **Server IP Address**, **Username**, **Password**, and **Description** parameters. The Description parameter is optional. Then, click **Create**.

    The addition of a vCenter Server may fail if the password contains the following special characters:

    \` ^ ~ = ; ! / \( \[ \] \{ \} @ $ \\ & \# % +

    **Note:** We recommend that you create a vCenter Server account that is dedicated for backup. The password of the account must include periods \(.\) and cannot include other special characters.


## Create a backup plan

To create a backup plan, perform the following steps:

1.  On the vCenter Servers tab, find the added vCenter Server, and click **Create Backup Plan** in the Actions column.

2.  In the Configure Plan step of the Create Backup Plan wizard, set the parameters and click **Next**. The following table describes the parameters.

    ![create](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7560129951/p84624.jpg)

    |Parameter|Description|
    |---------|-----------|
    |**Plan Name**|The name of the backup plan. If you do not specify this parameter, a random name is used.|
    |**Retention Period**|The retention period of the backup data. Unit: days, weeks, months, or years.|
    |**Force Quiesced Snapshot**|    -   If you select this check box, HBR uses quiesced snapshots to migrate data. If quiesced snapshots are unavailable, the backup fails.
    -   If you clear this check box, HBR attempts to use quiesced snapshots to migrate data. If quiesced snapshots are unavailable, HBR uses common snapshots to migrate data. By default, this check box is cleared. |
    |**Use LAN-free Backup**|Specifies whether to use LAN-free backup. If you select this check box, the disk to be backed up is mounted on the HBR gateway so that data is transferred over a storage area network \(SAN\) instead of a local area network \(LAN\). If the mount fails, data is transferred over a LAN.|
    |**Backup Policy**|The policy to back up data. Valid values: **Right Now** and **On Schedule**. If you select **On Schedule**, you must set the **Start Time**, **Backup Interval**, and **Enable Incremental Backup** parameters for the scheduled backup plan.

If you enable incremental backup, you must set the **Start Time** and **Backup Interval** parameters for incremental backup.

**Note:**

    -   If Changed Block Tracking \(CBT\) is disabled for a VM, full migration is run instead of incremental migration. For more information about CBT, see [VMware documentation](https://kb.vmware.com/s/article/1020128?spm=a2c4g.11186623.2.15.1dbd3d605QVWc7).
    -   During incremental backup, data that is added or modified after the most recent full backup or incremental backup is backed up.
    -   We recommend that you perform full migration at least 1 hour after incremental backup. |

3.  In the **Select VMs** step, select the VMs whose image that you want to back up, and click Next.

4.  In the Confirm step, view and confirm the settings of the backup plan. The settings include the backup plan name, retention period, backup policy, and VMs. Then, click **Create**.

    After the backup plan is created, HBR runs backup jobs based on the backup plan. You can perform the following operations on the Backup Plans tab:

    -   To start a backup job, find the backup plan and click **Run Immediately** in the Actions column.
    -   To pause a running backup job, find the backup plan and choose **More** \> **Suspend Plan** in the Actions column. To resume a paused backup job, find the backup plan and choose **More** \> **Resume Plan** in the Actions column.
    -   To delete the backup plan, find the backup plan and choose **More** \> **Delete Plan** in the Actions column. After you delete the backup plan, HBR no longer runs backup jobs for the plan but the backup data is retained.

## \(Optional\) Designate a backup client

After a backup plan is created, backup jobs are dispatched to backup clients based on the real-time client status. The client status includes how many jobs are running on each client, whether LAN-free backup is enabled for each client, and the performance of the ESXi host of each VM.

If you need to back up a large number of VMs, you can install multiple backup clients to increase backup efficiency. The procedure to install multiple backup clients is similar to that to install a single backup client. For more information, see [Preparations](/intl.en-US/Back up on-premises severs/Back up virtual machine image/Preparations.md).

After multiple backup clients are installed, HBR dispatches backup jobs based on the client status, including the load of each backup client. You can also designate a backup client to run a backup plan.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **On-Premises Backup**. On the On-Premises Backup page, click **VMware VM**.

3.  Click the **Backup Plans** tab. On the Backup Plans tab, find the backup plan, and choose **More** \> **Designate Client** in the Actions column.

4.  In the Designate Client pane, select a backup client to run the backup plan.

5.  Click **OK**.

    You can view the backup client on which the backup job for each VM is run on the Backups tab.

    ![backup history](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7560129951/p102293.jpg)


