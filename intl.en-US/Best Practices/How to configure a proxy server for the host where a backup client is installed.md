# How to configure a proxy server for the host where a backup client is installed {#task_1339954 .task}

This topic describes how to configure a Windows Server as a proxy server for the host where a backup client is installed.

If the host where data is to be backed up cannot access the Internet, you need to configure a proxy server for the host.

1.  Prepare a server with Internet access for configuring the proxy service.
2.  Install Visual C++ Redistributable for Visual Studio 2015-2019. [VC\_redist.x64.exe](https://aka.ms/vs/16/release/VC_redist.x64.exe) 

    [VC\_redist.x86.exe](https://aka.ms/vs/16/release/VC_redist.x86.exe)

3.  Download the binary package of [Apache HTTP Server 2.4](https://httpd.apache.org/docs/current/platform/windows.html#down) and decompress the package.
4.  Modify the configuration file Apache24\\conf\\httpd.conf. 

    **Note:** In Define SRVROOT "\\Apache24", change the path to the installation directory of Apache. When Apache is stored in the root directory of disk D, for example, you can change the path to D:\\Apache24.

    -   Load modules.

        ``` {#codeblock_cos_mkg_gfz}
        LoadModule proxy_module modules/mod_proxy.so
        LoadModule proxy_connect_module modules/mod_proxy_connect.so
        LoadModule proxy_ftp_module modules/mod_proxy_ftp.so
        LoadModule proxy_http_module modules/mod_proxy_http.so
        ```

    -   Specify any port as the listening port, for example, `Listen 8888`.
    -   Set access permissions.

        ``` {#codeblock_095_66l_00m}
        ProxyRequests On
        ProxyVia On
        <Proxy *>
        Require all granted
        </Proxy>
        ```

5.  Double-click `Apache24\bin\httpd.exe` to start the proxy service.
6.  Install the backup client on the host without Internet access in either of the following two ways. After the backup client is installed, you can start backup. 
    -   Method 1
        1.  Log on to the host without Internet access.
        2.  Choose **Computer** \> **Control Panel** \> **System and Security** \> **System** \> **Advanced system settings** \> **Environment Variables**.
        3.  In the Environment Variables dialog box, click **New** in the System variables area.
        4.  Set Variable name to HBR\_PROXY and Variable value to a string in the format of private IP address:listening port, such as http://10\*\*\*\*:8888.
        5.  After the environment variable is configured, restart the host.
        6.  Install the ECS backup client in the HBR console. For more information, see [Install an ECS backup client](../../../../intl.en-US/Back up ECS/Back up files in ECS/Prerequisites.md#section_vb1_zz5_fgb). If you need to install the offline backup client, see [Create a client](../../../../intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Prerequisites.md#section_cnq_phc_ggb).
    -   Method 2

        Install the backup client for the host without Internet access in the HBR console. If it is the first time you install a backup client for the host in the HBR console, the backup client fails to be installed. In this case, perform the following steps to activate the backup client:

        1.  Log on to the host without Internet access. Add a .toml configuration file in the client directory in the installation directory of the backup client.

            -   Windows
                1.  Go to the client directory in the installation directory of the backup client, for example, C:\\Program Files\\Aliyun Hybrid Backup Service\\client.
                2.  Create the configuration file hybridbackup.toml.
                3.  Add the following information to the hybridbackup.toml file and save the file:

                    ``` {#codeblock_llm_uyk_3ka .language-json}
                    [Server]
                    Proxy= "http://10. ****:8888"
                    ```

            -   Linux
                1.  Go to the client directory in the installation directory of the backup client, for example, /opt/alibabacloud/hbr/client.
                2.  Create the configuration file hybridbackup.toml.

                    ``` {#codeblock_178_o2z_c55 .language-json}
                    vi /opt/alibabacloud/hbr/client/hybridbackup.toml
                    ```

                3.  Add the following information to the hybridbackup.toml file and save the file:

                    ``` {#codeblock_7m5_x20_tve .language-json}
                    [Server]
                    Proxy= "http://10. ****:8888"
                    ```

            After the .toml file is added, restart the hybridbackup service.

        2.  Find the host for which the backup client fails to be installed in the HBR console and click **Activate Client**.
        3.  Start backup after the backup client is activated.

