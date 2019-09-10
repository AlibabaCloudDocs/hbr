# Agentless NAS backup {#task_1909859 .task}

You can use Hybrid Backup Recovery \(HBR\) to protect data in Alibaba Cloud Network Attached Storage \(NAS\) and restore data in a timely manner if data is lost or damaged.

**Note:** Alibaba Cloud NAS is referred to as NAS in this topic.

## Preparations {#section_8di_mba_sr5 .section}

Before using HBR to back up and restore data in NAS, you must create a NAS file system for backup.

**Note:** Currently, HBR only allows you to back up data in a NAS file system mounted in compliance with the Network File System \(NFS\) protocol.

## Step 1: Register a NAS instance {#section_rc9_g7v_ny8 .section}

To register a NAS instance, perform the following operations:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, click **NAS Backup**.
3.  On the NAS Instance tab, click **Register NAS Instance** in the upper-right corner.
4.  In the Register NAS Instance dialog box, specify relevant parameters.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1514021/156808434359915_en-US.jpg)

 
    -   Backup Vault Config: You can click **Select Existing Vault**. If you have not created a backup vault before, click **Create New Vault** and enter the vault name and description to create a vault. The vault name can be up to 64 characters in length.

        **Note:** Backup vaults are HBR cloud storage repositories that you can use to store backups. You can back up data from multiple ECS instances to the same vault. Backup vaults are located in different regions. You can only select or create backup vaults in the current region.

    -   Please select NAS filesystem to backup: Select the NAS file system you want to back up.
5.  Click **Create**. 

    You can create a NAS backup plan after the status of the NAS instance changes from **Attaching** to **Attached**.


## Step 2: Create a backup plan {#section_173_52r_gux .section}

**Note:** We recommend that each created NAS backup job contain no more than 50 million files, and the total number of files and subdirectories in each directory be no more than 8 million.

To create a NAS backup plan, perform the following operations:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, click **NAS Backup**.
3.  On the NAS Instance tab, click **Backup** in the Actions column for the registered NAS instance.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1514021/156808434359921_en-US.jpg)


4.  In the Create Plan dialog box that appears, specify relevant parameters, as described in the following table, and click **OK**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1514021/156808434459922_en-US.jpg)

 

    |Parameter|Description|
    |:--------|:----------|
    |Plan Name|Specify the name of the backup plan. If you do not specify this parameter, a random name is specified by default.|
    |Source File Path|Specify the storage path of the files to be backed up.|
    |Start Time|Specify the start time of the backup plan. The time is accurate to seconds.|
    |Plan Interval|Specify the frequency of incremental backups. Valid units: day and week.|
    |Retention|Specify the retention period of the backup. Valid units: day, week, month, and year.|

    After the backup plan is created, HBR backs up files on the NAS instance at the specified start time and at the specified intervals. On the Backup Plan tab, you can also perform the following operations:

    -   Start a backup job: Find the target backup plan and click **Execute Now** in the Actions column.
    -   Pause a backup job: Find the target backup plan and choose **![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1514021/156808434459926_en-US.jpg)** \> **Disable Plan** in the Actions column. To resume a paused backup job, choose **![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1514021/156808434459926_en-US.jpg)** \> **Enable Plan** in the Actions column.
    -   Delete a backup job: Find the target backup plan and choose **![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1514021/156808434459926_en-US.jpg)** \> **Delete Plan** in the Actions column. After you delete a backup plan, HBR no longer runs the plan but retains data that is backed up by using the plan.
    -   Modify a backup plan: Find the target backup plan and click **Edit** in the Actions column.
    **Note:** You can view the progress of backup jobs on the Backup Jobs tab. After the specified backup job is completed, you can restore the backup data of the specified source NAS instance to the current or another specified NAS file system.


## Step 3: Create a restoration job {#section_yl9_iwl_g8v .section}

To create a restoration job, perform the following operations:

1.  On the NAS Instance tab, click **Restore** in the Actions column for the registered NAS instance.
2.  On the **Select Source Instance** tab of the New Restore Task dialog box, set Restore Resource to **From Current NAS** or **From Other NAS**, and click **Next**.
3.  On the **Select Snapshot** tab, set Backup Time Frame to **Last 3 Months** or **All Snapshots**, select a backup source, and then click **Next**.
4.  On the **Config Restore Rules** tab, set **Restore Path** and **Restore Rule**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1514021/156808434459924_en-US.jpg)

 

    -   If you set Restore Rule to **Include All Files**, HBR restores all files on the selected source NAS instance.
    -   If you set Restore Rule to **Include Files** or **Exclude Files**, you need to enter the directories of files in the Input File List field. HBR restores files on the selected source NAS instance based on this restoration rule.
    In the Input File List field, enter one directory in each line. Ensure that each directory starts with the lowest-level folder in the source directory. For example, if the source directory is /test/data and you want to restore the file.txt and abc files in the data folder, enter the directories as follows:

    ``` {#codeblock_l2p_tjp_f6j}
    /data/file.txt
    /data/abc
    ```

5.  Click **Create**. After the restoration job is created, you can view the job progress in the **Status** column on the Restore Jobs tab.

## \(Optional\) Uninstall a NAS instance {#section_vo3_tb7_mef .section}

When a NAS instance is registered, HBR automatically creates a mount point in the NAS file system. You cannot directly delete this mount point because it is created by the internal service of Alibaba Cloud. If you need to unmount the NAS file system, uninstall the NAS instance on the NAS Instance tab in the HBR console, as shown in the following figure.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1514021/156808434459925_en-US.jpg)

**Note:** If you uninstall a NAS instance, relevant backup and restoration jobs may fail. Ensure that no backup or restoration job is in progress before you uninstall the NAS instance.

