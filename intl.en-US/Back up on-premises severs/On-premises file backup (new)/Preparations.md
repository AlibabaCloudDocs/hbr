# Preparations

You can use Hybrid Backup Recovery \(HBR\) clients to back up files from an on-premises server or virtual machine \(VM\) and restore the files based on your requirements. This topic describes the preparations that you must make before backup.

## Background information

You can use different HBR clients for backup based on scenarios. Different clients are activated in the following methods:

-   HBR clients for Windows can only be manually activated.
-   HBR clients for Linux can be automatically or manually activated.
-   HBR clients for Backup Appliance can be activated only by using Backup Appliance.

## \(Recommended\) Prepare an AccessKey pair for a RAM user

Resource Access Management \(RAM\) is a service provided by Alibaba Cloud. It allows you to create and manage multiple identities under an Alibaba Cloud account and then grant diverse permissions to a single identity or a group of identities. This way, you can authorize different identities to access different Alibaba Cloud resources.

An AccessKey pair is required when you activate an HBR client. The AccessKey pair is an identity credential. If an AccessKey pair of your Alibaba Cloud account is leaked, all cloud resources that belong to the account are exposed to risks. Therefore, we recommend that you use an AccessKey pair of a RAM user to activate HBR clients.

For more information about how to create RAM users, see [Create a RAM user](/intl.en-US/RAM User Management/Create a RAM user.md).

For more information about how to create an AccessKey pair for a RAM user, see [Create an AccessKey pair for a RAM user](/intl.en-US/Security Settings/AccessKey pairs/Create an AccessKey pair for a RAM user.md).

## Download and activate an HBR client for Windows

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **On-Premises Backup**.

3.  Click **Backup Wizard** in the upper-right corner.

4.  In the **Select Client** step in the Create Backup Plan panel, click **See how to install and activate the client**.

    Record the activation code for client installation and activation.

5.  Download the HBR client for Windows.

    You can download the installation package of HBR client for **Windows \(64bit\)** or **Windows \(32bit\)**.

6.  Install and activate the HBR client for Windows.

    1.  Double-click the installation package of HBR client and select a language for installation.

    2.  Select the path to which you want to install the client and click **Next**.

    3.  Select **Local client connecting to Alibaba Cloud**, and then click **Next**.

    4.  Enter the activation code recorded in Step 4 in the **Activation token** field. Then, click **Next**.

    5.  Click **Install**.

        After the client is installed, the client status displayed on the Create Backup Plan panel is **Activated**.


## Download and activate an HBR client for Linux

1.  Download and decompress the HBR client for Linux.

    You can download the installation package of HBR client for **Linux \(64bit\)** or **Linux \(32bit\)**.

2.  Manually or automatically activate the HBR client for Linux.

    In the following example, `05M72DYX` indicates the dynamic activation code that is obtained from the HBR console.

    -   Manually activate the HBR client for Linux

        In the path to which the HBR client is decompressed, run the following command to activate the client: ./setup -t local -k 05M72DYX.

    -   Automatically activate the HBR client for Linux

        Run the following command on the HBR client: /bin/bash -c "$\(curl -fsSL https://a-hbr-resource-shanghai.oss-cn-shanghai.aliyuncs.com/client/install/hbrclient/install-local-hbr-client.sh\)" -- -k 05M72DYX. The client is automatically activated.

        In the preceding command, `https://a-hbr-resource-shanghai.oss-cn-shanghai.aliyuncs.com` indicates the public endpoint of the OSS bucket that stores the scripts used to activate HBR clients.


## Activate the HBR client on a Backup Appliance equipment

An HBR client is installed and configured on each Backup Appliance equipment before delivery. You can activate the HBR client without additional configurations. If you have problems, submit a ticket.

Perform the following steps to activate the HBR client on a Backup Appliance equipment:

1.  Open a browser, and enter `http://hostname:8011` in the address bar.

    `hostname` indicates the IP address of the Backup Appliance equipment.

2.  On the Register page, set the parameters described in the following table and click **Register**.

    The following table describes the parameters that you can set in the basic settings.

    |Parameter|Description|
    |---------|-----------|
    |Activation code|The ID used to access Alibaba Cloud resources.You can perform the following steps to obtain the activation code:

    1.  Click **Backup Wizard** in the upper-right corner.
    2.  In the **Select Client** step in the Create Backup Plan panel, click **See how to install and activate the client**.
    3.  In the **Client Active Method** field in the **Add Client** panel, click **Appliance Active** to obtain the activation code. |
    |Deployment Environment|Select **Alibaba Cloud** or **Apsara Stack**|
    |Backup Data Network|You can select **Public Network** or **Intranet \(Classic or VPC\)**.**Note:** If you select a VPC network, ensure the ECS instance on which the HBR client is installed is running in VPC and is in the same region as the backup vault. |


