# Restore shares across regions by using a mirror vault

A backup vault is a repository that Hybrid Backup Recovery \(HBR\) uses to store backup data on the cloud. A mirror vault is the mirror of a backup vault. The two vaults reside in different regions. You can use a mirror vault for geo-disaster recovery and cross-region data restoration.

## Create a mirror vault

To create a mirror vault, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Overview**.

3.  Find the card of the backup vault for which you want to create a mirror vault. In the upper-right corner of the card, click the ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2488449951/p39694.png) icon.

4.  In the Create Mirror Vault pane, select the region where you want to create the mirror vault.

    **Note:** To implement disaster recovery, do not select the region where the backup vault resides.

5.  Enter a vault name. The name must be 1 to 32 characters in length.

6.  Enter a description of the vault and click **Create**.


## Restore data from a backup stored in a mirror vault

To restore data from a backup that is stored in a mirror vault, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  Select the region where the mirror vault resides. Then, [register a storage gateway](/intl.en-US/Back up CSG/Preparations.md) and set the backup vault to the mirror vault.

3.  [Restore data to the storage gateway](/intl.en-US/Back up CSG/Restore a CSG instance.md).

    **Note:** In this step, set the Restore From parameter to **Other Gateway**.


