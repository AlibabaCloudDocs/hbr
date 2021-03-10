# How can I limit the memory size of an HBR client?

This topic describes how to modify the number of cache files to limit the memory size of a Hybrid Backup Recovery \(HBR\) client.

HBR consumes a large amount of memory resources when it backs up data such as files and applications. If you do not limit the number of cache files during a backup, the "Out of Memory" error may occur on the host from which files are backed up and the backup may fail. To resolve this issue, you can limit the number of cache files by modifying the configuration file of the HBR client. This way, you can reduce the consumption of memory resources.

## Procedure

1.  Log on to the host from which files are backed up.
2.  Go to the installation directory of the HBR client.
3.  Create a file named `hbr.config` in the folder `client`.

    **Note:**

    -   If the `hbr.config` file already exists, you do not need to create it. You can simply edit the file.
    -   The `hbr.config` file must be at the same directory level as the `ids` file.
4.  Set the following parameters of the `hbr.config` file.

    |Parameter|Description|
    |---------|-----------|
    |max\_tree\_nodes|The maximum number of metadata files that can be cached in memory. Configurable range: 1 to 16384.|
    |max\_read\_dir\_names|The maximum number of files that can be buffered in memory. Configurable range: 1 to 100000.|

    The following example shows the configurations of the hbr.config file:

    ```
    max_tree_nodes=1000
    max_read_dir_names=1000
    ```

5.  Restart the HBR backup client.

    The following example shows how to restart the HBR client in Linux:

    ```
    # Restart the HBR client in Linux version 2.x.
    systemctl restart hbrclient
    restart hbrclient
    /etc/init.d/hbrclient restart
    
    # Restart the client in Linux version 1.x.
    systemctl restart hybridbackup
    restart hybridbackup
    /etc/init.d/hybridbackup restart
    ```

    The following example shows how to restart the HBR client in Windows:

    1.  Press `Win+R`. In the **Run** dialog box, enter `services.msc` and click **OK**.
    2.  Find the Aliyun Hybrid Backup Service in the service list. Right-click Aliyun Hybrid Backup Service and select **Restart**.

        ![restart](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4002925161/p247380.png)


