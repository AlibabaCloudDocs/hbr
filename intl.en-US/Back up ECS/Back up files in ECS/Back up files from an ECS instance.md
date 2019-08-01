# Back up files from an ECS instance {#concept_fw3_zbv_fgb .concept}

You can use Hybrid Backup Recovery \(HBR\) to back up files that are located on an ECS instance. When files are missing or damaged, you can restore these files by using a backup. This topic describes how to back up files that are located on an ECS instance.

**Note:** You can only back up files from an ECS instance that is located in one of the following regions: China \(Hangzhou\), China \(Shanghai\), China \(Beijing\), and China \(Shenzhen\).

## Prerequisites {#section_vnn_bfv_fgb .section}

You have completed the [preparation](intl.en-US/Back up ECS/Back up files in ECS/Prerequisites.md).

## Back up files from a single ECS instance {#section_lp4_1dv_fgb .section}

You can use HBR to back up files from a single ECS instance. Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **ECS Backup** \> **ECS File Backup**.
3.  On the ECS File Backup page, select the **ECS Instance** tab.
4.  Locate the target ECS instance, and click **Backup** in the Actions of the instance.
5.  In the **Create Backup Plan** dialog box, configure the required settings based on the following descriptions, and click **Create**.

    |Name|Description|
    |:---|:----------|
    |Source Path|     -   The path of a backup source. You can enter a maximum of eight source paths, which means that you can back up files from eight directories at a time.
    -   A source path must be an absolute path.
    -   You can enter a Uniform Naming Convention \(UNC\) path as a source path.

**Note:** When the source path is a UNC path, Windows access control lists \(ACLs\) are not backed up.

    -   Separate source paths with carriage returns.
 |
    |Plan Name|The name of the plan. If you leave this field blank, a random name is specified by default.|
    |Retention|The retention period of a backup. Unit: day, week, month, and year.|
    |Start Time|The start time of the plan. The time is accurate to the second.|
    |Plan Interval|Specify the frequency of incremental backups. Unit: day, week, month, and year.|
    |Delete Source Files|If you need to delete source files after a backup is complete, select **Delete**.|
    |Use VSS for backup|     -   The feature is only available for instances running Windows.
    -   If you need to ensure data consistency between a backup source and its backup when data changes occur in the backup source, you can select **Use**.
    -   If you use Volume Shadow Copy \(VSS\), you cannot back up data from multiple directories at a time.
 **Note:** You cannot use VSS for backup when the backup source is on an exFAT volume.

 |
    |Using Flow Control| You can use flow control to set bandwidth limits for backing up data from a directory during peak hours. This ensures business continuity.

 If you select **Use**, you need to select a Time Range based on business requirements. Enter the maximum allowed bandwidth during the specified time range in the Max Flow field, and click **Add**.

 |


## Back up files from multiple ECS instances {#section_gdj_bdv_fgb .section}

If you need to back up files from multiple ECS instances, you can create multiple backup plans at a time. Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **ECS Backup** \> **ECS File Backup**.
3.  At the top of the page, select the region of the ECS instance from which you need to back up data.
4.  In the upper-right corner, choose **Batch Operation** \> **Batch Add Backup Plan**.
5.  In the Batch Add Backup Plan dialog box, click **Download Template**.
6.  Open the downloaded template, follow instructions to configure the template, and save the template.

    **Note:** If you do not need to back up an ECS instance, you can delete the row where the instance is located.

    |Name|Description|
    |:---|:----------|
    |Client ID|The ID of the available client you can use to back up data. We recommend that you do not change the ID.|
    |Instance ID|The ID of the ECS instance where the client is located. We recommend that you do not change the ID.|
    |Instance Name|The name of the ECS instances where the client is located. We recommend that you do not change the name.|
    |Source|The path of a directory from which you need to back up data. A path must be an absolute path.|
    |Plan Name|The name of a plan. If you leave this field blank, a random name is specified by default.|
    |Retention Day|     -   The retention period of a backup. You must enter an integer as the value.
    -   Unit: day \(by default\).
    -   If you leave this empty, the backup file is saved for 730 days by default.
 |
    |Effective Time|The start time of a backup. The format is `YYYY-MM-DD/HH:MM:SS`. For example, 2018-12-03/12:00:00.|
    |Backup Interval|     -   Enter an interval between two incremental backups. You must enter an integer as the value.
    -   Unit: hour \(by default\).
    -   If you leave this field blank, the interval is 24 hours by default.
 |
    |Use VSS for backup|     -   This feature is only available for instances running Windows.
    -   You can enable this feature when data changes occur in the backup source. The feature is designed to help ensure data consistency between a backup source and a backup.
    -   Enter Y to enable this feature and enter N to disable this feature. If you leave this field blank, the feature is disabled by default.
    -   If you use VSS, you cannot back up multiple directories at a time.
 |
    |Bandwidth Throttling|     -   Flow control. You can set bandwidth limits for backing up directories to ensure business continuity.
    -   If you enable this function, enter the maximum bandwidth that can be consumed by a backup job during a specified time range.
    -   You must enter an integer as the value. Unit: MB \(by default\).
    -   If you leave this field blank, the bandwidth is not throttled.
 |

7.  Click **Upload Template** to upload the template.
8.  Click **Create**.

## More actions {#section_ksp_w2v_fgb .section}

On the ECS File Backup page, select the **Backup Plan and Job** tab. You can perform the following actions.

|Action|Procedure|
|:-----|:--------|
|View an error report|In the Actions column, you can click View to show the progress of a backup plan. If a number of files failed to back up, you can click **View** next to a backup plan. Click the Download icon next to the number of failed files to download the **Error Report**.|
|Run a backup job|In the Actions column, click the **More** icon next to a backup plan and select **Execute Now**.|
|Cancel a running backup job|In the Actions column, click the **More** icon next to a backup plan and select **Cancel Task**.|
|Pause a running backup job|In the Actions column, click the **More** icon next to a backup plan and select **Pause**.|
|Resume a running backup job|In the Actions column, click the **More** icon next to a backup plan and click **Enable**.|
|Modify a backup plan|In the Actions column, click the **More** icon next to a backup plan and select **Edit**.|
|Delete a backup plan|In the Actions column, click the **More** icon next to a backup plan and select **Delete**. After you delete a backup plan, the backup plan is no longer running. However, data that you have already backed up by using the plan is retained.|

