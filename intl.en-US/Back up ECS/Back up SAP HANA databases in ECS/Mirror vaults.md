# Mirror vaults {#concept_ny4_dnt_xgb .concept}

A mirror vault is the mirror of a backup vault. The two vaults are located in different regions. You can use a mirror vault for geo-disaster recovery or cross-region data restoration.

**Note:** 

-   After a mirror vault is created, ongoing backup jobs in the source vault are synchronized to the mirror vault in real time. The historical backup data stored in the source vault is synchronized to the mirror vault 90 minutes after the mirror vault is created.
-   You can create only one mirror vault for each backup vault.
-   You can restore backup data stored in a mirror vault but cannot back up the data in a mirror vault.
-   You must delete a mirror vault before deleting its source vault.
-   A source vault is created when you create a backup client.

## Create a mirror vault {#section_vhf_xnt_xgb .section}

The procedure is as follows:

1.  Log on to the [Hybrid Backup Recovery \(HBR\) console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, click **Overview**.
3.  Select a backup vault for which you want to create a mirror vault, and click the ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/132497/156894483639694_en-US.png) icon in the upper-right corner of the backup vault.
4.  In the Create Mirror Vault dialog box, select a region where the mirror vault is located.

    **Note:** For disaster recovery, you cannot select the region where the source vault is located.

5.  Set Vault Name. The vault name can be up to 32 characters in length.
6.  Set Vault Description as required, and then click **Create**.

## Restore an SAP HANA database from a backup stored in a mirror vault {#section_vrt_gyt_xgb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/162161/156894483661567_en-US.jpg)

As shown in the preceding figure, a database in SAP HANA cluster A is backed up in a backup vault in region A. To restore the database to SAP HANA cluster B in region B, you need to log on to the HBR console on an Elastic Compute Service \(ECS\) instance where SAP HANA cluster B is deployed, and register an SAP HANA instance in the console.

