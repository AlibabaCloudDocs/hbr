# Back up files

You can use Hybrid Backup Recovery \(HBR\) to back up files from on-premises servers or virtual machines \(VMs\) and restore the files if needed. HBR provides the two types of backup plans: instant and scheduled. This topic describes how to back up files from on-premises servers or VMs.

**Note:** An HBR backup client backs up files in a folder incrementally based on the specified backup policy. This means that the client only backs up files that have been added or modified since last backup. For example, after HBR backs up three files in a folder: File 1, File 2, and File 3. After the backup, File 2 is edited. Then, HBR backs up only File 2 during next backup.

## Create an instant backup plan

If you need only one-time full backup, perform the following steps to create an instant backup plan:

1.  Log on to an HBR backup client.

2.  In the left-side navigation pane, click Backup. In the upper-right corner of the Backup Jobs page, click **Create Backup Job**.

3.  On the **Basic Settings** tab of the Create Backup Job dialog box, set the parameters. The following table describes the parameters.

    |Parameter|Description|
    |:--------|:----------|
    |Source|The paths to the source files. Specify the paths based on the following rules:     -   If no wildcard \(\*\) is included, you can enter a maximum of eight source paths.
    -   If wildcards \(\*\) are included, you can enter only one source path. The format of the path can be /\*/\*.
    -   Only absolute paths are supported. The paths must be start with /, \\\\, C:\\, or D:\\.
**Note:**

    -   You can specify only one root path. For example, you cannot specify both C:\\ and D:\\.
    -   If VSS backup is used, you can enter only one path. Uniform Naming Convention \(UNC\) paths and wildcards \(\*\) are not supported. You cannot specify files to excluded from the backup plan.
    -   If UNC paths are used, VSS backup and wildcards \(\*\) are not supported. You cannot specify files to excluded from the backup plan. If a UNC path is specified, HBR does not back up the access control list \(ACL\) of Windows. |
    |Use VSS for backup \(Windows only\)|    -   Specifies whether to use Volume Shadow Copy Service \(VSS\) for backup. If data in the backup source changes, select this check box. VSS ensures data consistency between the source and the backup.
    -   This parameter is valid only for Windows clients.
    -   If VSS is used, you cannot back up data from multiple directories.
**Note:** This feature is unavailable if the backup source resides on a volume of the exFAT format. |
    |Backup Rule|The rule that specifies the files to be excluded from the backup plan. Select **All Files** or **Exclude Files**. If you select **Exclude Files**, specify the paths to files that you want to exclude from the backup plan.

**Note:** Specify the paths based on the following rules:

    -   You can enter a maximum of eight paths, including paths that include wildcards \(\*\).
    -   If a path does not include forward slashes \(/\), a wildcard \(\*\) in the path matches multiple directory levels. For example, the \*abc\* path matches /abc/, /d/eabcd/, and /a/abc and the \*.txt path matches all files whose extension is TXT.
    -   If a path includes forward slashes \(/\), each wildcard \(\*\) in the path matches one directory level. For example, the /a/\*/\*/share path matches the /a/b/c/share path but does not match the /a/d/share path.
    -   If a path ends with a forward slash \(/\), the path matches a directory. For example, the \*tmp/ path matches the /a/b/aaatmp/ directory and the /tmp/ directory.
    -   The path separator in Linux is the forward slash \(/\). The path separator in Windows is the backslash \(\\\). |
    |Running Plan|The type of the backup plan. Select **Instant**.|

4.  Optional. Click the **Bandwidth Throttling** tab. Set **Work Hours**. In the Throttling field, enter the maximum bandwidth that can be used for backup during the specified throttling period. Then, click Add.

    **Note:**

    -   The throttling period is accurate to the hour. You can add multiple throttling periods based on your requirements.
    -   If you need to modify a throttling period, find the throttling period, click **Delete** in the Actions column, and then add a throttling period.
    -   The maximum bandwidth must be at least 1 MB/s.
5.  Click **Submit**.

    After a backup job is started, you can perform the following operations on the Backup Jobs page:

    -   View the progress of the backup job.
    -   Click **Cancel** or **Retry** in the Actions column to cancel or retry the backup job.
    -   If the backup of some files fail, click the Download icon in the Errors column to download the error report.

## Create a scheduled backup plan

If you need scheduled backup, perform the following steps to create a scheduled backup plan:

1.  Log on to an HBR backup client.

2.  In the left-side navigation pane, click **Backup**.

3.  In the upper-right corner of the Backup Jobs page, click **Create Backup** Job.

4.  In the Create Backup Job dialog box, click the **Basic Settings** tab.

