# Register an SAP HANA instance

Before using Hybrid Backup Recovery \(HBR\) to back up an SAP HANA instance that is hosted on Elastic Compute Service \(ECS\), you must register the SAP HANA instance in the HBR console.

When you register the SAP HANA instance, you must configure the connection to the SAP HANA instance. After the SAP HANA instance is registered, a backup client for ECS is installed on each ECS instance that hosts the SAP HANA instance.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Application Backup**. On the ECS Application Backup page, click **SAP HANA**.

3.  Select the region where you want to store the backup data of the SAP HANA instance.

4.  In the upper-right corner, click **Register SAP HANA Instance**.

5.  In the Register SAP HANA Instance pane, set the parameters.

    ![HANA](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9246549951/p100391.jpg)

    |Parameter|Description|
    |:--------|:----------|
    |Backup Vault|The backup vault where you want to store the backup data. A backup vault is a repository that HBR uses to store backup data. You can use a single vault to store backup data that is received from multiple backup clients. Backup vaults reside in different regions. You can select or create only a backup vault in the current region.     -   If you have created backup vaults, click **Select Vault**, and select a backup vault from the **Vault Name** drop-down list.
    -   If you have not created backup vaults, click **Create Vault** and specify the **Vault Name** field. The vault name must be 1 to 64 characters in length. |
    |Instance Alias|The alias of the SAP HANA instance. The alias is displayed as the instance name in the HBR console to represent the SAP HANA instance.|
    |Host Address|The private or internal IP address of the host where the primary node of the SAP HANA instance resides.|
    |Instance Number|The instance number of the SAP HANA system.|
    |Username|The name of the user account that is used to access the SAP HANA instance.|
    |Password|The password of the user account.|
    |Use SSL|Specifies whether to connect to the SAP HANA instance over Secure Sockets Layer \(SSL\).|
    |Verify SSL Certificate|Specifies whether to verify SSL certificate of the instance host. This parameter is required if you turn on the Use SSL switch.|

6.  Click **Next**.

7.  In the Install Client step, select Yes or No for **Use HTTPS** and select all ECS instances that host the SAP HANA instance. HBR will install a backup client for each ECS instance. To search for an ECS instance, you can select **Instance ID**, **Instance Name**, or **VPC ID** from the drop-down list next to the search box and enter a keyword in the search box.

    **Note:** You can select whether to use HTTPS for encrypted data transmission from the ECS instances to the backup vault. Note that HTTPS compromises the performance of data transmission. Data that is stored in the backup vault is encrypted, regardless of the setting of this switch. If you modify the setting of this parameter, the modification takes effect on the next migration or restore job.

8.  Click **Create**. HBR then installs a backup client on each selected ECS instance.

    After the SAP HANA instance is registered, you can view the information and status of the SAP HANA instance on the **SAP HANA** tab. You can choose **More** \> **Configure Connection** in the Actions column to modify the instance information.


