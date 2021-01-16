# Restore files across regions by using an image repository

An image repository is a repository where Hybrid Backup Recovery \(HBR\) stores backup data in the cloud. You can create a remote image repository for a backup vault to meet disaster recovery requirements. When necessary, you can use the remote image repository to restore data across regions.

**Note:**

-   After an image repository is created, the data in the backup vault is synchronized to the image repository in real time. The historical backup data stored in the backup vault is synchronized to the image repository 90 minutes after the image repository is created.
-   You can create only one image repository for each backup vault.
-   You can restore the data that is stored in an image repository but cannot back up the data in an image repository.
-   Before you can delete a backup vault, you must delete its image repository.
-   You can create a backup vault when you create a backup client.

![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0941890951/p54088.jpg)

## Create an image repository

To create an image repository, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Overview**.

3.  Find the card of the backup vault for which you want to create an image repository. In the upper-right corner of the card, click **Cross-Region Backup**.

4.  In the Create Mirror Vault dialog box, select the region where you want to create the image repository.

    **Note:**

    -   To implement disaster recovery, do not select the region where the backup vault resides.
    -   5.  Enter a vault name in the Vault Name field. The vault name cannot exceed 64 characters in length.

6.  Enter a description of the vault in the Description field. Click **Create**.


## Restore data from a backup file stored in an image repository

If you need to restore data from a backup stored in an image repository, log on to the HBR console on an ECS instance. The ECS instance must reside in the same region as the image repository. Then, install the backup client. To restore data from a backup file stored in an image repository, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  [Install a backup client on an ECS instance](/intl.en-US/Back up ECS/ECS file backup/Preparations.md).

    **Note:** Select the image repository.

3.  [Restore data to the ECS instance in the HBR console](/intl.en-US/Back up ECS/ECS file backup/Restore files to an ECS instance.md).

    **Note:** Select **Other ECS Instance** or **Local Server** from the **Restore From** drop-down list.


