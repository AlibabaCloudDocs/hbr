# Before you begin

You can use Hybrid Backup Recovery \(HBR\) to archive the files of an on-premises NAS file system. You can search for and retrieve these files as needed. This topic describes what you must prepare before you archive data.

## Prepare an AccessKey pair for a RAM user \(Recommended\)

Resource Access Management \(RAM\) is an Alibaba Cloud service that allows you to manage user identities and control access to resources. RAM allows you to create and manage multiple identities within an Alibaba Cloud account, and grant diverse permissions to a single identity or a group of identities. This way, you can authorize different identities to access different Alibaba Cloud resources.

For more information about how to create RAM users, see [Create a RAM user](/intl.en-US/RAM User Management/Basic operations/Create a RAM user.md).

For more information about how to create an AccessKey pair for a RAM user, see [Create an AccessKey pair for a RAM user](/intl.en-US/Security Settings/AccessKey pairs/Create an AccessKey pair for a RAM user.md).

## Download and activate an HBR client for Linux

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Archive**.

3.  In the upper-right corner of the page, click **Add Client**.

4.  In the Add Client panel, select an activation method.

    Record the activation code, which is used to install and activate the client.

5.  Download and decompress the HBR client for Linux.

    You can download the installation package of the HBR client for **Linux \(64bit\)** or **Linux \(32bit\)**.

6.  Manually or automatically activate the HBR client for Linux.

    In the following example, `05M72DYX` indicates the dynamic activation code that is obtained from the HBR console.

    -   Manually activate the HBR client for Linux.

        In the path to which the HBR client is decompressed, run the following command to activate the client: ./setup -t local -k 05M72DYX.

    -   Automatically activate the HBR client for Linux.

        Run the following command on the HBR client: /bin/bash -c "$\(curl -fsSL https://a-hbr-resource-shanghai.oss-cn-shanghai.aliyuncs.com/client/install/hbrclient/install-local-hbr-client.sh\)" -- -k 05M72DYX. The client is automatically activated.

        In the preceding command, `https://a-hbr-resource-shanghai.oss-cn-shanghai.aliyuncs.com` indicates the public endpoint of the OSS bucket. The OSS bucket stores the scripts that are used to activate HBR clients.

    Run the following commands to install the nfs tool that is used to back up and restore NAS file systems on the HBR client:

    -   Centos

        ```
        sudo yum install nfs-utils
        ```

    -   Ubuntu

        ```
        sudo apt-get install nfs-common
        ```


## Download and activate an HBR client for Windows

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Archive**.

3.  In the upper-right corner of the page, click **Add Client**.

4.  On the Add Client page, select **Manually Activate**.

    Record the activation code, which is used to install and activate the client.

5.  Download the HBR client for Windows.

    You can download the installation package of the HBR client for **Windows \(64bit\)** or **Windows \(32bit\)**.

6.  Install and activate the HBR client for Windows.

    1.  Double-click the installation package of the HBR client and select a language for installation.

    2.  Select the path in which you want to install the client and click **Next**.

    3.  Select **Local client connecting to Alibaba Cloud**, and then click **Next**.

    4.  Configure the logon identity.

        -   If you want to back up or archive the files from only local paths, select **Local System**.
        -   If you want to back up or archive network shared files, select **This user**. The user must meet the following requirements:
            -   The user has the permissions of the local administrator.
            -   The user has the permissions to log on as a service.

                You can perform the following steps to configure the logon user:

                1.  Open the **Control Panel**. In the window that appears, click **Administrative Tools**.
                2.  Open **Local Security Policy** and choose **Local Policies** \> **User Rights Assignment**.
                3.  Turn on the **Logon as a service** switch. In the dialog box that appears, add a user.
            -   The user has the permissions to access shared files over the network.
    5.  If you want to use a proxy server, enter the address of the proxy server. Click **Next**.

    6.  Enter the activation code that you recorded in Step 4 from the **Activation token** field. Then, click **Next**.

    7.  Click **Install**.

        After the client is installed, the client status is displayed as **Activated** on the Clients tab.


