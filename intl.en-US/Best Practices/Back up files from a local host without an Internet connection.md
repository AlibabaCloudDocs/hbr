# Back up files from a local host without an Internet connection {#task_263217 .task}

If you need to back up files from a local host that does not have an Internet connection, you need to connect the host to an Alibaba Cloud VPC by using a VPN gateway or a dedicated data circuit. Then, you can create a configuration file named hybridbackup.toml. This topic describes how to create the hybridbackup.toml configuration file.

-   You have installed a backup client. For more information about how to install a backup client, see [Install and activate a client](../../../../intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Prerequisites.md#section_g3t_wvd_qfb). You do not need to activate the backup client.
-   If you need to connect the local host to a VPC through a VPN gateway, you must create a VPN gateway. For more information, see [Create a VPN Gateway](../../../../intl.en-US/User Guide/Manage a VPN Gateway/Create a VPN Gateway.md#).

1.  Enter the client folder of the client installation folder. For example, C:\\Program Files\\Aliyun Hybrid Backup Service\\client.
2.  Create a .txt file and name the file hybridbackup.toml.
3.  Open the hybridbackup.toml file and add the following information. 

    You need to replace the Endpoint value with an actual endpoint. Supported regions include China \(Beijing\), China \(Shanghai\), China \(Hangzhou\), and China \(Shenzhen\).

    ``` {#codeblock_ukz_ovg_tdr}
    [Server]
    Endpoint = "<hbr-vpc.[cn-hangzhou].aliyuncs.com>"
    ```

4.  Restart the backup service. 
    -   Backup clients that are installed on Windows

        Open the command prompt, enter services.msc and press Enter to open the Services dialog box, locate the **Aliyun hybrid backup service**, and restart the service.

    -   Backup clients that are installed on Linux

        Run the service hybridbackup restart command to restart the backup service.


