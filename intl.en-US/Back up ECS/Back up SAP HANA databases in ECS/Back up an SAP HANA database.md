# Back up an SAP HANA database {#concept_f5y_cxj_ggb .concept}

You can use Hybrid Backup Recovery \(HBR\) to back up SAP HANA databases deployed on Alibaba Cloud Elastic Compute Service \(ECS\) instances and restore these databases as required. This topic describes how to back up an SAP HANA database.

## Prerequisites {#section_vnn_bfv_fgb .section}

[Preparations](intl.en-US/Back up ECS/Back up SAP HANA databases in ECS/Preparations.md) are completed.

## Procedure {#section_zft_r3l_ggb .section}

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **ECS Backup** \> **SAP HANA Backup**.
3.  Click the **SAP HANA Instance** tab.
4.  In the right-side Actions column, click **Backup** for the SAP HANA instance to be backed up.
5.  In the Create Plan dialog box, select the database to be backed up, and then click **Next**.

    **Note:** You cannot back up databases that are stopped.

6.  Set Backup Policy. If you do not need to regularly back up the database, select **Instant Backup**. Otherwise, select **Schedule Backup**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83225/156818809460260_en-US.jpg)

7.  Set **Backup Type**. Backup types are described as follows:
    -   **Complete**: backs up full data in the database.
    -   **Differential**: backs up data modified after the last full backup.
    -   **Incremental**: backs up data modified after the last full backup, incremental backup, or differential backup.
8.  Set **Backup Prefix**.
9.  If you select **Schedule Backup**, you also need to set **Plan Name**, **Start Time**, and **Plan Interval**.
10. Click **OK**.
11. By default, HBR keeps SAP HANA database backup data for 10 years. To customize the retention period, perform the following operations:

    1.  On the SAP HANA Backup page, click the SAP HANA Instance tab.
    2.  Click the instance name or choose More \> **Manage Node** in the right-side Actions column for the target SAP HANA instance. The HANA Instance Info page appears.
    3.  On the HANA Instance Info page, click the **Database** tab, find the target database, and then choose More \> **Config Retention** in the right-side Actions column.
    4.  In the Config Retention dialog box, set the parameters as instructed in the following table.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83225/156818809460262_en-US.jpg)

        |Parameter|Description|
        |:--------|:----------|
        |Retention Policy|         -   **Default \(10 years\)** 

Select this option if you want to keep backup data for 10 years. HBR automatically deletes the backup data when the retention period expires.

        -   **Customized** 

By selecting this option, you can customize the time for deleting expired backup data each day and the backup retention period.

 |
        |Time to Run Retention|Specify the time for deleting expired backup data. The time is accurate to seconds. We recommend that you specify a time other than business and backup peak hours.|
        |Retention|Specify the retention period of backup data. Valid units: day, week, month, and year. Maximum retention period: 10 years. **Note:** After the retention period expires, HBR automatically deletes the expired catalogs and data related to Backint backup and file backup. This operation is unrecoverable. Specify the retention period with caution.

 |

    5.  Click **Create**.
    **Note:** To modify the backup retention period, you can repeat the preceding steps and specify another retention period.


## Related operations {#section_u1j_b2y_ggb .section}

-   Manage a backup plan

    In the HBR console, you can view the information and status of created backup plans, and manage these backup plans. The procedure is as follows:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  In the left-side navigation pane, choose **ECS Backup** \> **SAP HANA Backup**.
    3.  Click the **Backup Plan** tab.
    4.  Check the backup plan information and status on the Backup Plan tab.
    5.  Click an operation in the Actions column to manage a backup plan. Operations in the Actions column are **Edit**, **Excute Now**, **Disable Plan**, **Enable Plan**, and **Delete Plan**. After you delete a backup plan, HBR does not run the plan any more but reserves backup data.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83225/156818809460264_en-US.jpg)

-   View and cancel a backup job

    You can view the status of **Instant Backup** jobs and **Schedule Backup** jobs. You can also cancel an ongoing backup job. The procedure is as follows:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  In the left-side navigation pane, choose **ECS Backup** \> **SAP HANA Backup**.
    3.  Click the **Backup Jobs** tab.
    4.  Check the backup job information and status on the Backup Jobs tab.
    5.  To cancel an ongoing backup job, click **Cancel** in the right-side Actions column for the job.
-   View backup history

    You can view all backup history in the HBR console. The procedure is as follows:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  In the left-side navigation pane, choose **ECS Backup** \> **SAP HANA Backup**.
    3.  Click the **SAP HANA Instance** tab.
    4.  In the right-side Actions column, choose **More** \> **Manage Node** for the target SAP HANA instance.
    5.  On the HANA Instance Info page, click the **Backup History** tab.
    6.  View backup job details on the Backup History tab.

