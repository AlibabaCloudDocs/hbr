# Prerequisites {#concept_qnt_cz5_fgb .concept}

You can use Hybrid Backup Recovery \(HBR\) to back up files from ECS instances and restore these files as required. The following prerequisites are required before you back up data.

**Note:** 

-   To achieve the best backup performance, we recommend that the configurations of a host where a backup client is running meet the following requirements. The host uses a 64-bit CPU with more than two cores and more than 8 GB available memory.
-   The size of data that a host can back up is determined by available memory resources. For a host with 4 GB of available memory, the maximum number of files that you can back up on the host is one million and the total size of data is 8 TB.
-   You can only use HBR to back up data from ECS instances that are located in one of the following regions: China \(Hangzhou\), China \(Shanghai\), China \(Beijing\), and China \(Shenzhen\).

## Authorize roles {#section_pts_5z5_fgb .section}

When using Hybrid Backup Recovery \(HBR\) to back up files from ECS instances, you must authorize two roles: AliyunHBRDefaultRole and AliyunECSAccessingHBRRole. After the authorization, HBR and ECS are accessible by each other. Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  Choose **ECS Backup** \> **ECS File Backup**.
3.  Authorization pages appear one by one, which require you to confirm the authorization of these roles.

## Cloud Assistant {#section_qb5_wz5_fgb .section}

-   An ECS backup client must work with Cloud Assistant. By default, Cloud Assistant clients are installed on ECS instances that are created after Dec 1, 2017. When ECS instances from which you need to back up data are purchased before Dec 1, 2017, you must manually [install a Cloud Assistant client](../../../../intl.en-US/Deployment & Maintenance/Cloud assistant/Configure the cloud assistant client.md).
-   When ECS instances that are located in a classic network have Cloud Assistant clients installed, you need to use the following steps to configure a Cloud Assistant client.
    -   For an ECS instance running Windows
        1.  Connect to the ECS instance. In the C:\\ProgramData\\aliyun\\assist\\ folder, create a file named `region-id` and enter the value of the corresponding `region id` parameter based on the region where the ECS instance is located. For example, for an ECS instance that is located in the China \(Hangzhou\) region, you need to enter `cn-hangzhou`.

            ``` {#codeblock_5ry_xfx_xpr}
            echo cn-hangzhou >C:\ProgramData\aliyun\assist\region-id
            ```

            Regions and corresponding region-ids are listed in the following table.

            |Region|region-id|
            |:-----|:--------|
            |China \(Hangzhou\)|cn-hangzhou|
            |China \(Shanghai\)|cn-shanghai|
            |China \(Beijing\)|cn-beijing|
            |China \(Shenzhen\)|cn-shenzhen|

        2.  Restart the AliyunService service by using Task Manager.
    -   For an ECS instance running Linux
        1.  Connect to the ECS instance. In the /usr/local/share/aliyun-assist/ folder, create a file named `region-id` and enter value the corresponding `region id` parameter based on the region where the ECS instance is located. For example, for an ECS instance that is located in the China \(Hangzhou\) region, you need to enter `cn-hangzhou`.

            ``` {#codeblock_tec_648_m11}
            echo cn-hangzhou >/usr/local/share/aliyun-assist/region-id
            ```

            Regions and corresponding region IDs are listed in the following table.

            |Region|region-id|
            |:-----|:--------|
            |China \(Hangzhou\)|cn-hangzhou|
            |China \(Shanghai\)|cn-shanghai|
            |China \(Beijing\)|cn-beijing|
            |China \(Shenzhen\)|cn-shenzhen|

        2.  Run the `chkconfig agentwatch off` command and the `chkconfig agentwatch on` command. Alternatively, you can run the `systemctl restart agentwatch` command to restart the Cloud Assistant client.

            **Note:** If the issue persists after you restart the Cloud Assistant client, you need to restart the Cloud Assistant client by using the preceding commands.


## Install an ECS backup client {#section_vb1_zz5_fgb .section}

You can use an ECS backup client to back up files from an ECS instance and restore these files. You can use one of the following methods to install ECS backup clients.

