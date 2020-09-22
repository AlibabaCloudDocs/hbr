# Back up shares of a gateway

You can use Hybrid Backup Recovery \(HBR\) to back up shares of Cloud Storage Gateway \(CSG\). You can then restore the shares if they are lost or damaged. This topic describes how to back up shares of a gateway.

## Prerequisites

[Preparations](/intl.en-US/Back up CSG/Preparations.md) are completed.

## Procedure

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  Select the region where the gateway resides.

3.  In the left-side navigation pane, choose **Backup** \> **CSG Backup**.

4.  On the Storage Gateways tab, find the gateway, and click **Back Up** in the Actions column.

5.  In the Select Source step, select the share that you want to back up. Click **Next**.

6.  In the Configure Plan step, set the parameters and click **OK**. The following table describes the parameters.

    |Parameter|Description|
    |---------|-----------|
    |Source Paths|    -   The paths to the source files. Enter a maximum of eight paths.
    -   Each source path must be an absolute path.
    -   Uniform Naming Convention \(UNC\) paths are supported.
    -   Separate each path with a carriage return. |
    |Plan Name|The name of the backup plan. By default, a random name is used.|
    |Retention Period|The retention period of the backup data. Unit: days, weeks, months, or years.|
    |Start Time|The start time of the backup plan. The time is accurate to seconds.|
    |Backup Interval|The interval at which data backup is performed. Unit: hours, days, or weeks.|
    |Throttle Bandwidth|Specifies whether to throttle the bandwidth. You can throttle the bandwidth that is used for data backup during peak hours. This guarantees business continuity. If you select **Yes**, you must set the Throttling Period \(Hour\) and Max Bandwidth parameters. Then, click **Add**.|


## Query files that are backed up

In the HBR console, you can query the list of files that are backed up in each backup plan.

1.  On the Backup Plans and Jobs tab, find the backup plan, and click **View** in the Actions column.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7367449951/p66188.jpg)

2.  On the page that appears, click **Browser** in the Actions column that corresponds to a source path.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7367449951/p66189.jpg)

    In the Browse dialog box, view all files in the source path.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7367449951/p66190.jpg)

    **Note:** In this dialog box, you can only query the files in the source path but cannot restore the files. For more information, see [Restore shares of a gateway](/intl.en-US/Back up CSG/Restore shares of a gateway.md).


## What to do next

On the Backup Plans and Jobs page, you can perform the following operations on a backup plan.

|Operation|Procedure|
|---------|---------|
|View an error report|Find the backup plan and view the backup progress in the Status column. If the backup of some files fail, click **View** in the Actions column. In the Errors column, click the **Download** icon to download the error report.|
|Start a backup job|Find the backup plan, and choose **More** \> **Run Immediately** in the **Actions** column.|
|Cancel a running backup job|Find the backup plan, and choose **More** \> **Cancel Job** in the **Actions** column.|
|Pause a running backup job|Find the backup plan, and choose **More** \> **Suspend** in the **Actions** column.|
|Resume a paused backup job|Find the backup plan, and choose **More** \> **Resume** in the **Actions** column.|
|Modify a backup plan|Find the backup plan, and choose **More** \> **Modify** in the **Actions** column.|
|Delete a backup plan|Find the backup plan, and choose **More** \> **Delete** in the **Actions** column. **Note:** After you delete the backup plan, HBR no longer runs backup jobs for the plan but the backup data is retained. |

