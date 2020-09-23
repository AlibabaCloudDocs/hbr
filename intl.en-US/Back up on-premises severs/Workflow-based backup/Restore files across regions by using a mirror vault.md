# Restore files across regions by using a mirror vault

A backup vault is a repository that Hybrid Backup Recovery \(HBR\) uses to store backup data on the cloud. You can back up data from multiple backup clients to the same vault. You can create a remote mirror vault for a vault to implement disaster recovery.

**Note:**

-   After a mirror vault is created, backup data in the source vault is synchronized to the mirror vault in real time. The historical backup data stored in the source vault is synchronized to the mirror vault 90 minutes after the mirror vault is created.
-   You can create only one mirror vault for each backup vault.
-   You can restore the backup data that is stored in a mirror vault but cannot back up the data in a mirror vault.
-   You must delete a mirror vault before you can delete the corresponding backup vault.
-   You can create a backup vault when you create a backup client.

![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/4072580061/p44049.png)

## Create a mirror vault

To create a mirror vault, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Overview**.

3.  Find the card of the backup vault for which you want to create a mirror vault. In the upper-right corner of the card, click the ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2488449951/p39694.png) icon.

4.  In the Create Mirror Vault pane, select the region where you want to create the mirror vault.

    **Note:** To implement disaster recovery, do not select the region where the backup vault resides.

5.  Enter a vault name. The name must be 1 to 32 characters in length.

6.  Enter a description of the vault and click **Create**.


## Restore files from a mirror vault

To restore data from a backup that is stored in a mirror vault, perform the following steps:

1.  [Download](/intl.en-US/Back up on-premises severs/File backup/Preparations.md) and [install](/intl.en-US/Back up on-premises severs/File backup/Preparations.md) a backup client for files on the destination server or virtual machine \(VM\).

    **Note:** When you download the backup client, you must specify the name of the mirror vault as the Vault Name parameter.

2.  Log on to the backup client on the destination server or VM and then [restore backups from another backup client](/intl.en-US/Back up on-premises severs/File backup/Restore files.md).

    **Note:** To find the files that you want to restore, you can use the [backup search](/intl.en-US/Back up on-premises severs/Workflow-based backup/Search backups.md) feature.


