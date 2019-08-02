# Reactivate a file client {#concept_t25_242_jhb .concept}

If you fail to activate a file client, you can perform the following steps to reactivate the client.

## Reactivate a client in the console {#section_zzn_342_jhb .section}

1.  Log on to the [Hybrid Backup Recovery console](https://hbr.console.aliyun.com).
2.  On the File Client page, locate the failed client.
3.  In the Actions column, click **Activate Client**.![](images/43535_en-US.png)
4.  In the Create Client dialog box, enter the required information based on the descriptions provided in the following table.

    |Name|Description|
    |:---|:----------|
    |Client IP Address|The IP address of the server or virtual machine that hosts the client. **Note:** The IP address must be accessible by a browser.

 |
    |AccessKey ID|Download the AccessKey ID and AccessKey Secret of the Alibaba Cloud account where the Hybrid Backup Recovery \(HBR\) service is activated.|
    |AccessKey Secret|Download the AccessKey ID and AccessKey Secret of the Alibaba Cloud account where the HBR service is activated.|
    |Create Client Password|Set the logon password of the client. The password must be a minimum of six characters in length.|

5.  Click **Activate Client** to open a web page. You can use this web page to operate the file client. You can use a file client to back up data.

## Reactivate a client on a web page {#section_fzc_k42_jhb .section}

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  On the File Client page, locate the failed client.
3.  In the Actions column, click**Download Certificate**, and then save the certificate.
4.  Open a browser, enter `http://localhost:8011` in the address bar to open the Initialize Register window, and configure the required settings based on the descriptions provided in the following table.

    **Note:** 

    -   If you perform a backup operation on an intermediate host, you must change `localhost` to the IP address of the server or virtual machine from which you back up data.
    -   Port 8011 is the default port that you can use to logon to a file client. If port 8011 on the server or virtual machine is occupied by another application, you can [specify another port number for a file client](intl.en-US/FAQ/On-premises backup FAQ/How can I change the number of the logon port for a file client?.md).
    |Name|Description|
    |:---|:----------|
    |Upload Certificate|You can upload the token you have downloaded from the console. The token is used as a certificate. The validity period of each certificate is two days. You must download a new certificate to register a client when the certificate in use expires.|
    |AccessKey ID and AccessKey Secret|Download the AccessKey ID and AccessKey Secret of the Alibaba Cloud account where the HBR service is activated.|
    |Network Type|     -   VPC: Select this option when the server or virtual machine is located in a Virtual Private Network \(VPC\) and in the same region where the backup source is located.
    -   Classic: Select this option when VPCs are not applicable.
 |
    |Password|Set the logon password of the client. The password must be a minimum of six characters in length.|
    |Encrypt AccessKey|If you use the password to encrypt the AccessKey, you must enter the password after each restart.|

5.  Click **Register** to activate the client.

