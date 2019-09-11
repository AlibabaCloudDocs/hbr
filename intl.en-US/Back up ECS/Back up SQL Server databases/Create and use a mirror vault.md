# Create and use a mirror vault {#concept_220894 .concept}

A mirror vault is the mirror of a backup vault. However, the two vaults are located in different regions. You can use a mirror vault for geo-disaster recovery or cross-region data restoration.

**Note:** 

-   After a mirror vault is created, ongoing backup jobs in the source vault are synchronized to the mirror vault in real time. The historical backup data stored in the source vault is synchronized to the mirror vault 90 minutes after the mirror vault is created.
-   You can create only one mirror vault for each backup vault.
-   You can restore backup data stored in a mirror vault but cannot back up the data in a mirror vault.
-   You must delete a mirror vault before deleting its source vault.
-   A source vault is created when you create a backup client.

## 创建镜像仓库 {#section_ay2_2pd_vu5 .section}

具体操作步骤如下：

1.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。
2.  在左侧导航栏，选择**概览**。
3.  选择需要创建镜像的仓库，并在其右上角单击![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/132497/156819094239694_zh-CN.png)。
4.  在弹出的窗口中，选择创建镜像仓库的地域。

    **Note:** 出于容灾考虑，您无法选择源仓库所在的地域。

5.  输入仓库名称，仓库名称不得超过32个字节。
6.  根据需要，输入仓库描述，然后单击**创建**。

## Restore a SQL Server database from a backup stored in a mirror vault {#section_i0p_j5i_712 .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/187890/156819094260303_en-US.jpg)

As shown in the preceding figure, a database in SQL Server cluster A is backed up in a backup vault in region A. To restore the database to SQL Server cluster B in region B, you need to log on to the Hybrid Backup Recovery \(HBR\) console on an Elastic Compute Service \(ECS\) instance where SQL Server cluster B is deployed, and register a SQL Server instance in the console. The procedure is as follows:

1.  Log on to the HBR console on an ECS instance that is located in the destination region, and [register a SQL Server instance](intl.en-US/Back up ECS/Back up SQL Server databases/Preparations.md#).

    **Note:** Select the destination mirror vault as the backup vault.

2.  Find the registered SQL Server instance in the HBR console, and then [restore the database to the destination SQL Server instance](intl.en-US/Back up ECS/Back up SQL Server databases/Restore a SQL Server database.md#).

