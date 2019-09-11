# Back up OSS {#concept_1664266 .task}

You can use Hybrid Backup Recovery \(HBR\) to back up Object Storage Service \(OSS\) objects and restore the objects when they are lost or damaged.

## Preparations {#section_qa6_w9c_rj5 .section}

OSS stores objects in buckets. Before using HBR to back up and restore OSS objects, you must create a bucket whose storage class is Standard. For more information about how to create a bucket, see [Create a bucket](../../../../intl.en-US/Console User Guide/Manage buckets/Create a bucket.md#).

**Note:** Currently, HBR allows you to back up and restore OSS objects only in Standard buckets.

## Step 1: Create a backup plan {#section_aj8_h2q_1s2 .section}

To create an OSS backup plan, perform the following operations:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, click **OSS Backup**.
3.  On the Backup Plan tab, click **Create Backup Plan** in the upper-right corner.
4.  In the Create Plan dialog box, set relevant parameters, as described in the following table, and then click **OK**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1319194/156819264460312_en-US.jpg)

 

    |Parameter|Description|
    |:--------|:----------|
    |Backup Vault Name|Set the name of the backup vault. If you do not specify this parameter, a random name is specified. You can also select an existing backup vault.

 |
    |OSS Bucket|Select an existing Standard bucket from the drop-down list.|
    |OSS Prefix|Select an OSS prefix from the drop-down list, or specify an OSS prefix. If you do not specify this parameter, HBR backs up all objects in the bucket.|
    |Plan Name|Set the name of the backup plan. If you do not specify this parameter, a random name is specified.|
    |Start Time|Set the start time of the backup plan. The time is accurate to seconds.|
    |Plan Interval|Set the frequency of incremental backups. Valid units: day and week.|
    |Retention|Set the retention period of the backup. Valid units: day, week, month, and year.|

    After the backup plan is created, HBR backs up OSS objects at the specified start time and at the specified intervals. On the Backup Plan tab, you can also perform the following operations:

    -   Start a backup job: Find the target backup plan and click **Execute Now** in the Actions column.
    -   Pause a backup job: Find the target backup plan and choose **![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1319194/156819264460316_en-US.jpg)** \> **Disable Plan** in the Actions column. To resume a paused backup job, choose **![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1319194/156819264460316_en-US.jpg)** \> **Enable Plan** in the Actions column.
    -   Delete a backup job: Find the target backup plan and choose **![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1319194/156819264460316_en-US.jpg)** \> **Delete Plan** in the Actions column. After you delete a backup plan, HBR no longer runs the plan but retains data that is backed up by using the plan.

## Step 2: Create a restoration job {#section_8oi_uhf_0lj .section}

You can restore the backup data of an OSS bucket to the original OSS bucket or another OSS bucket.

1.  On the Restore Jobs tab, click **Create Restore Job** in the upper-right corner.
2.  In the New Restore Task dialog box, select the source OSS bucket for **Source OSS Bucket**, set Backup Time Frame to **Last 3 Months** or **All Snapshots**, select a **Backup Source**, and then click **Next**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1319194/156819264460317_en-US.jpg)


3.  On the Config Restore Rules tab, select the destination OSS bucket for **OSS Bucket**, and select or enter an OSS prefix in the **OSS Prefix** field. The OSS prefix is optional.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1319194/156819264560320_en-US.jpg)

 

    -   If you set Restore Rule to **Include All Files**, HBR restores all objects in the destination OSS bucket.
    -   If you set Restore Rule to **Include Files** or **Exclude Files**, you need to enter object paths in the Input File List field. HBR restores objects in the destination OSS bucket based on this restoration rule.
    In the Input File List field, enter an object path in each line. Ensure that each path starts with the OSS prefix that you specified in the relevant backup plan. The following example shows how to enter object paths:

    -   If the specified OSS prefix is a/b/ and you want to include or exclude folder and file.txt, enter object paths as follows:

        ``` {#codeblock_36c_zhw_n9m}
        a/b/folder
        a/b/file.txt
        ```

    -   If no OSS prefix is specified and you want to include or exclude folder and file.txt, enter object paths as follows:

        ``` {#codeblock_sba_vze_8dg}
        folder
        file.txt
        ```

4.  Click **Create**. After the restoration job is created, you can view the job progress in the **Status** column on the Restore Jobs tab.

