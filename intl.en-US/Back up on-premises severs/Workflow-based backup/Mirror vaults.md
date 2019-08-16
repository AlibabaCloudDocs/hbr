# Mirror vaults {#concept_q4n_bc5_xgb .concept}

A backup vault is a Hybrid Backup Recovery \(HBR\) cloud warehouse used to store backup data on the cloud. Backup data from multiple clients can be stored in the same vault. You can create a remote mirror vault for a vault to meet the disaster recovery requirements.

**Note:** 

-   After a mirror vault is created, data that is being backed up by a backup job in the source vault are synchronized to the mirror vault in real time. The historical backups of the source vault start being synchronized to a mirror vault 90 minutes after the creation of the mirror vault.
-   You can only create one mirror vault for each backup vault.
-   You can restore backups from a mirror vault but cannot back up data to a mirror vault.
-   You must delete a mirror vault before deleting its source vault.
-   A source vault is always created when you create a backup client.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/132912/156576329954118_en-US.jpg)

## Create a mirror vault {#section_vhf_xnt_xgb .section}

Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, select **Overview**.
3.  Locate a backup vault for which you need to create a mirror vault, and click the ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/132912/156576329939717_en-US.png) icon in the upper-right corner of the backup vault.
4.  In the Create Mirror Vault dialog box, select a region where the mirror vault is located.

    **Note:** For disaster recovery, you cannot select a region where the source vault is located.

5.  Enter the Vault Name. The vault name must be less than 32 characters in length.
6.  Enter the Vault Description as required, and then click **Create**.

## Use a mirror vault {#section_vrt_gyt_xgb .section}

After a mirror vault is created, you can restore backups from the mirror vault as needed. Proceed as follows:

1.  [Download](intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Prerequisites.md#section_cnq_phc_ggb) and [install](intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Prerequisites.md#section_g3t_wvd_qfb) a file client on a server or virtual machine to which you need to restore data.

    **Note:** When downloading the file client, you must specify the name of the target vault as the Vault Name.

2.  Log on to the file client on the target server or virtual machine and then [restore backups from another file client](intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Restore backups.md#section_cwb_rdg_xgb).

    **Note:** You can also use the [backup search](intl.en-US/Back up on-premises severs/Workflow-based backup/Search backups.md) function to restore data.


