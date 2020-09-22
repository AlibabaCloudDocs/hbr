# Restore files

You can restore files to the source server or virtual machine \(VM\). You can also restore files to a server or VM that is different from the backup source.

**Note:** If you have a large number of backup files, you can use the file search feature to locate the files that you want to restore. For more information, see [Search backups](/intl.en-US/Back up on-premises severs/File backup/Search backups.md).

## Restore files to the source client

To restore files to the source client, perform the following steps:

1.  Log on to a Hybrid Backup Recovery \(HBR\) backup client.

2.  In the left-side navigation pane, click **Restore** to open the Restore Backup / Backups page.

3.  On the Backups tab, find the backup, and click **Restore** in the Actions column.

4.  In the Restore Backup dialog box, set the parameters that are listed in the following table, select the files that you want to restore, and then click **Submit**.

    |Parameter|Description|
    |:--------|:----------|
    |Target Folder|The destination folder to which the files are restored.|
    |File Options|    -   **Include Files**: Only the selected files and folders are restored to the destination folder.
    -   **Exclude Files**: Except for the selected files and folders, all other files and folders are restored to the target folder. |


## Restore files to a client that is different from the backup source

To restore files to a client that is different from the backup source, perform the following steps:

1.  Log on to the destination HBR file backup client.

2.  In the left-side navigation pane, click **Restore** to open the Restore Backup / Backups page.

3.  In the upper-right corner of the Backups tab, click **Restore From Other Client**.

4.  In the Restore Backup dialog box, select the source client and click **Next**.

5.  Select the backup that you want to restore, and click **Next**.

6.  In the Restore Backup dialog box, set the parameters that are listed in the following table, select the files that you want to restore, and then click **Submit**.

    |Parameter|Description|
    |:--------|:----------|
    |Target Folder|The folder to which the files are restored.|
    |File Options|    -   **Include Files**: Only the selected files and folders are restored to the destination folder.
    -   **Exclude Files**: Except for the selected files and folders, all other files and folders are restored to the target folder. |


