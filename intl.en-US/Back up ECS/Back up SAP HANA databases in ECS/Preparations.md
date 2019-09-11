# Preparations {#concept_yml_bpj_ggb .concept}

You can use Hybrid Backup Recovery \(HBR\) to back up SAP HANA databases deployed on Alibaba Cloud Elastic Compute Service \(ECS\) instances and restore these databases as required. This topic describes the preparations that you need to make before backing up data.

## Authorize roles {#section_pts_5z5_fgb .section}

Before using HBR to back up files from ECS instances, you must authorize two roles AliyunHBRDefaultRole and AliyunECSAccessingHBRRole to access your cloud resources. The procedure is as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **ECS Backup** \> **ECS File Backup**. Authorization dialog boxes appear one by one. Follow instructions to authorize the two roles to access your cloud resources.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83216/156818807560226_en-US.png)


## Install Cloud Assistant {#section_qb5_wz5_fgb .section}

An ECS backup client must work with Cloud Assistant. By default, a Cloud Assistant client is installed on ECS instances that are created after December 1, 2017. To back up files from ECS instances that you bought before December 1, 2017, you must [install a Cloud Assistant client](../../../../intl.en-US/Deployment & Maintenance/Cloud assistant/Configure the cloud assistant client.md).

## Register an SAP HANA instance {#section_mw5_npj_ggb .section}

When you register an SAP HANA instance, you need to configure the connection information about the SAP HANA instance. After the SAP HANA instance is registered, an ECS backup client is installed on each node of the SAP HANA instance. The procedure is as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  Select a region where ECS instances that you need to back up are located.
3.  In the left-side navigation pane, choose **ECS Backup** \> **SAP HANA Backup**.
4.  In the upper-right corner, click **Register HANA Instance**.
5.  In the Register HANA Instance dialog box, set the parameters as instructed in the following table.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83216/156818807560227_en-US.jpg)

    |Parameter|Description|
    |:--------|:----------|
    |Backup Vault Name|Specify the backup vault. A backup vault is a repository used by HBR to store backup data on the cloud. You can back up data from multiple clients to the same vault.     -   If you have created backup vaults:

Click Select Existing Vault and select a vault from the drop-down list.

    -   If you have not created any backup vaults:

Click **Create New Vault**, and then set **Backup Vault Name** and **Vault Description** to create a vault. The vault name cannot exceed 64 bytes in length.

 |
    |Instance Alias|Enter an alias for the SAP HANA instance to be backed up.|
    |Host Address|Enter the IP address of the SAP HANA primary node.|
    |Instance Number|Enter the instance number that is specified when you install SAP HANA.|
    |Username|Enter the username used to log on to the SAP HANA instance.|
    |Password|Enter the password used to log on to the SAP HANA instance.|
    |SSL Connection|Specify whether to use Secure Sockets Layer \(SSL\) to connect to SAP HANA databases.|
    |Verify SSL Certification|Specify whether to verify SSL certification for the database server if you enable the SSL connection.|

6.  Click **Next**.
7.  Select all nodes of the SAP HANA instance to be registered, so that HBR can install an ECS backup client on these nodes. In the drop-down list on the left of the search box, select Instance ID, Instance Name, or VPC ID as the keyword. Enter a complete or partial ID or name in the search box to search for ECS instances.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83216/156818807560229_en-US.jpg)

8.  After the configuration is completed, click **Create**. HBR automatically installs an ECS backup client on the selected ECS instances.

**Note:** After the SAP HANA instance is registered, you can click the **SAP HANA Instance** tab on the SAP HANA Backup page. On this tab, you can view the registration information and status of the registered SAP HANA instance. In the right-side Actions column, you can choose **More** \> **Edit Instance** to modify the SAP HANA instance.

## View and manage nodes {#section_ny2_lfr_ggb .section}

After the SAP HANA instance is registered, you can view the installation status of the ECS backup client on each node of the SAP HANA instance. Ensure that an ECS backup client is installed on all nodes to be backed up. You can also enable the node verification feature to install an ECS backup client on newly added nodes.

-   Check the client installation status

    To check the installation status of the ECS backup client on a node, perform the following operations:

    1.  Ensure that the SAP HANA instance is registered. On the SAP HANA Backup page, click the **SAP HANA Instance** tab.
    2.  In the Actions column, choose **More** \> **Manage Node** for the target SAP HANA instance.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83216/156818807560249_en-US.jpg)

    3.  Click the **Node Info** tab to view the installation status of the ECS backup client on nodes. If the ECS backup client is installed, the node status is Activated. In this case, you can also perform the following operations:
        -   Upgrade a backup client

            To upgrade the backup client on a node, click **Upgrade** in the Client Type column for the node.

            **Note:** During the upgrade, you need to disable the SAP HANA database backup feature. For more information, see [SAP Note 2009486](https://launchpad.support.sap.com/#/notes/2009486).

        -   Reinstall a backup client

            If the backup client fails to be installed on a node, choose **More** \> **Re-install** in the right-side Actions column for the node.

        -   Uninstall a backup client

            To uninstall the backup client from a node, choose **More** \> **Uninstall Client** in the right-side Actions column for the node.

        -   Delete a backup client

            To uninstall the backup client from a node and delete the node, click **Delete** in the right-side **Actions** column for the node.

            **Note:** Before deleting a backup client, you need to ensure that the backup client has no backup job in the Running or Completed state.

-   Verify nodes

    When you enable the node verification feature, HBR automatically detects changed nodes in the SAP HANA cluster and ECS instances that no longer belong to the cluster. If a node is added to the cluster, HBR reminds you to install an ECS backup client for the node. If HBR detects an ECS instance that does not belong to the SAP HANA cluster, HBR reminds you to uninstall the ECS backup client from the instance. The procedure is as follows:

    1.  Ensure that the SAP HANA instance is registered. On the SAP HANA Backup page, click the **SAP HANA Instance** tab.
    2.  In the Actions column, choose **More** \> **Manage Node** for the target SAP HANA instance.
    3.  In the upper-right corner of the HANA Instance Info page, click **Verify HANA Node**.
    4.  In the **Verify HANA Node** dialog box, check node information.
    5.  Select nodes for which you need to install or uninstall the ECS backup client.
    6.  Click **Confirm & Execute**.

**Note:** You can also perform the following operations:

-   Add a node

    On the HANA Instance Info page, click **Add HANA Node**, select the ECS instance on which you need to install an ECS backup client, and then add this ECS instance as a node to the SAP HANA cluster.

-   View databases on an SAP HANA instance

    On the HANA Instance Info page, click the **Database** tab. On this tab, you can view the status of all databases on the SAP HANA instance.


## Configure database backup {#section_qxg_dnq_vwh .section}

To improve the performance of SAP HANA database backup, we recommend that you use Backint and set a log backup policy. For more information, see [Configure a backup profile](intl.en-US/Back up ECS/Back up SAP HANA databases in ECS/Configure a backup profile.md) and [Set a log backup policy](intl.en-US/Back up ECS/Back up SAP HANA databases in ECS/Set a log backup policy.md).

**Note:** You can also enable the [backup alerting](intl.en-US/Back up ECS/Back up SAP HANA databases in ECS/Configure the backup alerting feature.md) feature. This feature enables HBR to send your alert contact an alert notification if a backup fails or a client is disconnected from a server.

