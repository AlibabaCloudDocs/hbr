# Search backups

If you have a large number of backup files, you can use the backup search feature to locate the file that you want to restore.

## Enable the backup search feature

To enable the backup search feature for a backup vault, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Overview**.

3.  On the Overview page, find the backup vault.

4.  In the upper-right corner of the vault card, click the Settings icon.

5.  In the Modify Backup Vault pane, turn on the Backup Search feature.

    **Note:** The backup search feature is available only for backup vaults that are located in the China \(Hangzhou\) and China \(Shanghai\) regions.


## Search backups

To use the backup search feature, perform the following operations:

1.  Log on to an HBR backup client.

2.  In the left-side navigation pane, click **Restore**.

3.  On the Restore Backup / Backups page, click the **Search Backups** tab.

4.  Enter a keyword or relative path of a file that you want to restore and click **Search**.

    **Note:**

    -   To search for a file by full file name, enclose the full name within a pair of double quotation marks \("\).
    -   To search for files by relative path, use forward slashes \(/\) as the path separator, for example, A/test.text.
5.  You can also enable **Advanced Search** in the upper-right corner of the page. Set one or more of the following conditions and click **Search**.

    |Condition|Description|
    |:--------|:----------|
    |File Type|Select **File** or **Folder** based on your requirements.|
    |Modify Time|Specify the last modification time of a file. The time is accurate to the second. If you need to clear the specified time, click the cross sign \(`×`\) next to the time.|
    |File Size|Specify a file size range. Unit: KB, MB, or GB. The minimum size of a file is 0 KB.|
    |Backup Time|Specify the start time and end time of the time period in which the backup of a file is completed. The time is accurate to the second. If you need to clear the specified time, click the cross sign \(`×`\) next to the time.|

    If you need to clear the search conditions, click **Reset**.

6.  Search results are displayed at the bottom of the Search Backups tab. Find the file you want to restore, and click **Restore** next to the file.

7.  In the Restore Backup dialog box, enter the folder to which you want to restore the file, and click **Submit** to restore the backup.


