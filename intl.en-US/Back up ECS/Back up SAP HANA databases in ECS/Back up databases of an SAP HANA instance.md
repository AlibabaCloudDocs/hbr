# Back up databases of an SAP HANA instance

You can use Hybrid Backup Recovery \(HBR\) to back up SAP HANA databases that are hosted on Elastic Compute Service \(ECS\) and restore the databases if needed. This topic describes how to back up databases of an SAP HANA instance.

## Prerequisites

[Preparations](/intl.en-US/Back up ECS/Back up SAP HANA databases in ECS/Preparations.md) are completed.

## Create a backup plan

To create a backup plan for an SAP HANA instance, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Application Backup** \> **SAP HANA**.

3.  Click the **SAP HANA Instances** tab.

4.  Find the SAP HANA instance and click **Back Up** in the **Actions** column.

5.  In the Create Backup Plan pane, select the database that you want to back up and click **Next**.

    **Note:** You cannot back up databases that are stopped.

6.  In the Configure Plan step, set the parameters.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7460129951/p35977.png)

    |Parameter|Required|Description|
    |---------|--------|-----------|
    |Backup Policy|Yes|    -   If you need to immediately back up databases, select **Right Now**.
    -   If you need to back up databases based on a schedule, select **On Schedule**. |
    |Backup Type|Yes|    -   **Full**: backs up all data in the databases.
    -   **Incremental**: backs up the data that is added or modified after the most recent full backup or incremental backup.
    -   **Differential**: backs up the data that is modified after the most recent full backup. |
    |Backup Prefix|No|The prefix of a backup version. If you do not specify this parameter, the default prefix is used.|
    |Plan Name|No|The name of the backup plan. This parameter is required for scheduled backup.|
    |Start Time|No|The start time of the backup plan. The time is accurate to seconds. This parameter is required for scheduled backup.|
    |Backup Interval|No|The interval at which data backup is performed. Unit: hours, days, or weeks. This parameter is required for scheduled backup.|

7.  Click **OK**.


## \(Optional\) Configure the retention period of backup data

By default, HBR retains the backup data of SAP HANA databases for 10 years. To customize the retention period for the backup data of an SAP HANA database, perform the following steps:

1.  Click the SAP HANA Instances tab.

2.  Find the SAP HANA instance to which the database belongs, and click its ID in the SAP HANA Instance Name/ID column.

3.  On the SAP HANA Instance page, click the **Databases** tab. Find the database, and choose **More** \> **Configure Retention Policy** in the Actions column.

4.  In the Configure Retention Policy pane, set the parameters.

    |Parameter|Description|
    |:--------|:----------|
    |Retention Policy|    -   **Limited**

Select this option if you need to specify a limited retention period. In addition, you also must specify an interval at which retention jobs are run.

    -   **Permanent**

Select this option if you need HBR to permanently retain the backup data. |
    |Retention Job Interval|The interval at which retention jobs are run, in seconds. **Note:** We recommend that you avoid business and backup peak hours. |
    |Retention Period|The retention period of the backup data. Unit: days, weeks, months, or years. Minimum retention period: 1 day. Maximum retention period: 10 years.

**Note:** HBR deletes the expired catalogs and data that are related to Backint and file backup. The deleted catalogs and data cannot be restored. We recommend that you set the retention period to a reasonable value. |

5.  Click **Create**.

    **Note:** To change the retention period of the backup data, repeat the preceding steps and specify a new retention period.


## What to do next

After a backup plan is created, you can manage the backup plan. For example, you can cancel backup jobs and view backups.

-   Manage a backup plan

    In the HBR console, you can view the information and status of a created backup plan and manage the backup plan. To manage a backup plan, perform the following steps:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  In the left-side navigation pane, choose **Backup** \> **ECS Application Backup** \> **SAP HANA**.
    3.  Click the **Backup Plans** tab.
    4.  On the Backup Plans tab, view the information and status of backup plans.
    5.  In the Actions column, click a button to manage a backup plan. You can click **Modify**, **Run Immediately**, **Suspend Plan**, **Resume Plan**, or **Delete Plan**. If you delete the backup plan, HBR no longer runs backup jobs for the plan but the backup data is retained.

        ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7460129951/p35978.png)

-   View or cancel a backup job

    You can view the status of instant backup jobs and scheduled backup jobs. You can cancel running backup jobs. To view or cancel a backup job, perform the following steps:

    1.  Click the **Backup Jobs** tab.
    2.  On the Backup Jobs tab, find the backup job and view its information and status.
    3.  To cancel a running backup job, find the job and click **Cancel** in the Actions column.
-   View backups

    You can view all backups in the HBR console. To view backups of an SAP HANA instance, perform the following steps:

    1.  Click the **SAP HANA Instances** tab.
    2.  Find the SAP HANA instance and click its ID.
    3.  On the SAP HANA Instance page, click the **Backups** tab.
    4.  View the backups of the related backup jobs.

