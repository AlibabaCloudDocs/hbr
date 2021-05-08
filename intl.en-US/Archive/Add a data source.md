# Add a data source

If you archive data for the first time, you must add a data source. This topic describes how to use Hybrid Backup Recovery \(HBR\) to add an on-premises NAS data source.

HBR is authorized and a client is installed. For more information, see [Preparations](/intl.en-US/Archive/Preparations.md).

## Procedure

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Archive**.

3.  On the Analyze and Archive tab, click **Create Data Source**.

4.  In the Create Data Source step, set the following parameters and click **Next**.

    In this example, the New NAS Instance option is specified.

    1.  The following table describes the parameters.

        |Parameter|Description|
        |---------|-----------|
        |NAS Instance From|The source from which NAS data is obtained. Valid values: New NAS Instance and Select Exist NAS.|
        |**NAS Type**|The type of the NAS file system. Valid values:        -   **Isilon \(PowerScale\)**: Isilon NAS file systems.
        -   **Others**: other NAS file systems. |
        |**NAS Instance Name**|The name of the NAS file system.|
        |**NAS Management Username**|The username of the account that is used to manage the NAS file system.|
        |**NAS Management Password**|The password for the username.|
        |**NAS Network Address**|The network address of the NAS file system.|
        |**NAS Management Port**|The management port of the NAS file system.|
        |**NAS Share Path**|The relative /ifs path of the NAS file system, for example, /myshare. The path name can contain letters, digits, and the following special characters: `,-_=/.:\`. |
        |**Protocol Type**|The protocol type of the NAS file system. Valid values:         -   NFS: Select this value if applicable.
        -   SMB: Select this value if applicable. |

    2.  Optional. Click **Advanced Settings** and click **+Set Mount Parameters**.

        You can add multiple mount parameters when you mount a file system. Separate these parameters with commas \(,\). The following table describes the mount parameters.

        |Parameter|Description|
        |:--------|:----------|
        |vers|Specifies the protocol version of the file system.         -   vers=3: uses NFSv3 to mount the file system.
        -   vers=4: uses NFSv4 to mount the file system. |
        |nolock|Specifies whether to enable file locking.|
        |proto|Specifies the protocol that is used to mount the file system.|
        |rsize|Specifies the size of data blocks that the client reads from the file system. Recommended value: 1048576. Unit: bytes. |
        |wsize|Specifies the size of data blocks that the client writes to the file system. Recommended value: 1048576. Unit: bytes. |
        |hard|Specifies that applications stop accessing a file system when the file system is unavailable, and wait until the file system becomes available. We recommend that you set this parameter to true.|
        |timeo|Specifies the period in deciseconds \(tenths of a second\) for which the NFS client waits before it retries to send a request. Recommended value: 600. Unit: deciseconds. |
        |retrans|Specifies the number of times for which the NFS client retries a request. Recommended value: 2. |

5.  Associate a client group.

    You can add multiple clients to a client group to concurrently perform an archive job. You can also select an existing client group. Perform the following steps to create a client group:

    1.  In the Client Group From field, select **New Backup Client Group**. Enter a **client group name** and add the required backup clients to the client group.
    2.  Click **Next**.
6.  Configure a data analysis plan.

    In the Config Data Source Analyze Plan step, set the following parameters.

    |Parameter|Description|
    |---------|-----------|
    |**Enable Data Source Analyze**|Specifies whether to enable the data analysis feature. If you turn on the **Enable Data Source Analyze** switch, HBR starts data analysis after a data source is added. You can use HBR to scan, analyze, or search a data source only after the data analysis feature is enabled for the data source.|
    |**Meta Index Start Time**|Specifies when to perform an index operation on metadata.|
    |**Meta Index Interval**|Specifies the interval at which HBR performs an index operation on metadata. Unit: days or weeks.|

7.  Click **OK**.

    After a data source is added, the new data source appears on the Analyze and Archive tab.


## Operations

You can click **More** next to an added data source and select the required operation. The following table describes the available operations.

|Operation|Description|
|---------|-----------|
|**View Datasource**|Views the details of an existing data source. These details include the type, NAS network address, NAS share path, and backup client group.|
|**Edit Datasource**|Modifies the parameters of an existing data source.|
|**Unregister Datasource**|Unregisters a data source. If you no longer need to archive data, perform this operation.|

