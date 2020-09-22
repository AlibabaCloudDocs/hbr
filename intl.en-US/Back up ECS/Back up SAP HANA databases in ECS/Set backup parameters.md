# Set backup parameters

This topic describes how to set the parameters that are related to Backint and log backup for SAP HANA databases.

Log backup allows you to restore an SAP HANA database to a specified time point when data in the database is lost or damaged. Backint is used to implement cross-region restoration based on catalog backups.

1.  Log on to the [Hybrid Backup Recovery \(HBR\) console](https://hbr.console.aliyun.com).

2.  Make sure that at least one SAP HANA instance is registered. On the ECS Application Backup page, click SAP HANA. Click the **SAP HANA Instances** tab.

3.  Click an instance ID.

4.  On the SAP HANA Instance page, click the **Databases** tab. On this tab, you can view the status of all databases in the SAP HANA instance.

5.  Find the database, and choose **More** \> **Set Backup Parameters** in the Actions column.

6.  In the Set Backup Parameters pane, set the parameters.

    ![config](../images/p104569.jpg)

    |Parameter|Required|Description|
    |:--------|--------|:----------|
    |Backint Settings|
    |Data Backup Config File|No|The configuration file that contains Backint parameters and is used for data backup. **Note:**

    -   We recommend that you use the same configuration file for data backup, log backup, and catalog backup.
    -   If an SAP HANA instance consists of multiple nodes, you must configure a data backup configuration file for each node. |
    |Use this file for log backup and catalog backup|No|Specifies whether to use the data backup configuration file for log backup and catalog backup. We recommend that you select this check box.|
    |Log Backup Config File|No|The configuration file that contains Backint parameters and is used for log backup.|
    |Catalog Backup Config File|No|The configuration file that contains Backint parameters and is used for catalog backup.|
    |Use Backint for Catalog Backup|No|Specifies whether to use Backint to back up catalogs. We recommend that you turn on this switch to improve the backup performance. **Note:** If you turn off this switch, cross-instance database restoration is not supported. |
    |Log Backup settings|
    |Auto Log Backup|Yes|Specifies whether to back up logs on a regular basis.|
    |Use Backint for Log Backup|Yes|Specifies whether to use Backint to back up logs.|
    |Log Backup Interval|Yes|The interval at which logs are backed up. **Note:** We recommend that you set the log backup interval to a minimum of 15 minutes. If you need to specify a smaller log backup interval, set it by using HANA Studio or HANA Cockpit. |

7.  Click **Create**.


