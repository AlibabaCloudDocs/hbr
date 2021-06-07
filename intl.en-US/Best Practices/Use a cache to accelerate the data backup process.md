# Use a cache to accelerate the data backup process

The cache feature is enabled by default on a backup client for on-premises files to accelerate the data backup process. The cache is used only to accelerate the data backup process, and cannot restore data on an on-premises or remote host.

A Hybrid Backup Recovery \(HBR\) client is installed for on-premises files. The version of the client is 1.5.0 or later. For more information, see [Preparations](/intl.en-US/Back up on-premises severs/On-premises file backup (new)/Preparations.md).

The cache feature allows you to accelerate the data backup process by caching data entry IDs and metadata. This feature reduces network requests during data backup. You can disable this feature or optimize its settings on the backup source.

## Procedure

You can perform the following steps to create a cache configuration file. You can also disable the cache feature or optimize its settings by using the configuration file. This file is optional. If you do not create a file, the default settings of the feature are used.

1.  Log on to the on-premises server or virtual machine \(VM\) whose files you want to back up.

2.  Open the installation folder of the backup client.

    You can find the installation path based on the following default installation paths.

    -   For backup clients of an earlier version

        Linux: /opt/alibabacloud/hbr

        Windows: C:\\Program Files\\Aliyun Hybrid Backup Service

    -   For backup clients of the latest version

        Linux: /opt/alibabacloud/hbrclient

        Windows: C:\\Program Files\\Aliyun Hybrid Backup Service Client

3.  Create a file named `hbr.config` in the `client` folder.

    **Note:** The `hbr.config` file must be at the same directory level as the `ids` file.

4.  In the `hbr.config` file, set the following parameters for the cache feature.

    |Parameter|Description|
    |:--------|:----------|
    |disable\_blob\_cache|Specifies whether to cache data entry IDs. Valid values:    -   true: Data entry IDs are cached.
    -   false: Data entry IDs are not cached. |
    |max\_blob\_cache\_weight|The maximum system memory that can be used by the cache for data entry IDs. Default value: 0.15. It indicates 15% of the total system memory. The value must be between 0 and 1.|
    |cache\_prefix|The path in which the cached data entry IDs are stored. The value must be an absolute path.|
    |max\_retain\_count|The maximum number of cached data entry IDs.|
    |disable\_file\_cache|Specifies whether to cache metadata. Valid values:    -   true: Metadata is cached.
    -   false: Metadata is not cached. |
    |file\_cache\_max\_size\_hint|The maximum size of a metadata cache file. The actual size may exceed the specified value. Default value: 2 GB. **Note:**

    -   If you set the parameter to 2 GB, a minimum of 4 TB data can be backed up.
    -   If you set the parameter to a small value, the backup does not fail but the cache performance is degraded.
    -   The value of the parameter cannot exceed the available disk space. |


## Example

The following example shows the configurations of the hbr.config file:

```
disable_blob_cache = false
max_blob_cache_weight = 0.15
cache_prefix = D:\CacheFolder
max_retain_count = 16 

disable_file_cache = false
file_cache_max_size_hint = 2GB           
```

