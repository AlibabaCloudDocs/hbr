# Search for backup files

This topic describes how to enable and use the backup search feature. If you have a large number of backup files, you can use the backup search feature to locate a file that you want to restore.

## Enable the backup search feature

To enable the backup search feature for a backup vault, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Overview**.

3.  On the Overview page, find the backup vault.

4.  In the upper-right corner of the vault card, click the Settings icon.

5.  In the Modify Backup Vault pane, turn on the Backup Search feature.

    **Note:** The backup search feature is available only for backup vaults that are located in the China \(Hangzhou\) and China \(Shanghai\) regions.


## Search for backup files

To use the backup search feature, perform the following steps:

1.  Log on to the [Hybrid Backup Recovery \(HBR\) console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **On-Premises Backup**. On the On-Premises Backup page, click the **File \(New\)** tab.

3.  Click the **Search Backups** tab.

4.  In the upper-left corner of the Search Backups tab, select a backup vault from the **Backup Vault** drop-down list.

5.  Enter a file name or folder name in the search bar. Then, press Enter or click **Search**.

6.  The search results are displayed on the Search Backups tab.

    The following table describes the required parameters.

    |Parameter|Description|
    |---------|-----------|
    |Source Paths|The path of the file.|
    |Backup Client Name/ID|The name and ID of the backup client.|
    |Snapshot ID/Hash|The snapshot ID and hash code of the backup.|
    |File Size|The size of the file.|
    |Modify Time|The time when the file was last modified.|
    |Backup Time|The time when the file was backed up.|
    |Actions|The operation that you want to perform. Set the value to Restore to restore the file.|

7.  You can also turn on **Advanced Search** in the upper-right corner of the page. Set one or more of the following parameters and click **Search**.

    The following table describes the available parameters.

    |Parameter|Description|
    |:--------|:----------|
    |Backup Client|The client that is used to back up the file. Select a backup client as needed.|
    |Search Type|The type of the file. Valid values:    -   **File**: searches for a file.
    -   **Folder**: searches for a folder. |
    |Modify Time|The start time and end time of the period during which the file was last modified. The time is accurate to the second. If you need to clear the specified time, click the cross sign \(`×`\) next to the time.|
    |Min Size|The upper limit of the file size. Unit: KB, MB, or GB. Minimum value: 0 KB.|
    |Max Size|The lower limit of the file size. Unit: KB, MB, or GB. Minimum value: 0 KB.|
    |Backup Time|The start time and end time of the period during which the file is backed up. The time is accurate to the second. If you need to clear the specified time, click the cross sign \(`×`\) next to the time.|

    **Note:** If you need to clear the search conditions, click **Reset** in the upper-right corner.


## Preview the search

The following figure shows the preview of the search backup feature. In this example, init is used as a keyword.

![Preview](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8996390161/p225456.png)

