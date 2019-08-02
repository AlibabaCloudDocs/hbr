# Mirror vaults {#concept_q4n_bc5_xgb .concept}

A backup vault is an HBR cloud backup warehouse used to store backup data on the cloud. You can create a remote mirror vault for a vault to meet disaster recovery requirements. You can also use a mirror vault for cross-region data restoration.

**Note:** 

-   After a mirror vault is created, backup jobs that are running in the source vault are synchronized to the mirror vault in real time. The historical backups of the source vault start being synchronized to a mirror vault 90 minutes after the creation of the mirror vault.
-   You can only create one mirror vault for each backup vault.
-   You can restore backups from a mirror vault but cannot back up data to a mirror vault.
-   You must delete a mirror vault before deleting the linked source vault.
-   A source vault is created when you create a backup client.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/132912/156472627554118_en-US.jpg)

## Create a mirror vault {#section_vhf_xnt_xgb .section}

Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, click **Overview**.
3.  Locate a vault for which you need to create a mirror vault, click the ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/132912/156472627539717_en-US.png) icon in the upper-right corner.
4.  In the Create Mirror Vault dialog box, select a region where the new mirror vault is located.

    **Note:** For disaster recovery, we recommend that you do not select the same region where the source vault is located.

5.  Enter the Vault Name. The vault name must be a maximum of 32 characters in length.
6.  Enter the Vault Description as required, and click **Create**.

## Restore backups from mirror vaults {#section_vrt_gyt_xgb .section}

To restore data from a remote mirror vault, you need to download a backup client to the target server or virtual machine. You must specify the backup source as the mirror vault for the backup client. Proceed as follows:

1.  On the server or virtual machine from which you need to restore data, [download](intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Prerequisites.md#section_cnq_phc_ggb) and [install](intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Prerequisites.md#section_g3t_wvd_qfb) a backup client.

    **Note:** When you configure the backup client, you need to specify the Backup Vault Name as the name of the target mirror vault.

2.  Log on to the backup client on the target server or virtual machine, and [restore backups from another client](intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Restore backups.md#section_cwb_rdg_xgb).

    **Note:** You can also use the [Search backups](intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Search backups.md) function to restore backups.


