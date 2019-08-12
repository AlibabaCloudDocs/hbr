# Back up NAS files {#concept_977495 .concept}

You can use HBR to back up NAS files in an ECS instance and restore the files when they are lost or damaged. This topic describes how to back up NAS files in an ECS instance.

## Prerequisites {#section_60b_01k_fr6 .section}

You have completed [preparations](intl.en-US/Back up NAS/Use an ECS file backup client to back up NFS NAS files/Preparations.md#).

## Step 1: Create an ECS file backup client {#section_wj8_7oh_c66 .section}

The procedure is as follows:

1.  At the top of the page, select the region of the ECS instance from which you need to back up data.
2.  On the ECS File Backup page, click **Add ECS Instance**.
3.  In the Add ECS Instance dialog box that appears, select an existing backup vault or click **Create Vault** to create one. Then, select the ECS instance that you created in [preparations](intl.en-US/Back up NAS/Use an ECS file backup client to back up SMB NAS files/Preparations.md#).
4.  Click **Create**. Wait for several minutes, and check that the status of the created ECS instance on the ECS Instance tab is Activated.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/776277/156473476754136_en-US.jpg)


## Step 2: Create a backup plan {#section_kmh_tmi_ee4 .section}

After creating the ECS file backup client, perform the following operations to create a backup plan:

1.  Click **Backup** next to the created ECS instance in the Actions column.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/776277/156473476854138_en-US.jpg)

2.  In the Create Backup Plan dialog box that appears, set the parameters, and then click **Create**.

    The following table describes the parameters.

    **Note:** You cannot use Volume Shadow Copy Service \(VSS\) to back up NAS files.

    |Parameter|Description|
    |---------|-----------|
    |Plan Name|The name of the backup plan. If you leave this field blank, a random name is specified by default.|
    |Source Path|The path of the mount point for the NAS file system.|
    |Start Time|The start time of the backup plan. The time is accurate to the second.|
    |Plan Interval|The frequency of incremental backups. Valid units: hour, day, and week.|
    |Retention|The retention period of the backup. Valid units: day, week, month, and year.|
    |Using Flow Control|You can enable throttling to set bandwidth limits for backing up data from a directory during peak hours. This ensures business continuity. **Note:** If you select **Use**, select a throttling period and enter the maximum bandwidth that can be used for backup in the throttling period based on business requirements, and then click **Add**.

 |


## Step 3: Run the backup job {#section_iyc_8rj_4jg .section}

After the backup plan is created, you can check it on the Backup Plan and Job tab. The NAS backup job starts based on the configured backup plan. You can also click **Execute Now** to run the backup job immediately.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/776277/156473476854140_en-US.jpg)

Then, you can check the progress of the backup job on the Backup Plan and Job tab.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/776277/156473476854142_en-US.jpg)

