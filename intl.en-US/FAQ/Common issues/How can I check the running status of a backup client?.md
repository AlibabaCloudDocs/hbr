# How can I check the running status of a backup client? {#concept_63626_zh .concept}

If a backup job fails or you failed to update a backup client, check the status of the backup client. If a client is not running as expected, you can uninstall the client and reinstall the client. This topic describes how to check the status of a backup client.

## Windows {#section_hx1_hmb_rfb .section}

If a backup client is installed on a Windows system, you can perform the following steps to check the running status of the backup client:

-   Check whether the backup service is running as expected

    Open the command prompt and run the services.msc command to view the status of local services. If the client is running as expected, the status of the Aliyun hybrid backup service is Started.

-   View system logs

    If the service is not running as expected, open the command prompt and run the eventvwr command. You can check the system logs for errors that are related to the hybridbackup service.

-   Check whether port 8011 is open for a local backup client

    Open the command prompt run the following command.

    netstat -ano | findstr "8011"

    ![](images/21563_en-US.png)


## Linux {#section_1xq_yz0_g5f .section}

If a backup client is installed on a Linux system, you can perform the following steps to check the status of the backup client:

-   Check whether the backup service is running as expected

    Open a shell and enter `ps axu|grep hybrid`. If the status of the service is started, it indicates that the client is running as expected.

-   Check whether port 8011 is open for a local backup client

    Open a shell and enter `lsof -i:8011`.


## View logs {#section_r1n_5mb_rfb .section}

You can check the status of the backup client based on log files.

Log files of a client are located in the client installation folder. The log files are `hybridbackup.log` and `ids_<a specific date and time>.log`.

