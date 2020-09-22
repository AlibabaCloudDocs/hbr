# Back up files from ECS instances

You can use Hybrid Backup Recovery \(HBR\) to back up files from Elastic Compute Service \(ECS\) and restore the files if needed. This topic describes how to back up files from ECS instances.

## Prerequisites

[Preparations](/intl.en-US/Back up ECS/ECS file backup/Preparations.md) are completed.

## Back up files from an ECS instance

To back up files from an ECS instance, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS File Backup**.

3.  On the ECS File Backup page, click the **ECS Instances** tab.

4.  On the ECS Instances tab, find the ECS instance and click **Back Up** in the Actions column.

5.  In the **Create Backup Plan** pane, set the parameters and click **OK**. The following table describes the parameters.

    |Parameter|Description|
    |:--------|:----------|
    |Plan Name|The name of the backup plan. By default, a random name is used.|
    |Source Paths|The paths to the source files. Specify the paths based on the following rules:     -   If no wildcard \(\*\) is included, you can enter a maximum of eight source paths.
    -   If wildcards \(\*\) are included, you can enter only one source path. The format of the path can be /\*/\*.
    -   Only absolute paths are supported. The paths must be start with /, \\\\, C:\\, or D:\\.
**Note:**

    -   You can specify only one root path. For example, you cannot specify both C:\\ and D:\\.
    -   If VSS backup is used, you can enter only one path. Uniform Naming Convention \(UNC\) paths and wildcards \(\*\) are not supported. You cannot specify the files to be excluded from the backup plan.
    -   If UNC paths are used, VSS backup and wildcards \(\*\) are not supported. You cannot specify the files to be excluded from the backup plan. If a UNC path is specified, HBR does not back up the access control list \(ACL\) of Windows. |
    |Backup Rule|The rule that specifies the files to be excluded from the backup plan. Select **Include All Files** or **Exclude Specified Files**. If you select **Exclude Specified Files**, specify the paths to files that you want to exclude from the backup plan.

**Note:** Specify the paths based on the following rules:

    -   You can enter a maximum of eight paths, including paths that include wildcards \(\*\).
    -   If a path does not include forward slashes \(/\), a wildcard \(\*\) in the path matches multiple directory levels. For example, the \*abc\* path matches /abc/, /d/eabcd/, and /a/abc and the \*.txt path matches all files whose extension is TXT.
    -   If a path includes forward slashes \(/\), each wildcard \(\*\) in the path matches one directory level. For example, the /a/\*/\*/share path matches the /a/b/c/share path but does not match the /a/d/share path.
    -   If a path ends with a forward slash \(/\), the path matches a directory. For example, the \*tmp/ path matches the /a/b/aaatmp/ directory and the /tmp/ directory.
    -   The path separator in Linux is the forward slash \(/\). The path separator in Windows is the backslash \(\\\). |
    |Start Time|The start time of the backup plan. The time is accurate to seconds.|
    |Backup Interval|The interval at which data backup is performed. Unit: hours, days, or weeks. **Note:** The maximum interval is 52 weeks \(1 year\). |
    |Retention Period|The retention period of the backup data. Unit: days, weeks, months, or years.|
    |Use VSS|    -   Specifies whether to use Volume Shadow Copy Service \(VSS\) for backup. This parameter is valid only for Windows ECS instances.
    -   If data in the backup source changes, select **Yes**. VSS ensures data consistency between the source and the backup.
    -   If VSS is used, you cannot back up data from multiple directories.
**Note:** This feature is unavailable if the backup source resides on a volume of the exFAT format. |
    |Throttle Bandwidth|Specifies whether to throttle the bandwidth. You can throttle the bandwidth that is used for data backup during peak hours. This guarantees business continuity.

If you select **Yes**, you must set the Throttling Period \(Hour\) and Max Bandwidth parameters. Then, click **Add**. |


## Back up files from multiple ECS instances

