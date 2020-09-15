# Upgrade, uninstall, or delete an HBR client for ECS backup

After an SAP HANA instance is registered, you can view the installation status of the HBR client for Elastic Compute Service \(ECS\) backup on each node of the SAP HANA instance. Make sure that an HBR client is installed on the node that you want to back up. After the HBR client is installed, you can upgrade, reinstall, uninstall, or delete the HBR client based on your business requirements.

If the version of an HBR client for ECS backup is outdated, you can upgrade the HBR client to the latest version. If the activation or upgrade of the HBR client fails, you must uninstall and reinstall the HBR client. If you no longer need the backup data in the HBR client, you can delete the HBR client.

1.  Make sure that at least one SAP HANA instance is registered. On the ECS Application Backup page, click **SAP HANA**.

2.  Find the SAP HANA instance, and choose **More** \> **View Details** in the Actions column.

3.  On the **SAP HANA Nodes** tab of the SAP HANA Instance Details page, view the installation status of the HBR client for ECS backup on each node. If the status is **Activated**, it indicates that the HBR client is installed. You can perform the following operations on the HBR client:

    -   Upgrade the HBR client

        To upgrade the HBR client on the node, find the node and click **Upgrade** in the Client Type column.

        During the upgrade, you must disable the backup feature of SAP HANA. For more information, see [SAP Note 2009486](https://launchpad.support.sap.com/#/notes/2009486).

    -   Reinstall the HBR client

        To reinstall the HBR client on the node, find the node and choose **More** \> **Uninstall Client** in the Actions column. After the HBR client is uninstalled, choose **More** \> **Reinstall Client** in the Actions column.

    -   Uninstall the HBR client

        To uninstall the HBR backup client from the node, choose **More** \> **Uninstall Client** in the Actions column.

    -   Delete the HBR client

        To uninstall the HBR client from the node and remove the node from the instance, find the node and click **Delete** in the Actions column.

        **Note:** After you delete an HBR client for ECS backup, the backup data is also deleted and running backup and restore jobs fail. Before you delete the HBR client, make sure that the backup data in the HBR client is no longer needed and the HBR client has no running backup and restore jobs.

        To remove the corresponding SAP HANA instance after the HBR client is deleted, perform the following steps:

        1.  On the ECS Application Backup page, click **SAP HANA**.
        2.  Find the SAP HANA instance, and choose **More** \> **Delete** in the Actions column.

            **Note:** After you delete an SAP HANA instance, the backup data is also deleted and running backup and restore jobs fail. Before you delete the SAP HANA instance, make sure that the data in the HBR clients of the instance is no longer needed and the HBR clients of the instance have no running backup and restore jobs. To remove the SAP HANA instance, you must enter the SID of the instance. The SID is three characters in length and starts with letters. For more information, see [How to find sid user and instance number of HANA db?](https://answers.sap.com/questions/555192/how-to-find-sid-user-and-instance-number-of-hana-d.html)


