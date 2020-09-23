# Back up MySQL databases

This topic describes how to use Hybrid Backup Recovery \(HBR\) to back up data from on-premises MySQL databases.

## Prerequisites

[Preparations](/intl.en-US/Back up on-premises severs/Workflow-based backup/Preparations.md) are completed.

## Step 1: Create a file named workflow.env

To create a file named workflow.env, perform the following steps:

1.  Go to the installation directory of the HBR backup client and create a file named `workflow.env` in the `client` subdirectory.

    **Note:** The `workflow.env` file must be stored in the same directory as the `hybridebackup` and `ids` executable files.

2.  In the `workflow.env` file, enter the username and password of the backup source in the following format:

    ```
        USERNAME=root
        PASSWORD=****
    ```


## Step 2: Configure backup scripts

You must configure two scripts: pre-backup script and post-backup script. Perform the following steps to configure the scripts:

-   Pre-backup script
    1.  [Download the pre-backup script for MySQL]().
    2.  Edit and save the pre-backup script. The following table describes the parameters in the pre-backup script for MySQL. You can set the parameters based on your requirements.
        -   Windows

            ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/4404580061/p61140.png)

            |Parameter|Description|
            |:--------|:----------|
            |BackupDir|The local backup path of the database. You need to specify this path as the backup source.|
            |MySQLInstallDir|The installation directory of the database.|

        -   Linux

            Set `BACKUPDIR` to the local backup path of the database. You need to specify this path as the backup source.

            ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/4404580061/p61141.png)

-   Post-backup script

    [Download the post-backup script for MySQL]() and change the path in the script to the local backup path of MySQL.


## Step 3: Create a backup workflow

To create a backup workflow, perform the following steps:

1.  Log on to the HBR backup client and click **Create Backup Workflow** in the upper-right corner.

2.  On the Backup Jobs/Create Backup Workflow page, click **Pre-backup Script**.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9423580061/p61078.png)

3.  In the Script Path field of the Pre-backup Script dialog box, enter the path to the pre-backup script that you specified in [Step 2](#section_kll_y33_yfb).

    **Note:** The script path must be a maximum of 250 characters in length.

4.  Click **Preview** to confirm the content of the pre-backup script and click **OK**.

5.  On the Backup Jobs/Create Backup Workflow page, click **Running Plan**.

6.  In the Running Plan dialog box, specify the following settings and click **OK**.

    -   If you need a scheduled backup plan, click **Scheduled**. From the Backup Policy drop-down list, select a backup policy.
    -   If you need an instant backup plan, click **Instant**.
7.  On the Backup Jobs/Create Backup Workflow page, click **Backup Source**.

8.  In the Backup Source dialog box, set the following parameters and click **OK**.

    |Parameter|Description|
    |:--------|:----------|
    |Source|    -   Enter the path to a backup source. You can enter a maximum of eight paths. This means that you can back up data from eight directories at a time.
    -   The path is dedicated to workflow-based backup. The path must point to an empty directory.
    -   Universal Naming Convention \(UNC\) paths are supported.
    -   Separate multiple paths with carriage returns. |
    |Use VSS for backup \(Windows only\)|    -   If the source data changes in the backup source and you need to ensure consistency between the source data and backup data, select this option.
    -   This feature is only available for Windows hosts.
    -   If you select this option, only one backup source is supported. |

9.  Optional. On the Backup Jobs/Create Backup Workflow page, click **Network Flow Control**. In the Network Flow Control dialog box, specify a period in **Work Hours** and a maximum bandwidth in **Throttling**, and then click **Add**. Confirm the settings and click **OK**.

    **Note:** You can use the flow control feature to throttle the bandwidth that is used for data backup during peak hours to ensure business continuity. If you do not need to throttle the bandwidth, skip this step.

10. On the Backup Jobs/Create Backup Workflow page, click **Post-backup Script**. In the Script Path field of the Post-backup Script dialog box, enter the directory of the post-backup script that you configured in [Step 2](#section_kll_y33_yfb). Click **OK**.

    **Note:** The script path must be a maximum of 250 characters in length.

11. On the Backup Jobs/Create Backup Workflow page, click **Submit** to start a backup job.

    **Note:**

    -   If you need to cancel the backup job, find the running backup job on the Backup Jobs page and click **Cancel** next to the backup job.
    -   If a backup job fails, find the running job on the Backup Job page and click **Retry** next to the backup job. You can click the Download icon next to the number of errors**** to download and view the error report.

## What to do next

[Restore files](/intl.en-US/Back up on-premises severs/Workflow-based backup/Restore backups.md)

[Search backups](/intl.en-US/Back up on-premises severs/Workflow-based backup/Search backups.md)