-   **Install ECS backup clients by selecting ECS instances**: installs backup clients for selected ECS instances.
-   **Install ECS backup clients by using a template**: installs backup clients for ECS instances by using a template.

 **Install ECS backup clients by selecting ECS instances** 

Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  Select a region where ECS instances that you need to back up are located.
3.  In the left-side navigation pane, choose **ECS Backup** \> **ECS File Backup**.
4.  In the upper-right corner, click **Add ECS Instance**.
5.  In the Add ECS Instance dialog box, enter the **Backup Vault Name**. On the drop-down list, select an existing backup vault. If no backup vault exists, click **Create Vault**, and enter the **Vault Name** and **Vault Description** to create a new vault. A vault name must be less than 64 characters in length.

    **Note:** Backup vaults are HBR cloud storage repositories that you can use to store backups. You can back up data from multiple ECS instances to the same vault. Backup vaults are located in different regions. You can only select or create backup vaults in the current region.

6.  Select one or more ECS instances on which you need to install a backup client. On the left side of Search, you can also select Instance ID, Instance Name, VPC ID, Private IP \(VPC\), and Internal IP \(Classic\). Then, enter a full name or keyword to search for one or more instances.

    **Note:** 

    -   You can only select or search for ECS instances that are located in the current region.
    -   If you select ECS instances that are located in a classic network, you must enter the [AccessKey ID and AccessKey Secret](../../../../intl.en-US/FAQ/Common issues/Obtain an AccessKey for RAM users.md#).
7.  After the configurations are complete, click **Create** and then backup clients will be installed on the selected ECS instances.

 **Install ECS backup clients from a template** 

Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  Select a region where ECS instances that you need to back up are located.

    **Note:** After selecting a region, you can only install multiple backup clients for ECS instances that are located in the region.

3.  In the left-side navigation pane, choose **ECS Backup** \> **ECS File Backup**.
4.  In the upper-left corner of the page, choose **Batch Operation** \> **Batch Add ECS Instances**.
5.  In the Batch Add ECS Instance dialog box, enter the **Backup Vault Name** to create a new backup vault, and then enter the Vault Description. The vault name must be less than 64 characters in length.

    **Note:** Backup vaults are located in different regions. You can only select or create backup vaults in the current region.

6.  \(Optional\) You can specify the Private IP \(VPC\) or Internal IP \(Classic\) of ECS instances on which you need to install backup clients.

    **Note:** 

    -   After you specify one or more IP addresses, only ECS instances that correspond to the IP addresses are displayed in a template.
    -   If no IP address is specified, all ECS instances that are located in the current region are displayed in a template.
    -   Separate multiple IP addresses with commas \(,\).
7.  Click **Download Template**.
8.  Open the template, enter the **AccessKey ID** and **AccessKey Secret**, and then save the template. You do not need to enter the AccessKey ID or AccessKey Secret for an ECS instance when the network type is VPC.

    **Note:** 

    -   Only ECS instances that have Cloud Assistant clients and backup clients installed are displayed in a template.
    -   If you add more than 20 ECS instances at a time, new vaults are created to host additional ECS instances.
    -   If you do not need to install a backup client on an ECS instance, you can delete the row where the ECS instance is located.
    -   We recommend that you do not change the column headers, such as **Instance ID**, **Instance Name**, and **Network Type**.
    -   We recommend that you delete the local template after uploading the template to ensure account security.
9.  Click **Upload Template** to upload the template.

After a template is uploaded, the number of each type of specified ECS instances and the total number of ECS instances are displayed in the Batch Add ECS instance dialog box.

## Manage backup clients {#section_hz5_kbv_fgb .section}

On the ECS File Backup page, select **ECS Instance** tab and locate the target ECS instance. For a large number of ECS instances, in the Search field that is located in the upper-right corner of the page, enter the Private IP \(VPC\) or Internal IP \(Classic\) to search for the target instance.

After locating the target ECS instance, you can perform the following actions.

|Action|Description|
|:-----|:----------|
|View the installation status of a backup client|If a client installation is successful, the status is displayed as Activated. If the status is Failed, follow instructions provided in the error message, click the More icon next to the ECS instance, and select **Re-install**.|
|Uninstall a client|In the Actions column, choose **More** \> **Uninstall Client**.|
|Delete a client|If you need to delete an ECS instance from a list of ECS instances and uninstall the backup client from the ECS instance, choose **More** \> **Delete** next to the instance. **Note:** You must ensure that no running or completed backup job exists on a backup client before deleting this client.

 |
|Update a backup client|Locate the target ECS instance, click **Update** to update the client to the latest version.|

## Subsequent operations {#section_irf_dlg_mgb .section}

[Back up files from an ECS instance](intl.en-US/Back up ECS/Back up files in ECS/Back up files from an ECS instance.md)

