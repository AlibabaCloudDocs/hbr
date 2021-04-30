# Archive data

This topic describes how to use Hybrid Backup Recovery \(HBR\) to archive the data of a data source. After the data is archived, the system generates an archive vault.

## Methods

The following two methods are available for HBR to archive the data of an added data source:

-   Archive analyzed data

    When you add a data source, the **Enable Data Source Analyze** switch is turned on. This method allows you to archive the analyzed data of a data source.

-   Directly archive data

    When you add a data source, the **Enable Data Source Analyze** switch is turned off. This method allows you to directly archive the data of a data source.


## Create an archive plan

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Archive**.

3.  On the Analyze and Archive tab, click **Archive** next to the required data source.

4.  In the **Create Archive Plan** dialog box, set the following parameters.

    In this example, the Select Archive Vault option is specified.

    |Parameter|Description|
    |---------|-----------|
    |**Config Archive Vault**|You can select an existing archive vault. If no archive vault is available, select **Create Archive Vault**. Then, enter an archive vault name to create an archive vault. The archive vault name must be 1 to 64 characters in length. **Note:** An archive vault is a repository that is used by HBR to store archive data in the cloud. Archive data that is collected by multiple clients can be stored in the same archive vault. Archive vaults reside in different regions. You can select or create only an archive vault in the current region. |
    |**Archive Vault Name**|The name of the archive vault. If you do not specify this parameter, a random name is generated and specified for the archive vault.|
    |**Archive Plan Name**|The name of the archive plan. If you do not specify this parameter, a random name is generated and specified for the archive plan.|
    |**Archive File Path**|The path of source files to be archived, for example, /myshare.|
    |**Archive File Rules**|You can specify one of the following three archive rules:    -   **Include All Files**: All files in the specified archive file path are archived.
    -   **Include Files** or **Exclude Files**: You must enter the names of files that you want to archive or exclude in the Enter Paths field. The system archives files based on the specified rule.

The file name that you enter in the Enter Paths field is equal to the sub-path of the archive file path. HBR matches the file names based on the following principles:

        -   If a file name that is specified in the Enter Paths field starts with a forward slash \(/\), HBR combines the sub-path and the archive file path into a complete path. Files in the complete path are included in or excluded from the archive plan.

For example, if the Archive File Path parameter is set to /ifs/dataset and the Enter Paths parameter is set to /subdir/data, all files and directories in the /ifs/dataset/subdir/data directory are included in or excluded from the archive plan.

For example, if the Archive File Path parameter is set to /ifs/dataset and the Enter Paths parameter is set to /abc\*, files and directories whose names are prefixed by abc in the /ifs/dataset/abc directory are included in or excluded from the archive plan.

        -   If a file name that is specified in the Enter Paths field does not start with a forward slash \(/\), HBR uses the file name as a condition. All files and directories that match the condition in the archive file path are included in or excluded from the archive plan.

For example, if the Archive File Path parameter is set to /ifs/dataset and the Enter Paths parameter is set to abc\*, files and directories whose names are prefixed by abc in the /ifs/dataset directory are included in or excluded from the archive plan.

For example, if the Archive File Path parameter is set to /ifs/dataset and the Enter Paths parameter is set to abc, files and directories whose names are abc in the /ifs/dataset directory are included in or excluded from the archive plan. |
    |**Archive Start Time**|The time when the archive plan starts. The time is accurate to the second.|
    |**Archive Run Interval**|The interval at which data is archived. Unit: days or weeks.|
    |**Advanced Settings**|
    |**Backup Sub-task Slice Size**|You can add multiple clients into a backup client group to concurrently perform an archive job. If you set this parameter, the number of files that a client can archive is limited based on the specified value of this parameter. Extra files are archived by another client.|
    |**Delete Original File After Archived**|Specifies whether to delete the original files after the archive plan is completed. By default, the system does not delete the original files.|

5.  Click **OK**.

    After an archive plan is configured, the new archive plan appears on the Archive Plan tab.

    ![archiveplan](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8855679161/p270169.png)


## Operations

After an archive plan is created, you can also perform the following operations.

|Operation|Description|
|---------|-----------|
|**Run Now**|Immediately runs an archive plan once.|
|**Modify Plan**|If you want to modify an archive plan, perform this operation.|
|**Delete Plan**|Deletes an archive plan. If you no longer require an archive, perform this operation.|

