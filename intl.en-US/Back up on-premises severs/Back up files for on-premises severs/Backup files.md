# Backup files {#concept_gf5_4kc_ggb .concept}

You can use a Hybrid Backup Recovery \(HBR\) backup client to back up files and folders from a local server or virtual machine. HBR supports the following backup modes: instant backup and scheduled backup. You can select the required backup mode based on business needs.

## Instant backup {#section_v3s_kwd_qfb .section}

If you have no regular backup plan and only need to perform a full backup, you can perform the following steps:

1.  Log on to an HBR client.
2.  On the Backup Jobs page, click **Create Backup Job**.
3.  In the Create Backup Job dialog box, select the **Basic Settings** tab and configure the required settings as described in the following table.

    |Name|Description|
    |:---|:----------|
    |Source|     -   The path of a backup source. You can enter a maximum of eight source paths, which means you can back up files from eight directories at a time. Separate source paths with carriage returns.
    -   You can enter a Uniform Naming Convention \(UNC\) path as a source path.
 |
    |Use VSS for backup \(Windows only\)|     -   If you need to ensure data consistency between a backup source and its backup when data changes occur in the backup source, you can select this option.
    -   The feature is only available for hosts running Windows.
    -   If you use Volume Shadow Copy \(VSS\), you cannot back up data from multiple directories at a time.
 |
    |Running Plan|Select **Instant**.|

4.  \(Optional\) Select the **Bandwidth Throttling** tab. Specify the required **Work Hours** and click **Add**. Then, enter the maximum allowed bandwidth during the specified time range in the Throttling field.

    **Note:** 

    -   The unit of the throttling period is accurate to the hour. You can add multiple throttling periods based on actual needs.
    -   If you need to modify a throttling period, click **Delete** next to the throttling period and add a new throttling period.
    -   The maximum bandwidth must be more than or equal to 1 Mbit/s.
5.  Click **Submit** to start the backup job.

**Note:** After a backup job is started, you can perform the following actions on the Backup Jobs page:

-   View the progress of the backup job.
-   In the Actions column, **cancel** or **retry** the backup job.
-   If a number of files failed to back up, locate the failed backup job on the Backup Jobs page. Click the Download icon next to the number of failed files to download the **error report**.

## Scheduled backup {#section_bnq_yzk_5fb .section}

If you have a regular backup plan, you can create a scheduled backup based on a custom backup policy. Proceed as follows:

1.  Log on to an HBR client.
2.  In the left-side navigation pane, select **Backup**.
3.  In the upper-right corner of the page, click **Create Backup Job**.
4.  In the Create Backup Job dialog box, select the **Basic Settings** tab.
5.  Enter the Source, select **Scheduled**, and select a Backup Policy.

    |Name|Description|
    |:---|:----------|
    |Source|     -   The path of a backup source. You can enter a maximum of eight source paths, which means that you can back up files from eight directories at a time. Separate source paths with carriage returns.
    -   You can enter a Uniform Naming Convention \(UNC\) path as a source path.
 |
    |Use VSS for backup \(Windows only\)|     -   If you need to ensure data consistency between a backup source and its backup when data changes occur in the backup source, you can select this option.
    -   The feature is only available for hosts running Windows.
    -   If you use Volume Shadow Copy \(VSS\), you cannot back up data from multiple directories at a time.
 |
    |Running Plan|Select **Scheduled**.|
    |Backup Policy|Select a [backup policy](intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Prerequisites.md#section_ljr_vhc_ggb) from the drop-down list.|

6.  \(Optional\) Select the **Bandwidth Throttling** tab. Specify the required **Working Hours** and click **Add**. Then, enter the maximum allowed bandwidth during the specified time range in the Throttling field.

    **Note:** 

    -   The unit of the throttling period is accurate to the hour. You can add multiple throttling periods based on actual needs.
    -   If you need to modify a throttling period, click **Delete** next to the throttling period and add a new throttling period.
    -   The maximum bandwidth must be no less than 1 Mbit/s.
7.  Click **Submit**.

**Note:** After a backup job is started, you can perform the following actions on the Backup Jobs page:

-   View the progress of the backup job
-   In the Actions column, **cancel** or **retry** the backup job.
-   In the Actions column, **delete** the backup job. After a backup job is deleted, the backup job is disabled and no backup policy applies to the backup job. However, backups that are created by the back job are retained and you can still restore data from these backups.
-   If a number of files failed to back up, locate the failed backup job on the Backup Jobs page. Click the Download icon next to the number of failed files to download the **error report**.

