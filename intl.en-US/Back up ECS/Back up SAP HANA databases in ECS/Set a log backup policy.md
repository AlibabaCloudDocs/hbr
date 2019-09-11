# Set a log backup policy {#concept_edf_12r_ggb .concept}

Hybrid Backup Recovery \(HBR\) supports log backup. This feature allows you to restore a database to the status at a specified time point.

## Procedure {#section_u2p_mxr_ggb .section}

1.  Ensure that the SAP HANA instance is registered. On the SAP HANA Backup page, click the **SAP HANA Instance** tab.
2.  In the Actions column, choose **More** \> **Manage Node** for the target SAP HANA instance.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83627/156818811960279_en-US.jpg)

3.  Click the **Database** tab to view the status of all databases on the SAP HANA instance.
4.  In the right-side Actions column, choose More \> **Config Backup** for the target database.
5.  In the Config Backup dialog box, set the parameters as instructed in the following table.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83627/156818811960281_en-US.jpg)

    |Parameter|Description|
    |:--------|:----------|
    |Auto Log Backup|Specify whether to regularly back up logs.|
    |Log Backup to Backint|Specify whether to use Backint to back up logs.|
    |Log Backup Interval|Specify the interval for log backup. Minimum interval: 15 minutes.|

6.  Click **Create**.