5.  Specify the paths to the source files, select **Scheduled** as Running Plan, and then select an existing backup policy as **Backup Policy**.

    |Parameter|Description|
    |:--------|:----------|
    |Source|The paths to the source files. Specify the paths based on the following rules:     -   If no wildcard \(\*\) is included, you can enter a maximum of eight source paths.
    -   If wildcards \(\*\) are included, you can enter only one source path. The format of the path can be /\*/\*.
    -   Only absolute paths are supported. The paths must be start with /, \\\\, C:\\, or D:\\.
**Note:**

    -   If VSS backup is used, you can enter only one path. UNC paths and wildcards \(\*\) are not supported. You cannot specify files to excluded from the backup plan.
    -   If UNC paths are used, VSS backup and wildcards \(\*\) are not supported. You cannot specify files to excluded from the backup plan. If a UNC path is specified, HBR does not back up the access control list \(ACL\) of Windows. |
    |Use VSS for backup \(Windows only\)|    -   Specifies whether to use Volume Shadow Copy Service \(VSS\) for backup. If data in the backup source changes, select this check box. VSS ensures data consistency between the source and the backup.
    -   This parameter is valid only for Windows clients.
    -   If VSS is used, you cannot back up data from multiple directories. |
    |Backup Rule|The rule that specifies the files to be excluded from the backup plan. Select **All Files** or **Exclude Files**. If you select **Exclude Files**, specify the paths to files that you want to exclude from the backup plan.

**Note:** Specify the paths based on the following rules:

    -   You can enter a maximum of eight paths, including paths that include wildcards \(\*\).
    -   If a path does not include forward slashes \(/\), a wildcard \(\*\) in the path matches multiple directory levels. For example, the \*abc\* path matches /abc/, /d/eabcd/, and /a/abc and the \*.txt path matches all files whose extension is TXT.
    -   If a path includes forward slashes \(/\), each wildcard \(\*\) in the path matches one directory level. For example, the /a/\*/\*/share path matches the /a/b/c/share path but does not match the /a/d/share path.
    -   If a path ends with a forward slash \(/\), the path matches a directory. For example, the \*tmp/ path matches the /a/b/aaatmp/ directory and the /tmp/ directory.
    -   The path separator in Linux is the forward slash \(/\). The path separator in Windows is the backslash \(\\\). |
    |Running Plan|The type of the backup plan. Select **Scheduled**.|
    |Backup Policy|The backup policy. Select an existing [backup policy](/intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Preparations.md) from the drop-down list.|

6.  Optional. Click the **Bandwidth Throttling** tab. Set **Work Hours**. In the Throttling field, enter the maximum bandwidth that can be used for backup during the specified throttling period. Then, click Add.

    **Note:**

    -   The throttling period is accurate to the hour. You can add multiple throttling periods based on your requirements.
    -   If you need to modify a throttling period, find the throttling period, click **Delete** in the Actions column, and then add a throttling period.
    -   The maximum bandwidth must be at least 1 MB/s.
7.  Click **Submit**.

    After a backup job is started, you can perform the following operations on the Backup Jobs page:

    -   View the progress of the backup job.
    -   Click **Cancel** or **Retry** in the Actions column to cancel or retry the backup job.
    -   Click **Delete** in the Actions column to delete the backup job. After you delete the backup job, HBR no longer runs the backup job based on the specified backup policy. However, HBR retains the backup data of the backup job. You can still restore data from the backup data.
    -   If the backup of some files fail, click the Download icon in the Errors column to download the error report.

## Query files to be backed up

In the HBR console, you can query the list of files to be backed up in each backup plan.

1.  On the File tab of the On-Premises Backup page, find the backup client, and click **Browse** in the Actions column.

2.  On the page that appears, click **Browse** in the Actions column that corresponds to a source path.

    In the Browse dialog box, view all files in the source path.

    **Note:** In this dialog box, you can only query the files in the source path but cannot restore the files. For more information, see [Restore files](/intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Restore files.md).


## FAQ

If file backup fails due to an unstable network connection, you can perform the following operations and try again:

1.  Log on to the ECS instance from which files need to be backed up.
2.  Go to the installation directory of the HBR backup client.
3.  In the `client` folder, create a file named `hbr.config`.

    **Note:** The `hbr.config` file must be in the same directory as the `hybridebackup` and `ids` executable files.

4.  Add the following parameters to the `hbr.config` file.

    |Parameter|Description|
    |---------|-----------|
    |retry\_times|The number of file backup retries. Default value: 3.|
    |retry\_interval|The interval at which file backup is retried. Default value: 100 ms.|
    |skip\_error\_files|Specifies whether to skip files that fail to be backed up. Default value: false.     -   false: does not skip the failed files.
    -   true: skips the failed files. |


The following script shows example configurations of the parameters in the hbr.config file.

```
retry_times=3
retry_interval=100
skip_error_files=false
```

