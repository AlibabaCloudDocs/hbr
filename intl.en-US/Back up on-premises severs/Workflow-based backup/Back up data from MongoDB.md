# Back up data from MongoDB {#concept_hl4_fzb_wfb .concept}

This topic describes how to use Hybrid Backup Recovery \(HBR\) to back up data from on-premises MongoDB.

## Prerequisites {#section_gq2_2k3_yfb .section}

You have completed the [preparation](intl.en-US/Back up on-premises severs/Workflow-based backup/Prerequisites.md).

## Step 1: Create a file named workflow.env {#section_jfl_hgc_wfb .section}

1.  Open the installation folder of an HBR backup client, create a file named `workflow.env` in the `client` subfolder.

    **Note:** The folder where the `workflow.env` file is located must be the same as that of the `hybridebackup` and `ids` executable files.

2.  In the `workflow.env` file, enter the username and password of a backup source. This format is as follows:

    ``` {#codeblock_8rf_e9n_u3q}
        USERNAME=root
        PASSWORD=****
    ```


## Step 2: Create a backup script {#section_kll_y33_yfb .section}

 **Pre-backup scripts** 

1.  [Download the pre-backup script of MongoDB](../../../../intl.en-US/HBR hidden/Database backup scripts.md).
2.  Configure and save the pre-backup script. The parameters and the description of each parameter that you can configure for the pre-backup script of MongoDB are listed in the following table. You can configure these parameters as required.
    -   Windows

        |Name|Description|
        |:---|:----------|
        |BackupDir|The local directory for the database. You need to specify the directory as the backup source.|
        |MongoDBInstallDir|The installation directory of the database.|
        |DBHOST|127.0.0.1|
        |DBPORT|The port that is used to access the database.|

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64702/156576323155462_en-US.png)

    -   Linux

        |Name|Description|
        |:---|:----------|
        |BackupDir|The local directory for the database. You need to specify the directory as the backup source.|
        |MongoDBInstallDir|The installation directory of the database.|
        |DBHOST|127.0.0.1|
        |DBPORT|The port that is used to access the database.|

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64702/156576323155463_en-US.png)


 **Post-backup scripts** 

[Download the post-backup script of MongoDB](../../../../intl.en-US/HBR hidden/Database backup scripts.md) and specify the local backup directory of MongoDB as the value of the BACKUPDIR parameter of the post-backup script. Save the script.

## Step 3: Create a backup workflow {#section_tjk_bj3_yfb .section}

1.  Log on to a backup client, click **Create Backup Workflow** in the upper-right corner.
2.  On the Backup Jobs/Create Backup Workflow page, click **Pre-backup Script**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64702/156576323155464_en-US.png)

3.  In the Script Path field of the Pre-backup Script dialog box, enter the directory of the pre-backup script configured in [Step 2](#section_kll_y33_yfb).

    **Note:** The script path must be a maximum of 250 characters in length.

4.  Click **Preview** to check the details of the pre-backup script and click **OK**.
5.  On the Backup Jobs/Create Backup Workflow page, click **Running Plan**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64702/156576323155465_en-US.png)

6.  In the Running Plan dialog box, configure the following settings and click **OK**.
    -   If you have a periodical backup plan, click **Scheduled**。 On the Backup Policy drop-down list, select an existing backup policy.
    -   If no periodical backup plan exists, click **Instant**.
7.  On the Backup Jobs/Create Backup Workflow page, click **Backup Source**.
8.  In the Backup Source dialog box, configure the following settings. Then, click **OK**.

    |Name|Description|
    |:---|:----------|
    |Source|     -   Enter the path of a backup source. You can enter a maximum of eight paths, which means that you can back up data from eight paths at a time.
    -   The path is dedicated to storing workflow-based backups. The path must be directed to an empty folder.
    -   You can enter a universal naming convention \(UNC\) path.
    -   Separate multiple paths with carriage returns.
 |
    |Use VSS for backup \(Windows only\)|     -   If data changes occur in the backup source, select this option to ensure consistency between source data and backup data.
    -   This function is only available for hosts running Windows.
    -   If you select this option, you cannot back up data from multiple backup sources.
 |

9.  \(Optional\) On the Backup Jobs/Create Backup Workflow page, click **Network Flow Control**. In the Network Flow Controldialog box, select a period of **Work Hours** and a maximum bandwidth of **Throttling**, and then click **Add**. Confirm the configuration and click **OK**.

    **Note:** You can use flow control to set bandwidth limits for backing up data during peak hours to ensure business continuity. If you do not need to configure flow control, you can skip this step

10. On the Backup Jobs/Create Backup Workflow page, click **Post-backup Script**. In the Script Path field of the Post-backup Script dialog box, enter the directory of the post-backup script configured in [Step 2](#section_kll_y33_yfb). Click **OK**.

    **Note:** The script path must be a maximum of 250 characters in length.

11. On the Backup Jobs/Create Backup Workflow page, click **Submit** to start a backup job.

**Note:** 

-   If you need to cancel a backup job, locate the running backup job on the Backup Jobs page and click **Cancel** next to the backup job.
-   If a backup job fails, you can locate the running job on the Backup Job page and click **Retry** next to the backup job. You can also click the Download icon next to the **number of errors** to download and view the error report.

## More actions {#section_ckm_kk3_yfb .section}

[Restore backups](intl.en-US/Back up on-premises severs/Workflow-based backup/Restore backups.md)

[Search backups](intl.en-US/Back up on-premises severs/Workflow-based backup/Search backups.md)

