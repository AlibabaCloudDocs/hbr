# Preparations {#task_473648 .task}

You can use HBR to back up CSG instances and restore them when necessary. This topic describes the preparations that you need to make before backing up data.

## Activate a RAM user {#section_2im_sbo_df8 .section}

Resource Access Management \(RAM\) is an Alibaba Cloud service that helps you manage user identities and access to your cloud resources. You can create and manage multiple RAM users within a single Alibaba Cloud account. You can grant different permissions to each RAM user, so that RAM users have different access permissions on Alibaba Cloud resources. Make sure that you have [Created a RAM user](../../../../intl.en-US/User Guide/RAM users/Create a RAM user.md#) and [Created an access key for a RAM user](../../../../intl.en-US/User Guide/Security settings/Access keys/Create an access key for a RAM user.md#) before backing up data.

## Register a CSG instance {#section_ma1_77o_cec .section}

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  Select the region of the CSG instance to be backed up.
3.  In the left-side navigation pane, click **Storage Gateway Backup**.
4.  On the Storage Gateway Backup page, click **Register Cloud Gateway** in the upper-right corner.
5.  In the Register Cloud Gateway dialog box that appears, set the parameters as instructed in the following table.

    |Parameter|Description|
    |---------|-----------|
    |Backup Vault Name|Specify the backup vault. A backup vault is a repository used by HBR to store backup data on the cloud. You can back up data from multiple clients to the same vault.     -   If you have created backup vaults:

Click Select Vault and select a vault from the drop-down list.

    -   If you have not created any backup vaults:

Click Create Vault, and enter the vault name and description to create a vault. The vault name must not exceed 64 bytes in length.

 |
    |Cloud Gateway Cluster|Select the gateway cluster of the CSG instance to be backed up.|
    |Please select a cloud gateway to backup|Select the CSG instance to be backed up. **Note:** The Storage Gateway Backup service can only back up standard or enhanced file gateways on Alibaba Cloud.

 |

6.  After the configuration is completed, click **Create**. The system automatically installs the backup client for the CSG instance on the corresponding ECS instance.

## Manage clients of CSG instances {#section_9p9_kli_vhg .section}

On the Storage Gateway Backup page, click the Cloud Gateway Instance tab, and then locate the target CSG instance.

|Operation|Procedure|
|---------|---------|
|To check the installation status of a client|Make sure that the client status appears as Activated after the client is installed. If the status is Failed, follow the instructions provided in the error message for troubleshooting. After the error is rectified, choose **More** \> **Re-install** in the Actions column.

 |
|To uninstall a client|Choose **More** \> **Uninstall Client** in the Actions column.|
|To delete a client and the corresponding CSG instance|Choose **More** \> **Delete** in the Actions column. **Note:** Before deleting a client, make sure that the client has no backup job in the Running or Completed status.

 |

