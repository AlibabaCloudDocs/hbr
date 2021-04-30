# Preparations

You can use Hybrid Backup Recovery \(HBR\) to archive the files of an on-premises NAS file system. You can search and retrieve these files based on your business requirements. This topic describes what you need to prepare before you archive data.

## Prepare an AccessKey pair for a RAM user \(Recommended\)

Resource Access Management \(RAM\) is an Alibaba Cloud service that allows you to manage user identities and control access to resources. RAM allows you to create and manage multiple identities within an Alibaba Cloud account, and grant diverse permissions to a single identity or a group of identities. In this way, you can authorize different identities to access different Alibaba Cloud resources.

For more information about how to create RAM users, see [Create a RAM user](/intl.en-US/RAM User Management/Create a RAM user.md).

For more information about how to create an AccessKey pair for a RAM user, see [Create an AccessKey pair for a RAM user](/intl.en-US/Security Settings/AccessKey pairs/Create an AccessKey pair for a RAM user.md).

## Download and activate an HBR client

HBR allows you to manually activate HBR clients for Windows or Linux. HBR also provides an automatic method to activate HBR clients for Linux and backup appliance equipment. This topic uses how to install an HBR client for Linux as an example.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Archive**.

3.  In the upper-right corner of the page, click **Add Client**.

4.  In the Add Client panel, select an activation method.

    Record the prompted activation code to install and activate the client.

5.  Download and decompress the HBR client for Linux.

    You can download the installation package of the HBR client for **Linux \(64bit\)** or **Linux \(32bit\)**

6.  Manually or automatically activate the HBR client for Linux.

    In the following example, `05M72DYX` indicates the dynamic activation code that is obtained from the HBR console.

    -   Manually activate the HBR client for Linux

        In the path to which the HBR client is decompressed, run the following command to activate the client: ./setup -t local -k 05M72DYX.

    -   Automatically activate the HBR client for Linux

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


