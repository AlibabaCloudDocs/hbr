# Preparations

You can use Hybrid Backup Recovery \(HBR\) to back up shares of Cloud Storage Gateway \(CSG\). You can then restore the shares if needed. This topic describes the preparations that you must make before backup.

**Note:** You can use the CSG backup service in the following regions: China \(Shanghai\), China \(Hangzhou\), China \(Beijing\), China \(Shenzhen\), China \(Zhangjiakou-Beijing Winter Olympics\), China \(Hohhot\), China \(Hong Kong\), Singapore \(Singapore\), Australia \(Sydney\), US \(Silicon Valley\), and Japan \(Tokyo\). This service will be available in more regions soon.

## \(Recommended\) Prepare an AccessKey pair for a RAM user

Resource Access Management \(RAM\) is a service provided by Alibaba Cloud. It allows you to create and manage multiple identities under an Alibaba Cloud account and then grant diverse permissions to a single identity or a group of identities. In this way, you can authorize different identities to access different Alibaba Cloud resources.

An AccessKey pair is required when you activate a backup client. The AccessKey pair is an identity credential. If an AccessKey pair of your Alibaba Cloud account is used, all cloud resources that belong to the account are exposed to risks. Therefore, we recommend that you use an AccessKey pair of a RAM user to activate backup clients. Before you back up data, make sure that a RAM user is created and an AccessKey pair is created for the RAM user. For more information, see [Create a RAM user](/intl.en-US/RAM User Management/Create a RAM user.md) and [Create an AccessKey pair for a RAM user](/intl.en-US/Security Settings/AccessKey pairs/Create an AccessKey pair for a RAM user.md).

## Register a gateway

To register a gateway, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **CSG Backup**.

3.  In the top navigation bar, select the region where the gateway resides.

4.  In the upper-right corner, click **Register Storage Gateway**.

5.  In the Register Storage Gateway pane, set the parameters. The following table describes the parameters.

    |Parameter or section|Description|
    |--------------------|-----------|
    |Vault Name|The backup vault where you want to store the backup data. A backup vault is a repository that HBR uses to store backup data. You can use a single vault to store backup data that is received from multiple backup clients. Backup vaults reside in different regions. You can select or create only a backup vault in the current region.     -   If you have created backup vaults, click **Select Vault**, and select a backup vault from the **Vault Name** drop-down list.
    -   If you have not created backup vaults, click **Create Vault** and specify the **Vault Name** field. The vault name must be 1 to 64 characters in length. |
    |Gateway Cluster|The cluster where the gateway resides.|
    |Use HTTPS|Specifies whether to use HTTPS for encrypted data transmission. Note that HTTPS compromises the performance of data transmission. Data that is stored in the backup vault is encrypted, regardless of the setting of this switch. If you modify the setting of this parameter, the modification takes effect on the next migration or restore job.|
    |Gateways|The gateways whose shares you want to back up. **Note:** You can use HBR to back up standard and enhanced CSG file gateways. |

6.  Click **Create**. HBR then installs a backup client on the ECS instance that hosts each selected gateway.


## What to do next

On the Storage Gateways tab, you can perform the following operations on a gateway.

|Operation|Description|
|---------|-----------|
|Check the installation status of the backup client|If the backup client is installed, the client status is Activated. If the client status is Installation Failed, it indicates that the installation of a backup client fails. Follow the instructions in the error message to troubleshoot the error. After the error is fixed, choose **More** \> **Install Client** in the Actions column. |
|Uninstall the backup client|Choose **More** \> **Uninstall Client** in the Actions column.|
|Delete the backup client|To uninstall the backup client and remove the gateway, choose **More** \> **Remove** in the Actions column. **Note:** Before you delete a backup client, make sure that the client has no running or completed backup jobs. |

