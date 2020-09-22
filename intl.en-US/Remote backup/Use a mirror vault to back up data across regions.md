# Use a mirror vault to back up data across regions

A backup vault is a repository that Hybrid Backup Recovery \(HBR\) uses to store backup data in the cloud. You can create a remote mirror vault for a backup vault and back up data in the backup vault to the mirror vault to meet disaster recovery requirements. Then, data in the backup vault is automatically copied to the mirror vault.

Before you use a mirror vault, note the following information:

-   You can create only one mirror vault for each backup vault.
-   You can back up data to a remote mirror vault and restore backup data from the mirror vault. However, you cannot create backup plans for the mirror vault. HBR starts to synchronize historical data in a source backup vault to the mirror vault 90 minutes after the mirror vault is created.
-   A mirror vault contains all the backup data that is stored in the source backup vault when the mirror vault is created.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Overview**. On the Overview page, select a region, for example, China \(Hangzhou\), next to **Regions**. Find the card of the backup vault for which you want to create a mirror vault, and click the ![+](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8437029951/p85985.jpg) icon in the upper-right corner of the vault card.

    ![add](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8437029951/p85986.jpg)

3.  In the Create Mirror Vault pane, select the region in which you want to create the mirror vault, enter the name of the mirror vault, and then click **Create**.

    **Note:** To implement disaster recovery, you cannot select the region where the source backup vault resides.

    ![mirror](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8437029951/p85997.jpg)

    You can view the data synchronization progress after you create a mirror vault. When the progress reaches 100%, it indicates that all data in the source backup vault is synchronized to the mirror vault.

    ![progress](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8437029951/p86044.jpg)

    Before you can delete a source backup vault, you must delete its mirror vault. To delete a mirror vault, click the ![delete](../images/p107748.jpg) icon in the upper-right corner of the mirror vault card.

    ![copy](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2221061951/p107750.jpg)


