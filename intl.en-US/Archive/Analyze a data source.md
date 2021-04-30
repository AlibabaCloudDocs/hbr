# Analyze a data source

You can use the data analysis feature to obtain the statistics of a data source. The statistics includes the total data volume, total number of files, modification time of each file, access time of each file, proportions of file sizes, and top 5 file types. This topic describes how to use Hybrid Backup Recovery \(HBR\) to analyze a data source.

The [Add a data source](/intl.en-US/Archive/Add a data source.md) operation is performed.

## Analyze a data source

Use one of the following methods to enable the data analysis feature:

-   Enable the data analysis feature

    If the **Enable Data Source Analyze** switch is turned on when you add a data source, you do not need to enable the feature. You can directly view the file distribution of the data source.

-   Configure the data analysis feature

    If the **Enable Data Source Analyze** switch is not turned on when you add a data source, you must enable the feature.

    1.  On the Analyze and Archive tab, choose **More** \> **Config Data Source Analyze Plan** next to the required data source.
    2.  In the Config Data Source Analyze Plan panel, configure a backup client group. Click **Next**.

        You can add multiple clients to a client group to concurrently perform a data analysis job. Select **New Backup Client Group**. Enter a **client group name** and add the required clients to the client group. You can also select an existing client group.

    3.  The following table describes the parameters that you can specify for a data analysis plan.

        |Parameter|Description|
        |---------|-----------|
        |**Enable Data Source Analyze**|Specifies whether to enable the **data analysis** feature.|
        |**Meta Index Start Time**|Specifies when to perform an index operation on metadata.|
        |**Meta Index Interval**|Specifies the interval at which HBR performs an index operation on metadata. Unit: days or weeks.|

    4.  Click **OK**.
-   Immediately perform an index operation on metadata

    You can perform an index operation on metadata at any time regardless of whether the specified start time is reached. On the Analyze and Archive tab, choose **More** \> **Run Meta Indexing** next to the required data source.


