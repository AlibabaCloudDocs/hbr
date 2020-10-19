# Clientless NAS backup

This topic describes how to use Hybrid Backup Recovery \(HBR\) to back up files in Apsara File Storage NAS. You can then restore the files at the earliest opportunity if they are lost or damaged.

## Prerequisites

An NFS or SMB file system is created.

For more information about how to create an NFS or SMB file system, see [Manage file systems]().

## Background information

Before you use HBR to back up files from Apsara File Storage NAS, note the following items:

-   Unless otherwise specified, NAS in this topic refers to Apsara File Storage NAS.
-   Clientless NAS backup allows you to back up Network File System \(NFS\) and Server Message Block \(SMB\) file shares no matter whether the file system is mounted. HBR uses an efficient backup mechanism that scans files in NAS file systems, instead of creating snapshots for NAS file systems.
-   In addition to the native backup service, you can also use a backup client for files to back up files in NAS file systems. For more information, see [Overview](/intl.en-US/Back up NAS/Use file backup/Back up NFS NAS using ECS file backup/Overview.md).

## Back up files within a region

**Note:** We recommend that each created NAS backup job contains no more than 50 million files and the total number of files and subfolders in each folder is no more than 8 million.

To back up files in a NAS file system to a backup vault in the same region as the file system, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **NAS Backup**.

3.  In the upper-right corner, click **Create Backup Plan**.

4.  In the Create Backup Plan panel, set the parameters and click **OK**.

    **Note:** You can enjoy the free trial of each backup plan for 60 days, starting from the day when the backup plan is created.

    ![nas1](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9932549951/p92980.jpg)

    1.  Set the basic parameters as described in the following table.

        |Parameter|Description|
        |---------|-----------|
        |File System|The source NAS file system whose files you want to back up.|
        |Plan Name|The name of the backup plan. By default, a random name is used.|
        |Start Time|The start time of the backup plan. The time is accurate to seconds.|
        |Pay After Trial Ends|Specifies whether to pay for the backup plan after its free trial ends.|

    2.  The following table describes the advanced settings of the backup plan. If you want to specify the advanced settings, click Show Advanced Settings and click **Switch to Paid Plan**.

        |Condition|Description|
        |---------|-----------|
        |Source Paths|The path to the folder that you want to back up, for example, /nas/folder. If you want to back up the root folder, enter a forward slash \(/\).|
        |Backup Interval|The interval at which the backup is performed. Unit: days or weeks.|
        |Retention Policy|The retention policy for the backup data. You can select **Limited** or **Permanent**. If you select **Limited**, you must set the **Retention Period** parameter. |
        |Retention Period|The retention period of the backup data. Unit: days, weeks, months, and years.|
        |Backup Vault|The backup vault where you want to store the backup data. You can select or create only a backup vault in the current region. If you select **Select Vault**, select a backup vault from the Vault Name drop-down list. If no backup vault is available, select **Create Vault** and specify the Vault Name field. The vault name must be 1 to 64 characters in length. **Note:** A backup vault is a repository where HBR stores backup data in the cloud. You can back up files from multiple NAS file systems to the same vault. Backup vaults reside in different regions. You can select or create backup vaults only in the current region. |

        After the backup plan is created, HBR backs up files in the source NAS file system at the specified intervals, starting from the specified start time. On the Backup Plans tab, you can perform the following operations:

        -   To start a backup job, find the backup plan and click **Run Now** in the Actions column.
        -   To pause a running backup job, find the backup plan and choose **More** \> **Suspend Plan** in the Actions column. To resume a paused backup job, find the backup plan and choose **More** \> **Resume Plan** in the Actions column.
        -   To delete the backup plan, find the backup plan and choose **More** \> **Delete Plan** in the Actions column. After you delete the backup plan, HBR no longer runs backup jobs for the plan but the backup data is retained.
        -   To view the backups of a file system that are created in the most recent three months or view all backups, find the backup plan and choose **More** \> **Backups** in the Actions column.
        -   To modify a backup plan, find the backup plan and click **Modify** in the Actions column.
        **Note:** You can view the progress of backup jobs on the Backup Jobs tab. After a backup job is completed, you can restore the backup data of the source NAS file system to the same or another NAS file system.


## Restore files within a region

To restore backup data from a backup vault to a NAS file system in the same region as the vault, perform the following steps:

