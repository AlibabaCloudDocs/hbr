# How can I select a different port as the logon port of a file client?

When you install a file client, port 8011 is the default port that you use to log on to the file client. If port 8011 is occupied by other applications, you can change the logon port of the file client when you install the client.

## Windows

If you want to back up data from a server or virtual machine that runs on Windows, install a client and specify a logon port. Perform the following steps:

1.  Download a client to the target server or virtual machine.

2.  Extract the installation package of the client.

3.  Open Command Prompt.

4.  Go to the directory where the client installation file resides.

5.  Enter the name of the client installation file and add the `/p=<a specified port number>` parameter, for example, `hbr-install-1.5.2-windows-amd64.exe /p=8022`. Press Enter and install the client as prompted.

    ![55](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4165427161/p259734.png)

    After the client is installed, open a browser and enter `http://localhost:<a specified port number>` in the address bar. Press Enter to activate the client.


## Linux

If you want to back up data from a server or virtual machine that runs on Linux, install a client and specify a logon port. Perform the following steps:

1.  Download a client to the server or virtual machine.

2.  Extract the installation package of the client to a specified directory and run the `./setup -p <a specified port number>` command to start the Hybrid Backup Recovery \(HBR\) service. For example, if you want to set the logon port of the client to port 8022, run the `./setup -p 8022` command.

    ![22](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4165427161/p259735.png)

    After the client is installed, open a browser and enter `http://localhost:<a specified port number>` in the address bar. Press Enter to activate the client.


