# NAS backup

This topic describes how to use Hybrid Backup Recovery \(HBR\) to back up files from Apsara File Storage NAS.

## Prerequisites

An NFS or SMB file system is created.

For more information about how to create an NFS or SMB file system, see [Manage file systems]().

## Background information

Before you use HBR to back up files from NAS, we recommend that you take note of the following information:

-   Unless otherwise specified, NAS in this topic refers to Apsara File Storage NAS.
-   NAS backup allows you to back up Network File System \(NFS\) and Server Message Block \(SMB\) file shares without the need to mount the file system. HBR uses an efficient backup mechanism. It is used to scan the files in NAS file systems. In this case, you do not need to create snapshots of the file system.

You can also use a backup client to back up files in NAS file systems. For more information, see [Overview](/intl.en-US/Back up NAS/Use file backup/Back up NFS NAS using ECS file backup/Overview.md).

## Back up files within a region

**Note:** We recommend that you limit the number of files to 50 million files for each NAS backup job, and 8 million files and subfolders for each folder.

You can back up files in a NAS file system to a backup vault in the same region as the file system. Perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **NAS Backup**.

3.  Click **Get Started**.

4.  In the Create Backup Plan panel, set the parameters and click **OK**.

    **Note:** You can use a backup plan for 30 days free of charge. It starts from the date when you create the backup plan.

    ![nas1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6572779161/p270308.png)

    1.  The following table describes the parameters.

        |Parameters|Description|
        |----------|-----------|
        |File System|The source NAS file system whose files you want to back up.|
        |Plan Name|The name of the backup plan. If you do not specify this parameter, a random name is generated and assigned to the backup plan.|
        |Start Time|The time when the backup plan starts. The time is accurate to seconds.|
        |Pay After Trial Ends|Specifies whether to pay for the backup plan after its free trial ends.|

    2.  The following table describes the advanced settings of the backup plan. If you want to specify the advanced settings, click Show Advanced Settings and click **Switch to Paid Plan**.

        |Parameters|Description|
        |----------|-----------|
        |Source Paths|The path to the folder that you want to back up, for example, /nas/folder. If you want to back up the root folder, enter a forward slash \(/\).|
        |Backup Interval|The interval at which the incremental backup is performed. Unit: days or weeks.|
        |Retention Policy|The retention policy of the backup data. Valid values: **Limited** and **Permanent**. If you select **Limited**, you must set the **Retention Period** parameter. Unit: days, weeks, months, or years. |
        |Retention Period|The retention period of backup data. Unit: days, weeks, months, or years.|
        |Backup Vault|The backup vault where you want to store the backup data. If you select **Select Vault**, select a backup vault from the Vault Name drop-down list. If no backup vault is available, select **Create Vault** and specify the Vault Name field. The vault name must be 1 to 64 characters in length. **Note:** A backup vault is a repository where HBR stores data in the cloud. You can back up files from multiple NAS file systems to the same vault. Backup vaults reside in different regions. You can select or create backup vaults only in the current region. |

        After the backup plan is created, HBR backs up files in the source NAS file system from the specified start time at the specified interval. On the Backup Plans tab, you can perform the following operations:

        -   To start a backup job, find the backup plan and click **Run Now** in the Actions column.
        -   To suspend a running backup job, find the backup plan and choose **More** \> **Suspend Plan** in the Actions column. To resume a suspended backup job, find the backup plan and choose **More** \> **Resume Plan** in the Actions column.
        -   To delete a backup plan, find the backup plan and choose **More** \> **Delete Plan** in the Actions column. After you delete the backup plan, HBR no longer runs backup jobs for the plan. However, the backup data is retained.
        -   To view all backups of a file system or the backups created in the most recent three months, find the backup plan and choose **More** \> **Backups** in the Actions column.
        -   To modify a backup plan, find the backup plan and click **Modify** in the Actions column.
        **Note:** You can view the progress of backup jobs on the Backup Jobs tab. After a backup job is complete, you can restore the backup data of the source NAS file system to the same or another NAS file system.


## Restore files within a region

You can restore backup data from a backup vault to a NAS file system in the same region as the vault. Perform the following steps:

1.  In the upper-right corner of the **Restore Jobs** tab, click **Create Restore Job**.

