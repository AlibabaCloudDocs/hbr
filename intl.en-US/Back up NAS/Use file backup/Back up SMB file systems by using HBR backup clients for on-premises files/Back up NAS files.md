# Back up NAS files

You can use an HBR backup client for files to back up files from user-created Server Message Block \(SMB\) file systems. HBR provides the two types of backup plans: instant and scheduled. This topic describes how to back up files from user-created SMB file systems.

## Create an instant backup plan

If you need only one-time full backup, perform the following steps to create an instant backup plan:

1.  Log on to an HBR backup client.

2.  In the left-side navigation pane, click Backup. In the upper-right corner of the Backup Jobs page, click **Create Backup Job**.

3.  On the **Basic Settings** tab of the Create Backup Job dialog box, set the parameters. The following table describes the parameters.

    -   Source: Enter the path to the mount target of the NAS file system.
    -   Running Plan: Select **Instant**.
    **Note:** Volume Shadow Copy Service \(VSS\) is not supported for NAS backup.

4.  Optional. Click the **Bandwidth Throttling** tab. Set **Work Hours**. In the Throttling field, enter the maximum bandwidth that can be used for backup during the specified throttling period. Then, click **Add**.

    **Note:**

    -   The throttling period is accurate to the hour. You can add multiple throttling periods based on your requirements.
    -   If you need to modify a throttling period, find the throttling period, click **Delete** in the Actions column, and then add a throttling period.
    -   The maximum bandwidth must be at least 1 MB/s.
5.  Click **Submit**.

    **Note:** After a backup job is started, you can perform the following operations on the Backup Jobs page:

    -   View the progress of the backup job.
    -   Click **Cancel** or **Retry** in the Actions column to cancel or retry the backup job.
    -   If the backup of some files fail, click the **Download** icon in the Errors column to download the error report.

## Create a scheduled backup plan

If you need scheduled backup, perform the following steps to create a scheduled backup plan:

1.  Open a browser and enter `http://localhost:8011` in the address bar. On the page that appears, enter the password to log on to the HBR backup client for files.

    **Note:**

    -   If you are using an intermediate host, replace `localhost` with the IP address of the NAS client host.
    -   Port 8011 is the default port that you can use for logon to a backup client for files. If port 8011 on the host of the backup client is occupied by another application, you can [specify another port number for the backup client](/intl.en-US/FAQ/On-premises backup FAQ/How can I change the number of the logon port for a file client?.md).
2.  In the left-side navigation pane, click **Backup Policies**.

3.  In the upper-right corner of the Backup Polices page, click **Create Policy**.

4.  In the Create Policy dialog box, set the Name and other parameters.

    |Parameter|Description|
    |:--------|:----------|
    |Name|The name of the backup policy.|
    |Frequency|The interval at which backup is performed. Units:     -   Hours. Valid values: 1 to 23.
    -   Days. Valid values: 1 to 6.
    -   Weeks. Valid values: 1 to 4. |
    |Backup Time|The time to start the first backup. The first backup is a full backup.|
    |Retention|    -   The retention period of backup data. Units: days, months, or years.
    -   Maximum retention period: 3650 days \(10 years\). |

5.  Click **Submit**.

    After the scheduled backup policy is created, perform the following steps to start a scheduled backup job:

    1.  Log on to the HBR backup client for files.
    2.  In the left-side navigation pane, click **Backup**.
    3.  In the upper-right corner of the Backup Jobs page, click **Create Backup Job**.
    4.  In the Create Backup Job dialog box, click the **Basic Settings** tab. If you are creating a backup job for a user-created NFS file system, set the following parameters:

        -   Source: Enter the path to the mount target of the NAS file system.
        -   Running Plan: Select **Scheduled**.
        -   Backup Policy: Select the created backup policy.
        **Note:** VSS is not supported for NAS backup.

    5.  Optional. Click the **Bandwidth Throttling** tab. Set **Work Hours**. In the Throttling field, enter the maximum bandwidth that can be used for backup during the specified throttling period. Then, click **Add**.

        **Note:**

        -   The throttling period is accurate to the hour. You can add multiple throttling periods based on your requirements.
        -   If you need to modify a throttling period, find the throttling period, click **Delete** in the Actions column, and then add a throttling period.
        -   The maximum bandwidth must be at least 1 MB/s.
    6.  Click **Submit**.

        **Note:** After a backup job is started, you can perform the following operations on the Backup Jobs page:

        -   View the progress of the backup job.
        -   Click **Cancel** or **Retry** in the Actions column to cancel or retry the backup job.
        -   Click **Delete** in the Actions column to delete the backup job. After you delete the backup job, HBR no longer runs the backup job based on the specified backup policy. However, HBR retains the backups that are created by the backup job. You can still restore data from these backups.
        -   If the backup of some files fail, click the **Download** icon in the Errors column to download the error report.

