# Mirror vaults {#concept_ny4_dnt_xgb .concept}

A backup vault is a Hybrid Backup Recovery \(HBR\) warehouse used to store backup data on the cloud. You can create a remote mirror vault for a backup vault to meet disaster recovery requirements. You can also use a mirror vault for geo-disaster recovery or cross-region data restoration.

**Note:** 

-   After a mirror vault is created, data that is being backed up by a backup job in the source vault is synchronized to the mirror vault in real time. The historical backups stored in the source vault start being synchronized to a mirror vault 90 minutes after the creation of the mirror vault.
-   You can only create one mirror vault for each backup vault.
-   You can restore backups stored in a mirror vault but cannot back up data to a mirror vault.
-   You must delete a mirror vault before deleting its source vault.
-   A source vault is created when you create a backup client.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/132497/156465317154088_en-US.jpg)

## Create a mirror vault {#section_vhf_xnt_xgb .section}

Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, select **Overview**.
3.  Locate a vault for which you want to create a mirror vault, click the ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/132497/156465317139694_en-US.png) icon in the upper-right corner.
4.  In the Create Mirror Vault dialog box, select a region where the new mirror vault is located.

    **Note:** For disaster recovery, you cannot select the region where the source vault is located.

5.  Enter the Vault Name. The name must be a maximum of 32 characters in length.
6.  Enter the Vault Description as required, and click **Create**.

## Restore data from a backup stored in a mirror vault {#section_vrt_gyt_xgb .section}

If you attempt to restore data from a backup stored in a remote mirror vault, log on to the Hybrid Backup Recovery \(HBR\) console on an ECS instance that is located in the target region. Proceed as follows:

1.  [Install a backup client on an ECS instance](intl.en-US/Back up ECS/Back up files in ECS/Prerequisites.md#section_vb1_zz5_fgb).

    **Note:** Select the target mirror vault when selecting a vault.

2.  Locate the ECS instance in the HBR console, and then [use the ECS instance to restore data from a backup](intl.en-US/Back up ECS/Back up files in ECS/Restore data from a backup to an ECS instance.md).

    **Note:** In the **Restore Source** field, select **From Other ECS** or **From Local Client** as required.


