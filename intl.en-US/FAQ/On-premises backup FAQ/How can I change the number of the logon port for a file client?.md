# How can I change the number of the logon port for a file client? {#concept_rvf_dwr_bgb .concept}

When you install a file client, port 8011 is the default port that you use to log on to the file client. If port 8011 is occupied by other applications, you can change the logon port of the file client when installing the client.

## Windows {#section_cr3_jxr_bgb .section}

If Windows is running on a server or virtual machine from which you want to back up data, you can perform the following steps to install a client and specify a logon port:

1.  Download a client to the server or virtual machine.
2.  Extract the client installation package.
3.  Open the command prompt.
4.  Navigate to the directory where the client installation file is located.
5.  Enter the name of the client installation file and add the `/p=<a specified port number>` parameter. For example, `hbr-install-1.5.2-windows-amd64.exe /p=8022`. Press Enter and follow the instructions to install the client.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/78559/156471710354176_en-US.png)


After the client is installed, open a browser and enter `http://localhost:<a specified port number>` in the address bar. Press Enter to activate the client.

## Linux {#section_wqc_kxr_bgb .section}

If Linux is running on a server or virtual machine from which you want to back up data, you can perform the following steps to install a client and specify a port to log on to the client:

1.  Download a client to the target server or virtual machine.
2.  Extract the client installation package to a directory and run the `./setup -p <a specified port number>` command to start the Hybrid Backup Recovery service. For example, if you want to set the logon port number of the client to 8022, run the `./setup -p 8022` command.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/78559/156471710354178_en-US.png)


After the client is installed, open a browser and enter `http://localhost:<a specified port number>` in the address bar. Press Enter to activate the client.

