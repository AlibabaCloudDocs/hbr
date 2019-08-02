# Back up a CSG instance {#task_473650 .task}

You can use HBR to back up CSG instances. When any file gateway is lost or damaged, you can restore it by using a backup. This topic describes how to back up a CSG instance.

## Prerequisites {#section_ylm_r2l_3hf .section}

You have completed [preparations](intl.en-US/Back up CSG/Preparations.md#).

## Procedure {#section_693_0rn_a5l .section}

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  Select the region of the CSG instance to be backed up.
3.  In the left-side navigation pane, click **Storage Gateway Backup**.
4.  On the Storage Gateway Backup page, click the Cloud Gateway Instance tab.
5.  Locate the target CSG instance and click **Backup** in the Actions column.
6.  In the Select Backup Source step in the Create Backup Plan wizard, select the shared data source of the CSG instance to be backed up. Click **Next**.
7.  In the Config Backup Plan step, set the parameters as instructed in the following table, and then click **Create**.

    |Parameter|Description|
    |---------|-----------|
    |Source Path|     -   The path of the backup source. You can enter a maximum of eight source paths, which means that you can back up files from eight directories at a time.
    -   The source path must be an absolute path.
    -   You can enter a Uniform Naming Convention \(UNC\) path as a source path.
    -   Separate multiple source paths with carriage returns.
 |
    |Plan Name|The name of the backup plan. If you leave this field blank, a random name is specified by default.|
    |Retention|The retention period of the backup. Valid units: day, week, month, and year.|
    |Start Time|The start time of the backup plan. The time is accurate to the second.|
    |Plan Interval|The frequency of incremental backups. Valid units: hour, day, and week.|
    |Using Flow Control|You can enable throttling to set bandwidth limits for backing up data from a directory during peak hours. This ensures business continuity. If you select **Use**, select a throttling period and enter the maximum bandwidth that can be used for backup in the throttling period based on business requirements, and then click **Add**.|


## Related operations {#section_upp_p1t_qj1 .section}

On the Storage Gateway Backup page, click the Backup Plan and Job tab, where you can perform the operations as described in the following table.

|Operation|Procedure|
|---------|---------|
|To view an error report|Locate the target backup plan and view the backup progress in the Status column. If some files fail to be backed up, click **View** next to the backup plan in the Actions column. Then, click the Download icon in Errors column to download the **error report**.|
|To start a backup job|In the **Actions** column of the target backup plan, choose **More** \> **Execute Now**.|
|To cancel a running backup job|In the **Actions** column of the target backup plan, choose **More** \> **Cancel Task**.|
|To pause a running backup job|In the **Actions** column of the target backup plan, choose **More** \> **Pause**.|
|To resume a paused backup job|In the **Actions** column of the target backup plan, choose **More** \> **Enable**.|
|To modify a backup plan|In the **Actions** column of the target backup plan, choose **More** \> **Edit**.|
|To delete a backup plan|In the **Actions** column of the target backup plan, choose **More** \> **Delete**. **Note:** After you delete a backup plan, it no longer runs. However, data that you have backed up by using the plan is retained.

 |