You can create multiple backup plans back up files from multiple ECS instances. To create multiple backup plans in a batch, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS File Backup**.

3.  In the top navigation bar, select the region where the ECS instances reside.

4.  In the upper-right corner, choose **Batch Actions** \> **Create Backup Plans**.

5.  In the Create Backup Plans pane, click **Download Template**.

6.  Open the template, set the parameters, and then save the template. The following table describes the parameters.

    **Note:** If you do not need to back up files from an ECS instance, delete the row that corresponds to the ECS instance from the template.

    |Parameter|Description|
    |:--------|:----------|
    |Client Id|The ID of the backup client. Do not change the client ID.|
    |Instance Id|The ID of the ECS instance where the backup client is installed. Do not change the instance ID.|
    |Instance Name|The name of the ECS instance where the backup client is installed. Do not change the instance name.|
    |Source|The path to the directory from which you want to back up files. The path must be an absolute path.|
    |Plan Name|The name of the backup plan. If you do not specify this parameter, a random name is used.|
    |Retention \(Day\)|    -   The retention period of backup data. Enter an integer.
    -   Unit: days.
    -   If you do not specify this parameter, the backup data is retained for 730 days. |
    |Effective Time|The start time of the backup plan. Specify the time in the `YYYY-MM-DD/HH:MM:SS` format, for example, 2018-12-03/12:00:00.|
    |Backup Interval|    -   The interval at which incremental backup is performed. Enter an integer.
    -   Unit: hours.
    -   If you do not specify this parameter, the interval is 24 hours. |
    |Use VSS for backup|    -   This feature is only available for Windows ECS instances.
    -   If data in the backup source changes, enable this feature. VSS ensures data consistency between the source and the backup.
    -   Enter Y to enable this feature or N to disable this feature. If you do not specify this parameter, the feature is disabled.
    -   If you use VSS, you cannot back up data from multiple directories. |
    |Bandwidth Throttling|    -   Specifies whether to throttle the bandwidth. You can throttle the bandwidth that is used for data backup. This guarantees business continuity.
    -   If you enable this feature, specify the maximum bandwidth that can be used for backup. The maximum bandwidth applies all day.
    -   Enter an integer. Unit: MB/s.
    -   If you do not specify this parameter, the bandwidth is not throttled. |

7.  Click **Upload Template** to upload the template.

8.  Click **OK**.


## Query files that are backed up

In the HBR console, you can query the list of files that are backed up in each backup plan.

1.  On the Backup Plans and Jobs tab, find the backup plan, and click **View** in the Actions column.

2.  On the page that appears, click **Browse** in the Actions column that corresponds to a source path.

    In the Browse dialog box, view all files in the source path.

    **Note:** In this dialog box, you can only query the files in the source path but cannot restore the files. For more information, see [Restore files to an ECS instance](/intl.en-US/Back up ECS/ECS file backup/Restore files to an ECS instance.md).


## What to do next

On the ECS File Backup page, click the **Backup Plans and Jobs** tab. On this tab, you can perform the following operations on a backup plan.

|Operation|Procedure|
|:--------|:--------|
|View an error report|Find the backup plan and view the backup progress in the Status column. If the backup of some files fail, click **View** in the Actions column. In the Errors column, click the **Download** icon to download the error report.|
|Start a backup job|Find the backup plan, and choose **More** \> **Run Immediately** in the Actions column.|
|Cancel a running backup job|Find the backup plan, and choose **More** \> **Cancel Job** in the Actions column.|
|Pause a running backup job|Find the backup plan, and choose **More** \> **Suspend** in the Actions column.|
|Resume a paused backup job|Find the backup plan, and choose **More** \> **Resume** in the Actions column.|
|Modify a backup plan|Find the backup plan, and choose **More** \> **Modify** in the Actions column.|
|Delete a backup plan|Find the backup plan, and choose **More** \> **Delete** in the Actions column. After you delete the backup plan, HBR no longer runs backup jobs for the plan but the backup data is retained.|

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

