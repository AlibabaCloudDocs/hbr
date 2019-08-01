# Search backups {#concept_owz_y4c_wfb .concept}

When you restore a piece of data among a large number of backups, you can use the backup search function to locate the target piece of data in seconds.

## Turn on the backup search function {#section_jcv_cpc_wfb .section}

1.  Log on to the [Hybrid Backup Recovery \(HBR\) console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, select **Overview**.
3.  On the Overview page, locate the required vault where you need to turn on the backup search function.
4.  In the upper-right corner of the vault, click Settings.
5.  In the Vault Setting dialog box, turn on Backup Search.

**Note:** The backup search function is only available for vaults that are located in the China \(Hangzhou\) and China \(Shanghai\) regions.

## Search backups {#section_snw_fpc_wfb .section}

1.  Log on to an HBR backup client.
2.  In the left-side navigation pane, select **Restore**.
3.  On the Restore Backup / Backups page, select the **Search Backups** tab.
4.  Enter a keyword or relative path of a file that you need to restore and click **Search**.

    **Note:** 

    -   You can search for a file by using the full name of the file. You must enclose the full name with a pair of quotation marks \("\).
    -   When searching for a file by a relative path, you must use forward slashes \(/\) as delimiters. For example, A/test.text.
5.  You can also turn on **Advanced Search** in the upper-right corner of the page. Configure one or more of the following settings and click **Search**.

    |Name|Description|
    |:---|:----------|
    |File Type|Select **File** or **Folder** as required.|
    |Modify Time|The last modification time of a file. The time is accurate to the second. If you need to clear the specified time, click `X` next to the time.|
    |File Size|You can specify a range of backup sizes. Valid values: KB, MB, and GB. The minimum size of a backup is 0 KB.|
    |Backup Time|A time period in which the target backup is completed. You must specify the start time and the end time of the period. The time is accurate to the second. If you need to clear the specified time, click `X` next to the time.|

    If you need to cancel the previous settings, click **Reset**.

6.  Search results are displayed at the bottom of the Search Backups page, locate the backup you need to restore and click **Restore** next to the backup.
7.  In the Restore Backup dialog box, enter the target folder to which you need to restore the file, and click **Submit** to restore the backup.

