# Back up NAS files {#concept_978480 .concept}

You can use an HBR file backup client to back up SMB NAS files in a local IDC. The HBR file backup client supports instant file backup and scheduled file backup. You can back up files in either mode based on your business requirements.

## Instant backup {#section_u00_m5s_wlc .section}

If you do not have any backup schedules and only need to back up full data, perform the following operations:

1.  Log on to the HBR file backup client.
2.  In the left-side navigation pane, click Backup. On the Backup Jobs page, click **Create Backup Job** in the upper-right corner.
3.  In the Create Backup Job dialog box that appears, click the **Basic Settings** tab and set the following parameters:

    -   Source: Enter the path of the mount point for the NAS file system.
    -   Running Plan: Select **Instant**.
    **Note:** You cannot use Volume Shadow Copy Service \(VSS\) to back up NAS files.

4.  \(Optional\) Click the **Bandwidth Throttling** tab. Set **Work Hours** and Throttling, and then click **Add** to specify the maximum bandwidth that can be used for backup in the throttling period.

    **Note:** 

    -   The throttling period is accurate to the hour. You can add multiple throttling periods as needed.
    -   To modify a throttling period, click **Delete** next to the period in the Actions column, and set the period again.
    -   The maximum bandwidth cannot be less than 1 Mbit/s.
5.  Click **Submit**.

    **Note:** After the backup job starts, you can perform the following operations on the Backup Jobs page:

    -   View the progress of the backup job.
    -   Cancel or retry the backup job by clicking **Cancel** or **Retry** in the Actions column, respectively.
    -   If some files fail to be backed up in the job, locate the job on the Backup Jobs page. In the Errors column of the job, click the **Download** icon to download the error report.

## Scheduled backup {#section_833_0ht_vjw .section}

If you have a backup schedule, perform the following operations to create a backup policy and customize the first backup time and backup frequency:

1.  Open a browser and visit `http://localhost:8011` to log on to the HBR file backup client. On the client logon page, enter the logon password.

    **Note:** 

    -   If you back up data through an intermediate host, replace `localhost` with the IP address of the server or virtual machine where you want to back up data.
    -   You can log on to the file backup client over the default port 8011. If port 8011 on the target server or virtual machine is occupied by another application, you can [specify another port number for the file backup client](../../../../intl.en-US/FAQ/On-premises backup FAQ/How can I change the number of the logon port for a file client?.md).
2.  In the left-side navigation pane, click **Backup Policies**.
3.  On the Backup Policies page, click **Create Policy**.
4.  In the Create Policy dialog box that appears, set Name and set the other parameters as needed.

    |Parameter|Description|
    |:--------|:----------|
    |Name|The name of the policy.|
    |Frequency|Valid units:     -   Hour \(1-23\)
    -   Day \(1-6\)
    -   Week \(1-4\)
 |
    |Backup Time|The first backup time. The first backup is a full backup.|
    |Retention|     -   Valid units: day, month, and year.
    -   Maximum retention time: 3,650 days \(10 years\).
 |

5.  Click **Submit**.

After creating the scheduled backup policy, perform the following operations to start a scheduled backup job:

1.  Log on to the HBR file backup client.
2.  In the left-side navigation pane, click **Backup**.
3.  On the Backup Jobs page, click **Create Backup Job** in the upper-right corner.
4.  In the Create Backup Job dialog box that appears, click the **Basic Settings** tab. When backing up SMB NAS files in a local IDC, set the following parameters:

    -   Source: Enter the path of the mount point for the NAS file system.
    -   Running Plan: Select **Scheduled**.
    -   Backup Policy: Select the created backup policy.
    **Note:** You cannot use VSS to back up NAS files.

5.  \(Optional\) Click the **Bandwidth Throttling** tab. Set **Work Hours** and Throttling, and then click **Add** to specify the maximum bandwidth that can be used for backup in the throttling period.

    **Note:** 

    -   The throttling period is accurate to the hour. You can add multiple throttling periods as needed.
    -   To modify a throttling period, click **Delete** next to the period in the Actions column, and set the period again.
    -   The maximum bandwidth cannot be less than 1 Mbit/s.
6.  Click **Submit**.

    **Note:** After the backup job starts, you can perform the following operations on the Backup Jobs page:

    -   View the progress of the backup job.
    -   Cancel or retry the backup job by clicking **Cancel** or **Retry** in the Actions column, respectively.
    -   Delete the backup job by clicking **Delete** in the Actions column. After the backup job is deleted, data is no longer backed up based on the configured backup policy. Data that has been backed up is retained and can be restored.
    -   If some files fail to be backed up in the job, locate the job on the Backup Jobs page. In the Errors column of the job, click the **Download** icon to download the error report.

