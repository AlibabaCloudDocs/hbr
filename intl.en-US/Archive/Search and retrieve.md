# Search and retrieve

This topic describes how to use the search feature to search data sources and archive the files of an archive vault.

Hybrid Backup Recovery \(HBR\) allows you to search for the files of a data source or archive vault.

-   You can archive the files that are returned from the data source.
-   You can transfer the files that are returned from the archive vault to the data source. These archived files are used to restore the required files in the data source.

## Search for files

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Archive**.

3.  Enter a file name or folder name in the search box. Then, click **Search**.

    ![searchbox](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8515679161/p270187.png)

4.  The search results show the details of each file.

    The following table describes the parameters.

    |Parameter|Description|
    |---------|-----------|
    |**Filename/Path**|The name of a file or directory.|
    |**File Location**|The archive vault or data source where a file resides.|
    |**File Info**|The details of a file. These details include the creation time, modification time, size, and owner.|

5.  Configure the full-text and advanced search features.

    If you cannot obtain the required files by using the preceding search method, you can use the full-text and advanced search features.

    ![advancedsearch](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8515679161/p270106.png)

    -   Fulltext Search switch

        If you turn on the **Fulltext Search** switch, it indicates that the search scope includes the content of each file. Otherwise, the system searches only the names of files and directories.

        **Note:** You can use the full-text search feature to search only files that reside in archive vaults. To perform a full-text search, select Search Archive Vault in the advanced search options.

    -   Advanced switch

        In the upper-right corner of the page, turn on the **Advanced** switch. Set one or more of the following parameters and click **Search**.

        |Parameter|Description|
        |:--------|:----------|
        |**Search Data Source or Search Archive Vault**|The type of the vault. You must specify the name of a data source or archive vault.         -   **Search Data Source**: searches data sources.
        -   **Search Archive Vault**: searches archive vaults. |
        |**Search Type**|The type of the required file. Valid values:         -   **File**: searches for a file.
        -   **Folder**: searches for a folder. |
        |**Modify Time**|The start time and end time of the period during which the file was last modified.|
        |**Min Size**|The minimum size of the file. The memory size is measured in KB, MB, or GB.|
        |**Max Size**|The maximum size of the dirty data file. Unit: KB, MB, or GB.|
        |**Creation Time**|The start time and end time of the period during which the file was created.|


## Archive the file of a data source

If you search a data source, you can directly archive a file that is returned in the search results. You can archive one or all files in the search results.

1.  Select the required file.

2.  Click **Archive Selected File**.

    To archive all the search results from the same data source, click **Archive All Result**.

    **Note:** To archive all results, select the required data source in the advanced search options.

3.  In the Create Archive Plan dialog box, set the following parameters. Then, click **Next**.

    In this example, the Select Archive Vault option is specified.

    |Parameter|Description|
    |---------|-----------|
    |**Config Archive Vault**|You can select an existing archive vault. If no archive vault is created, select **Create Archive Vault**. Then, enter a name for the new archive vault. The archive vault name must be 1 to 64 characters in length. **Note:** An archive vault is a repository that is used by HBR to store archive data in the cloud. Archive data that is collected by multiple clients can be stored in the same archive vault. Archive vaults reside in different regions. You can select or create an archive vault only in the current region. |
    |**Archive Vault Name**|The name of the archive vault. If you do not specify this parameter, a random name is generated and specified for the archive vault.|
    |**Archive Plan Name**|The name of the archive plan. If you do not specify this parameter, a random name is generated and specified for the archive plan.|
    |**Archive Content**|The files to be archived. By default, these files are specified.|
    |**Archive Type**|The following archive types are available:    -   **Archive Once** If this option is selected, the file is archived only once.
    -   **Archive On Schedule**: If this option is selected, you still need to set the **Archive Start Time** and **Archive Run Interval** parameters. This specifies that the system archives the file at the specified interval from the point in time that you specify in the **Archive Run Interval** parameter. |

4.  Click **OK**.

    After the archive plan is created, the new archive plan appears on the Archive Plan tab.


## Retrieve files from an archive vault

If you search an archive vault, you can transfer the required files in the search results to a data source. These files are used to restore the required files in the data source.

1.  Select the required file.

2.  In the upper-right corner of the page, click **Retrieve Selected File**.

    To select search results from one or more archive vaults, click **Retrieve All Result**.

    **Note:** To retrieve all results, select the required archive vault name in the advanced search options.

3.  In the Create Restore Job dialog box, set the required parameters in each step, and click **Next**.

    1.  Retrieve the selected files.

        By default, these files are specified.

    2.  Set the restore destination.

        Select a NAS file system to which you want to restore these files.

    3.  Set the restore path.

        You can restore these files to the original path or specify a new path. You can specify a new path, for example, `/home/usr`.

4.  Click **OK**.

    After a retrieval job is created, the new retrieval job appears on the Job List tab.


