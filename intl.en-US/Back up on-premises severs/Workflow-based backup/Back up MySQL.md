# Back up MySQL {#concept_hl4_fzb_wfb .concept}

This topic describes how to use Hybrid Backup Recovery \(HBR\) to back up data from on-premises MySQL.

## Prerequisites {#section_gq2_2k3_yfb .section}

You have completed the [preparations](intl.en-US/Back up on-premises severs/Workflow-based backup/Prerequisites.md).

## Step 1: Create a file named workflow.env {#section_jfl_hgc_wfb .section}

1.  Go to the installation directory of the HBR backup client and create a file named `workflow.env` in the `client` subdirectory.

    **Note:** The `workflow.env` file must be stored in the same directory as the `hybridebackup` and `ids` executable files.

2.  In the `workflow.env` file, enter the username and password of a backup source in the following format:

    ``` {#codeblock_vds_ok4_zv1}
        USERNAME=root
        PASSWORD=****
    ```


## Step 2: Configure backup scripts {#section_kll_y33_yfb .section}

 **Pre-backup script** 

1.  [Download the pre-backup script for MySQL](../../../../intl.en-US/HBR hidden/Database backup scripts.md).
2.  Configure and save the pre-backup script. The following section describes the parameters that need to be configured in the pre-backup script for MySQL. You can configure these parameters as required.
    -   Windows

        |Parameter|Description|
        |:--------|:----------|
        |BackupDir|The local backup path of the database. You need to specify this path as the backup source.|
        |MySQLInstallDir|The installation directory of the database.|

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64607/156576316155447_en-US.png)

    -   Linux

        `BACKUPDIR`: the local backup path of the database. You need to specify this path as the backup source.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64607/156576316255448_en-US.png)


 **Post-backup script** 

[Download the post-backup script for MySQL](../../../../intl.en-US/HBR hidden/Database backup scripts.md) and change the path in the script to the local backup path of MySQL. Save the script.

## Step 3: Create a backup workflow {#section_tjk_bj3_yfb .section}

1.  Log on to the HBR backup client and click **Create Backup Workflow** in the upper-right corner.
2.  On the Backup Jobs/Create Backup Workflow page, click **Pre-backup Script**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64539/156576316255446_en-US.png)

3.  In the Script Path field of the Pre-backup Script dialog box, enter the file path of the pre-backup script configured in [Step 2](#section_kll_y33_yfb).

    **Note:** The script path must be a maximum of 250 characters in length.

4.  Click **Preview** to check the details of the pre-backup script and click **OK**.
5.  On the Backup Jobs/Create Backup Workflow page, click **Running Plan**.
6.  In the Running Plan dialog box, configure the following settings and click **OK**.
    -   If you have a regular backup plan, click **Scheduled**. In the Backup Policy drop-down list, select a backup policy.
    -   If you have no regular backup plan, click **Instant**.
7.  On the Backup Jobs/Create Backup Workflow page, click **Backup Source**.
8.  In the Backup Source dialog box, configure the following settings. Then, click **OK**.

    |Parameter|Description|
    |:--------|:----------|
    |Source|     -   Enter the path of a backup source. You can enter a maximum of eight paths, which means that you can back up data from eight directories at a time.
    -   The path is dedicated to storing workflow-based backups. The path must be directed to an empty directory.
    -   You can enter a Universal Naming Convention \(UNC\) path as a source path.
    -   Separate multiple paths with carriage returns.
 |
    |Use VSS for backup \(Windows only\)|     -   If data changes occur in the backup source, select this option to ensure consistency between source data and backup data.
    -   This feature is only available for hosts running Windows.
    -   If you select this option, you cannot back up data from multiple backup sources.
 |

9.  \(Optional\) On the Backup Jobs/Create Backup Workflow page, click **Network Flow Control**. In the Network Flow Control dialog box, set a period in **Work Hours** and a maximum bandwidth in **Throttling**, and then click **Add**. Confirm the configuration and click **OK**.

    **Note:** You can use throttling to set bandwidth limits for backing up data during peak hours to ensure business continuity. If you do not need to configure throttling, you can skip this step.

10. On the Backup Jobs/Create Backup Workflow page, click **Post-backup Script**. In the Script Path field of the Post-backup Script dialog box, enter the directory of the post-backup script configured in [Step 2](#section_kll_y33_yfb). Click **OK**.

    **Note:** The script path must be a maximum of 250 characters in length.

11. On the Backup Jobs/Create Backup Workflow page, click **Submit** to start a backup job.

**Note:** 

-   If you need to cancel a backup job, locate the running backup job on the Backup Jobs page and click **Cancel** next to the backup job.
-   If a backup job fails, you can locate the running job on the Backup Job page and click **Retry** next to the backup job. You can also click the Download icon next to the **number of errors** to download and view the error report.

## More actions {#section_ckm_kk3_yfb .section}

[Restore backups](intl.en-US/Back up on-premises severs/Workflow-based backup/Restore backups.md)

[Search backups](intl.en-US/Back up on-premises severs/Workflow-based backup/Search backups.md)

