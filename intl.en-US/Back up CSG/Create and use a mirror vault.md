# Create and use a mirror vault {#task_491269 .task}

A backup vault is a repository used by HBR to store backup data on the cloud. You can create a remote mirror vault for a backup vault to meet disaster recovery requirements. When necessary, you can use the remote mirror vault for cross-region data restoration.

**Note:** 

-   After a mirror vault is created, data that is being backed up by a backup job in the source vault is synchronized to the mirror vault in real time. The historical backups stored in the source vault start being synchronized to a mirror vault 90 minutes after the creation of the mirror vault.
-   You can only create one mirror vault for each backup vault.
-   You can restore backups stored in a mirror vault but cannot back up data to a mirror vault.
-   You must delete a mirror vault before deleting its source vault.
-   A source vault is created when you create a backup client.

## Create a mirror vault {#section_uha_17o_45x .section}

Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, select **Overview**.
3.  Locate a vault for which you want to create a mirror vault, click the ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/132497/156473348739694_en-US.png) icon in the upper-right corner.
4.  In the Create Mirror Vault dialog box, select a region where the new mirror vault is located.

    **Note:** For disaster recovery, you cannot select the region where the source vault is located.

5.  Enter the Vault Name. The name must be a maximum of 32 characters in length.
6.  Enter the Vault Description as required, and click **Create**.

## Restore backup data from a mirror vault {#section_pu6_44y_15p .section}

After a mirror vault is created, you can use it to restore backup data when necessary. The procedure is as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  Select the region of the mirror vault and [register a CSG instance](intl.en-US/Back up CSG/Preparations.md#section_ma1_77o_cec) for the mirror vault.
3.  Locate the target CSG instance and use it to [restore backup data](intl.en-US/Back up CSG/Restore a CSG instance.md#).

    **Note:** You must set Restore Resource to **From Other ECS**.