1.  In the upper-right corner of the **Restore Jobs** tab, click **Create Restore Job**.

2.  In the Create Restore Job panel, set the parameters in the **Select Backup** step and click **Next**. The following table describes the parameters.

    |Parameter|Description|
    |---------|-----------|
    |Source Vault|The backup vault where the backup data that you want to restore is stored.|
    |Source File System|The source NAS file system. Select a NAS file system that has been backed up by using HBR.|
    |Select a backup to restore|The backup to restore. Select **Recent 3 Months** or **All** to filter backups.|

3.  In the **Select Backup Files** step, set the **Restore Policy** parameter and click **Next**.

    The following restore policies are supported:

    -   **Include All Files**: HBR restores all objects that are backed up from the source OSS bucket.
    -   **Include Files** or **Exclude Files**: In the text box, enter the paths to the folders and files that you want to restore. HBR restores files that are backed up from the source OSS bucket based on the restore policy.
    In the text box, enter one path in each line and start each path with the source folder. For example, if the source path is /test/data and you want to restore the file.txt file and the abc folder, enter the following paths:

    ```
    /data/file.txt
    /data/abc
    ```

4.  In the **Configure Destination** step, select a file system from the **File System** drop-down list and enter the path to the destination folder in the **Destination Path** field.

    **Note:** For example, you can enter /nas/abc if you want to restore files to the /nas/abc folder. If you want to restore files to the root folder, enter a forward slash \(/\).

5.  Click **Create**.

    After the restore job is created, you can view the job progress in the **Status** column on the Restore Jobs tab.


## Back up files across regions

A backup vault is a repository where HBR stores backup data in the cloud. To implement disaster recovery, you can create a remote mirror vault for a backup vault and back up data in the backup vault to the mirror vault.

To back up data to a mirror vault, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  Click **Overview** in the left-side navigation pane. On the Overview page, select a region, for example, China \(Hangzhou\), in the **Regions** section. Find the backup vault for which you want to create a mirror vault and click the ![+](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8437029951/p85985.jpg) icon in the upper-right corner of the backup vault.

    ![add](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8437029951/p85986.jpg)

3.  In the Create Mirror Vault panel, select the **Region** where the mirror vault resides, enter the **Vault Name**, and then click Create.

    **Note:**

    -   You can create only one mirror vault for each backup vault.
    -   You can back up data to a remote mirror vault and restore backup data from the mirror vault. However, you cannot create backup plans for the mirror vault. HBR starts to synchronize historical data in a source backup vault to the mirror vault 90 minutes after the mirror vault is created.
    -   A mirror vault contains all the backup data that is stored in the source backup vault when the mirror vault is created.
    ![mirror](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8437029951/p85997.jpg)

    You can view the data synchronization progress after you create a mirror vault. When the progress reaches 100%, it indicates that all data in the source backup vault is synchronized to the mirror vault.

    ![progress](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8437029951/p86044.jpg)


## Restore files across regions

A backup vault is a repository where HBR stores backup data in the cloud. To implement disaster recovery, you can perform the following steps to restore data in a mirror vault to a NAS file system:

1.  On the **NAS Backup** page, select the region where the mirror vault resides.

2.  Click the **Restore Jobs** tab. In the upper-right corner of the Restore Jobs tab, click **Create Restore Job**.

3.  In the **Select Backup** step, set the parameters as prompted.

    ![COPY](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8437029951/p86047.jpg)

    **Note:** Select the mirror vault from the **Source Vault** drop-down list. The name of a mirror vault is prefixed with \[COPY\]. For information about how to set other parameters, see [Restore files within a region](#section_yl9_iwl_g8v).


## Optional operations

In the upper-right corner of the NAS Backup page, click **Manage Mounts**. In the Manage Mounts panel, you can perform the following operations:

-   View all the file systems for which you have created backup plans in the selected region. You can click a file system to view the information about the NAS file system. The information includes the protocol type and the number of mount targets.
-   Unmount a file system. After you create a backup plan for a NAS file system, HBR automatically creates a mount target for the file system. You cannot delete the mount target in the NAS console. If you want to delete the mount target, find the file system in the Manage Mounts panel and click **Unmount** in the Actions column. After the mount target is deleted, backup jobs of the file system fail. Before you delete the mount target, ensure that no backup or restore jobs of the file system are running.