2.  In the Create Restore Job panel, set the parameters in the **Select Backup** step and click **Next**. The following table describes the parameters.

    |Parameters|Description|
    |----------|-----------|
    |Source Vault|The backup vault where the backup data that you want to restore is stored.|
    |Source File System|The source NAS file system. Select a NAS file system that has been backed up by using HBR.|
    |Select a backup to restore|The backup to restore. Select **Recent 3 Months** or **All** to filter backups.|

3.  In the **Select Restore Items** step, set the **Restore Items** parameter and click **Next**.

    Valid values of the Restore Policy parameter:

    -   **Include All Files**: HBR restores all objects that are backed up from the source OSS bucket.
    -   **Include Files** or **Exclude Files**: In the text box, enter the paths to the folders and files that you want to restore. HBR restores files that are backed up from the source OSS bucket based on the restore policy.
    In the Input File List field, enter a path in each line. Make sure that each patch starts with the lowest-level folder in the source backup path. For example, if the source backup path is /test/data and you want to restore the file.txt and abc folder in the data folder, enter the following paths:

    ```
    /data/file.txt
    /data/abc
    ```

4.  In the **Restore Destination** step, select a destination NAS file system in the current region and set **Destination Path**.

    **Note:** For example, you can enter /nas/abc if you want to restore files to the /nas/abc folder. If you want to restore files to the root folder, enter a forward slash \(/\).

5.  Click **Create**.

    After the restore job is created, you can view the job progress in the **Status** column on the Restore Jobs tab.


## Back up files across regions

A backup vault is a repository where HBR stores backup data in the cloud. To implement disaster recovery, you can create a remote mirror vault for a backup vault and back up data from the same backup vault to the mirror vault.

To back up data to a mirror vault, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Overview**. On the Overview page, select a region, for example, China \(Hangzhou\), in the **Regions with Backup Vault** section. Find the backup vault for which you want to create a mirror vault and click the **Cross-Region Backup** in the upper-right corner of the backup vault section.

    ![crossregion](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6572779161/p270322.png)

3.  In the Create Mirror Vault pane, select the region where the mirror vault resides, enter the name and description of the mirror vault, and then click **Create**.

    **Note:**

    -   You can create only one mirror vault for each backup vault.
    -   You can back up data to a remote mirror vault and restore backup data from the same mirror vault. However, you cannot create backup plans for this mirror vault. HBR starts to synchronize historical data from a source backup vault to the mirror vault. This applies 90 minutes after the mirror vault is created.
    -   A mirror vault contains all the backup data that is stored in the source backup vault when the mirror vault is created.
    ![mirror](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8437029951/p85997.jpg)

    After you create a mirror vault, you can view the progress of synchronized data. After the data is synchronized, you can restore the data in a NAS file system from the mirror vault.


## Restore files across regions

A backup vault is a repository where HBR stores backup data in the cloud. To implement disaster recovery, you can restore data from a remote mirror vault to a NAS file system. Perform the following steps:

1.  On the **NAS Backup** page, select the region where the mirror vault resides.

2.  Click the **Restore Jobs** tab. In the upper-right corner of the Restore Jobs tab, click **Create Restore Job**.

3.  In the **Select Backup** step, set the parameters as required.

    **Note:** You must select the mirror vault from the **Source Vault** drop-down list. The name of a mirror vault is prefixed by \[COPY\]. For information about how to set other parameters, see [Restore files within a region](#section_yl9_iwl_g8v).


## Optional operations

In the upper-right corner of the NAS Backup page, click **Manage Mounts**. In the Manage Mounts panel, you can perform the following operations:

-   View all the file systems for which you have created backup plans in the selected region. You can click a file system to view the information of the NAS file system. The information includes the protocol type and the number of mount targets.
-   **Unmount a file system**. After you create a backup plan for a NAS file system, HBR creates a mount target for the file system. You cannot directly delete the mount target in the NAS console because it is created by using an internal service of Alibaba Cloud. If you want to delete the mount target, find the file system in the Manage Mounts panel and click **Unmount** in the Actions column. After the mount target is deleted, backup jobs of the file system fail. Before you delete the mount target, make sure that no backup jobs or restore jobs of the file system are running.

