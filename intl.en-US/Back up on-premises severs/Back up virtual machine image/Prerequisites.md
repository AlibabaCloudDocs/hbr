# Prerequisites {#concept_g5d_24c_ggb .concept}

Hybrid Backup Recovery \(HBR\) allows you to back up the images of local VMware vSphere virtual machines and restore these images as needed. The following prerequisites are required before you perform a backup job.

## RAM users and AccessKeys {#section_rth_lhc_ggb .section}

Resource Access Management \(RAM\) enables you to manage user access to Alibaba Cloud resources. You can create and manage multiple RAM users with a single Alibaba Cloud account. You can grant different permissions for each RAM user. This allows each RAM user to have different access permissions to Alibaba Cloud resources.

An AccessKey is required when you activate a backup client. As the leak of an Alibaba Cloud account's AccessKey exposes cloud resources to security risks, we recommend that you use the AccessKey of a RAM user to perform the activation. Before performing a backup job, ensure that you have [Created a RAM user](../../../../intl.en-US/User Guide/RAM users/Create a RAM user.md#) and [Created an access key for a RAM user](../../../../intl.en-US/User Guide/Security settings/Access keys/Create an access key for a RAM user.md#).

## Create a client {#section_cdt_54c_ggb .section}

You can use virtual machine clients to perform backup and restore jobs. You can perform the following steps to configure a backup client and download the backup client to a server where vSphere Client is installed:

1.  On the server where vSphere Client is installed, log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **On-Premises Backup** \> **VM Client**.
3.  In the upper-right corner of the page, click **Create Client**.
4.  In the Create Client dialog box, configure the required settings and click **Create**. Settings are described as follows.

    |Name|Description|
    |:---|:----------|
    |Backup Vault Name|A backup vault is an HBR cloud warehouse used to store backup data on the cloud. Backup data from multiple clients can be stored in the same vault.     -   One or more backup vaults available

You can select a backup vault on the drop-down list.

    -   No backup vault available

Click **Create Vault**. Enter the **Backup Vault Name** and **Vault Description** to create a new backup vault. The vault name must be a maximum of 32 characters in length.

 |
    |Client Name|The name of the backup client. The client name must be a maximum of 32 characters in length.|
    |Software Platform|vSphere is selected by default.|
    |Network Type|     -   Virtual Private Cloud \(VPC\): Select this option when the virtual machine to be backed up is located in a VPC and in the same region where the backup vault is located.
    -   Public Network: Select this option when VPCs are not applicable.
 |

5.  Click **Download Client** and **Download Certificate**.

    **Note:** You can install a client to connect a virtual machine to Hybrid Backup Recovery \(HBR\) and use the certificate to activate the client. You can also go to the File Client page and download a client at any time.


## Install a client {#section_ggt_jb2_qfb .section}

After downloading a client and certificate, you need to install the client. After the client is installed, you can use the client to perform backup and restore jobs. You can perform the following steps to install a client:

1.  Log on to the vSphere Web Client.

    **Note:** HBR only supports vCenter Server 5.5, 6.0, and 6.5.

2.  In the left-side navigation pane, right-click the virtual machine that you need to deploy an OVF template and select **Deploy OVF Template**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83063/156473008235163_en-US.png)

3.  In the Deploy OVF Template dialog box, select **Local File**. Click **Browse** to select a downloaded client file, and then click **Next**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83063/156473008235164_en-US.png)

4.  Enter the name of the OVF template, select a location you need to deploy the OVF template, and then click **Next**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83063/156473008335165_en-US.png)

5.  Select a location where you need to run the deployed template, and then click **Next**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83063/156473008335166_en-US.png)

6.  Verify the details of the template, and click **Next**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83063/156473008335167_en-US.png)

7.  Select the required virtual disk format, select a datastore to store the deployed OVF template, and then click **Next**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83063/156473008335168_en-US.png)

8.  Select a source network, map the network to a destination network, and click **Next**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83063/156473008435169_en-US.png)

9.  Customize the deployment properties for the software solution, and click **Next**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83063/156473008435170_en-US.png)

10. View the configuration details, and click **Finish**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83063/156473008435171_en-US.png)

11. On the Recent Tasks page, you can view the progress of the deployment task. This process may take a few minutes.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83063/156473008535172_en-US.png)

12. After the OVF template is deployed, turn on the virtual machine that is deployed by using the OVF template.
13. Open a browser and enter `https://hostname:8443` in the address bar.

    **Note:** The `hostname` is the IP address of the virtual machine that is deployed by using the OVF template.

14. In the Activate Gateway dialog box, configure the required settings and click **Register** to log on to the Hybrid Backup Gateway console. Settings are described in the following table.

    |Name|Description|
    |:---|:----------|
    |AccessKey ID and AccessKey Secret|Download the AccessKey ID and AccessKey Secret of the Alibaba Cloud account where the Hybrid Backup Recovery \(HBR\) service is activated.|
    |Password|The logon password of the client. The password must be a minimum of six characters in length.|
    |Certificate|The certificate you have downloaded from the HBR console. The validity period of each certificate is two days. You must download a new certificate to register a client when the certificate in use expires.|


## \(Optional\) Create a backup plan and backup policy {#section_xjh_4v1_rfb .section}

Before you perform a backup job, we recommend that you schedule the backup time and interval of the backup job based on the business requirements.

-   If no regular backup plan exists, you can skip this step.
-   If you have a regular backup plan, you can perform the following steps to create a backup policy and specify the first backup time and backup interval. Proceed as follows:

1.  Log on to the Hybrid Backup Gateway console, in the top navigation pane, select **Backup Policies**, and click **Create Backup Policy**.
2.  Enter the Policy Name, and specify the Effective Time and Backup Interval. For example, if you set the backup interval to one day, a backup job is run at the specified time every day.
3.  Click **Submit**.

