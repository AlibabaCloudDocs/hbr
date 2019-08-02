# Restore backups {#concept_62974_zh .concept}

You can restore backups to a server or virtual machine. This applies to backups that are created by using a client or another client in the same vault.

**Note:** When you restore a piece of data among a large number of backups, you can use the[Search backups](intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Search backups.md#) function to locate the target piece of data in seconds.

## Restore backups by using this client {#section_whg_btc_sfb .section}

 **Procedure** 

1.  Log on to a Hybrid Backup Recovery \(HBR\) backup client.
2.  In the left-side navigation pane, select **Restore** to open the Restore Backup / Backups page.
3.  On the Backups tab, locate the target backup, and click **Restore** next to the backup.
4.  In the Restore Backup dialog box, configure the required settings as described in the following table, select backups to be restored, and click **Submit** to restore these backups.

    |Name|Description|
    |:---|:----------|
    |Target Folder|The target folder to which backups are restored.|
    |File Options|     -   Include Files: Only selected files and folders are restored to the target folder.
    -   Exclude Files: All files and folders are restored to the target folder except for the selected files and folders.
 |


## Restore from other clients {#section_cwb_rdg_xgb .section}

 **Procedure** 

1.  Log on to an HBR client.
2.  In the left-side navigation pane, select **Restore** to open the Restore Backup /Backups page.
3.  In the upper-right corner of the page, click **Restore From Other Client**.
4.  In the Restore Backup dialog box, select a client where files to be restored are located and click **Next**.
5.  Select the version of a backup to be restored and click **Next**.
6.  On the Restore File tab, configure the required settings as described in the following table, select files to be restored, and click **Submit** to restore a backup.

    |Name|Description|
    |:---|:----------|
    |Target Folder|The target folder to which backups are restored.|
    |File Options|     -   Include Files: Only selected files and folders are restored to the target folder.
    -   Exclude Files: All files and folders are restored to the target folder except for the selected files and folders.
 |


