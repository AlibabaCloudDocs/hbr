# Restore files across regions by using an image repository

This topic describes how to restore files across regions by using an image repository. An image repository is a repository where Hybrid Backup Recovery \(HBR\) stores backup data in the cloud. You can create a remote image repository for a backup vault to meet disaster recovery requirements. When necessary, you can use the remote image repository to restore data across regions.

**Note:**

-   After a mirror vault is created, backup data in the backup vault is synchronized to the mirror vault in real time. The historical backup data in the backup vault starts to be synchronized to the mirror vault 90 minutes after the mirror vault is created.
-   You can create only one mirror vault for each backup vault.
-   You can restore the backup data that is stored in a mirror vault but cannot back up the data in a mirror vault.
-   You must delete a mirror vault before you can delete the corresponding backup vault.
-   You can create a backup vault when you create a backup client.

## Create a mirror vault

To create a mirror vault, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Overview**.

3.  Find the card of the backup vault for which you want to create a mirror vault. In the upper-right corner of the card, click the ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2488449951/p39694.png) icon.

4.  In the Create Mirror Vault pane, select the region where you want to create the mirror vault.

    **Note:** To implement disaster recovery, do not select the region where the backup vault resides.

5.  Enter a vault name. The name must be 1 to 32 characters in length.

6.  Enter a description of the vault and click **Create**.


## Restore files from a backup stored in a mirror vault

Before you restore files that is stored in a mirror vault, perform the following steps to install a backup client for files on the destination server or virtual machine \(VM\) and add the client to the mirror vault.

1.  [Download](/intl.en-US/Back up on-premises severs/File backup/Preparations.md) and [install](/intl.en-US/Back up on-premises severs/File backup/Preparations.md) a file backup client on the destination server or VM.

    **Note:** Before you download a backup client, you must create a client. When you create the client, select the mirror vault.

2.  Log on to the backup client on the destination server or VM, and [restore files from another client](/intl.en-US/Back up on-premises severs/File backup/Restore files.md).

    **Note:** To find the files that you want to restore, you can use the [backup search](/intl.en-US/Back up on-premises severs/File backup/Search backups.md) feature.


