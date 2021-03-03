# Use a cache to accelerate the data backup process

The cache feature is enabled by default on a backup client for on-premises files to accelerate the data backup process.

## Background information

The cache feature allows you to accelerate the data backup process by caching data entry IDs and metadata. This feature reduces network requests during data backup. You can disable this feature or optimize the configurations of this feature on the backup source.

**Note:**

-   The cache is used only to accelerate the data backup process but cannot help restore data on a local or remote host.
-   You can enable this feature only on a backup client whose version is 1.5.0 or later.

## Prerequisites

A backup client for on-premises files is downloaded and installed.

## Procedure

You can perform the following steps to create a cache configuration file. You can also disable the cache feature or optimize the configurations of the feature by using the file. This file is optional. If you do not create this file, the default settings of the feature are used.

1.  Log on to the on-premises host where source data is stored.

2.  Open the installation folder of the backup client.

3.  Open a subfolder of the `client` folder and create a file named `hbr.config`.

    **Note:** The `hbr.config` file must be stored in the folder where the `ids` file resides.

4.  In the `hbr.config` file, set the following parameters for the cache feature.

    |Parameter|Description|
    |:--------|:----------|
    |disable\_blob\_cache|    -   true: disables a cache for data entry IDs.
    -   false: enables a cache for data entry IDs. |
    |max\_blob\_cache\_weight|    -   The maximum system memory that can be used by the cache for data entry IDs.
    -   Default value: 0.15. It indicates 15% of the total system memory.
    -   The value must be between zero and one. |
    |cache\_prefix|    -   A string that indicates a path. The location where the cached data entry IDs and metadata are stored.
    -   The path must be an absolute path. |
    |max\_retain\_count|    -   The maximum number of cached data entry IDs.
    -   The value must be an integer. |
    |disable\_file\_cache|    -   true: disables a cache for metadata.
    -   false: enables a cache for metadata. |
    |file\_cache\_max\_size\_hint|    -   The maximum size of a cache file. The disk space used may exceed the specified value.
    -   Default value: 2 GB.

**Note:**

        -   If you set the maximum cache file size to 2 GB, a maximum of 4 TB data can be backed up.
        -   If you set the maximum cache file size to a small value, the backup does not fail but the performance of the cache is affected.
        -   The value of the parameter cannot exceed the available disk space.
    -   Unit: B, KB, MB, or GB The default unit is B, which indicates a byte. |


## Examples

This section provides an example hbr.config file:

```
disable_blob_cache = false
max_blob_cache_weight = 0.15
cache_prefix = D:\CacheFolder
max_retain_count = 16 

disable_file_cache = false
file_cache_max_size_hint = 2g           
```

