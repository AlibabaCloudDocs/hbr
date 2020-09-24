# Install an HBR backup client for ECS

Before you can back up files from an Elastic Compute Service \(ECS\) instance and restore these files, you must install a backup client on the ECS instance in the Hybrid Backup Recovery \(HBR\) console.

## Background information

You can use the wizard in the HBR console to install backup clients on several ECS instances in the same region. You can also use a template to install backup clients on a large number of or all of the ECS instances in the same region.

If the version of a backup client for ECS is outdated, you can upgrade the client to the latest version. If the activation or upgrade of a backup client for ECS fails, you must uninstall and reinstall the client. If you no longer need the backup data in a backup client for ECS, you can delete the client.

## Install backup clients on several ECS instances

To install backup clients on several ECS instances in the same region, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS File Backup**.

3.  In the top navigation bar, select the region where the ECS instances reside.

4.  In the upper-right corner of the ECS Instances tab, click **Add ECS Instance**.

5.  In the Add ECS Instance pane, set the parameters. The following table describes the parameters.

    |Parameter or section|Description|
    |--------------------|-----------|
    |Backup Vault|The backup vault where you want to store the backup data. A backup vault is a repository that HBR uses to store backup data. You can use a single vault to store backup data that is received from multiple backup clients. Backup vaults reside in different regions. You can select or create a backup vault only in the current region.     -   If you have created backup vaults, click **Select Vault**, and select a backup vault from the **Vault Name** drop-down list.
    -   If you have not created backup vaults, click **Create Vault** and specify the **Vault Name** field. The name must be 1 to 64 characters in length. |
    |Use HTTPS|Specifies whether to use HTTPS for encrypted data transmission. Note that HTTPS compromises the performance of data transmission. Data that is stored in the backup vault is encrypted, regardless of the setting of this switch. If you modify the setting of this parameter, the modification takes effect on the next migration or restore job.|
    |ECS instances|In this section, select the ECS instances on which you want to install backup clients. To search for ECS instances, perform the following steps: Select **Instance ID**, **Instance Name**, **VPC ID**, **Private IP \(VPC\)**, or **Internal IP \(Classic\)** from the drop-down list next to the search box. Enter a partial or entire keyword in the search box. **Note:** If you select an ECS instance in the classic network, you must provide an AccessKey pair that is used to access the ECS instance. We recommend that you use the AccessKey pair of a RAM user. |

6.  Click **Create**. HBR then installs a backup client on each selected ECS instance.


## Install backup clients on a large number of ECS instances

To install backup clients on a large number of ECS instances in the same region, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS File Backup**.

3.  In the top navigation bar, select the region where the ECS instances reside.

4.  In the upper-right corner of the ECS Instances tab, choose **Batch Actions** \> **Add ECS Instances**.

5.  In the Add ECS Instances pane, enter a backup vault name in the **Vault Name** field. The name must be 1 to 64 characters in length.

6.  Optional. Select Private IP \(VPC\) or Internal IP \(Classic\). Specify the private or internal IP addresses of the ECS instances on which you want to install backup clients.

    **Note:**

    -   By default, the template lists the ECS instances in the region. On these ECS instances, the Cloud Assistant client is installed but the backup client is not installed.
    -   If you specify ECS instance IP addresses, the template lists only the specified ECS instances.
    -   Separate each IP address with a comma \(,\).
7.  Click **Download Template**.

8.  Open the template, specify the **Access Key ID** and **Access Key Secret** fields for ECS instances in the classic network, and then save the template. You do not need to specify AccessKey pairs for VPC ECS instances.

    **Note:**

    -   If you attempt to install backup clients on more than 20 ECS instances by using a template, HBR automatically creates new backup vaults to support the backup clients.
    -   For more information about how to create an AccessKey pair, see [View the basic information about AccessKey pairs](/intl.en-US/Security Settings/AccessKey pairs/View the basic information about AccessKey pairs.md).
    -   If you do not need to install a backup client on an ECS instance, delete the row that corresponds to the ECS instance from the template.
    -   We recommend that you do not change the values in the **Instance Id**, **Instance Name**, and **Network Type** columns.
    -   To ensure account security, we recommend that you delete the local template after the template is uploaded to HBR.
9.  Click **Upload Template**.

    After the template is uploaded, the number of VPC ECS instances and the number of classic network ECS instances are displayed.


## Manage a backup client

On the **ECS Instances** tab of the ECS File Backup page, find the ECS instance that hosts the backup client. To search for an ECS instance, select Private IP \(VPC\) or Internal IP \(Classic\) from the drop-down list next to the search box, enter the IP address of the ECS instance, and then click the Search icon.

You can view the installation status of the backup client. After the backup client is installed, you can uninstall, delete, or upgrade the backup client.

|Operation|Description|
|:--------|:----------|
|Check the installation status of the backup client|If the backup client is installed, the client status is Activated. If the client status is Installation Failed, it indicates that the installation of a backup client fails. Follow the instructions in the error message to troubleshoot the error. After the error is fixed, choose **More** \> **Install Client** in the **Actions** column.|
|Uninstall the backup client|Choose **More** \> **Uninstall Client** in the **Actions** column.|
|Delete the backup client|To uninstall the backup client from the ECS instance and remove the ECS instance, choose **More** \> **Remove** in the **Actions** column. **Note:** After you delete a backup client, the existing backup data is also deleted and running backup and restore jobs fails. Before you delete a backup client, make sure that the backup data in the client is no longer needed and the client has no running backup or restore jobs. |
|Upgrade the backup client to the latest version|Click **Upgrade** in the Client Type column.|

