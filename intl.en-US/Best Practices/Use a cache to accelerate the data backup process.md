# Use a cache to accelerate the data backup process {#concept_m5g_3nt_qfb .concept}

The cache function is enabled by default on a backup client to accelerate the data backup process. This function helps you accelerate the data backup process by caching data entry IDs and metadata. You can disable this function or optimize the configurations of this function on source backup devices.

**Note:** 

-   The cache is only used to accelerate the data backup process, but cannot help restore data on a local host or remote host.
-   You can only enable this function on a backup client whose version is 1.5.0 or later.

## Prerequisites {#section_afz_fyt_qfb .section}

You have downloaded and installed a backup client.

## Procedure {#section_z3j_zxt_qfb .section}

You can perform the following steps to create a cache-based acceleration file. You can also disable the cache-based acceleration function or optimize the configurations of the function by configuring parameters in this file. This file is optional. If you do not create this file, the cache-based acceleration function works with the default settings.

1.  You must log on to a server or virtual machine where data needs to be backed up.
2.  Locate and open the installation folder of the backup client.
3.  Open the subfolder of the `client` folder, and create a file named `hbr.config`.

    **Note:** The `hbr.config` file must be stored in the folder where the `hybridebackup`and `ids` applications are located.

4.  In the `hbr.config` file, configure the following parameters for cache-based acceleration.

    |Name|Description|
    |:---|:----------|
    |disable\_blob\_cache|     -   true: disables caching data entry IDs.
    -   false: enables caching data entry IDs.
 |
    |max\_blob\_cache\_weight|     -   Specifies the maximum percentage of system memory usage by a cache that is used to store data entry IDs.
    -   Default value: 0.15. It indicates 15% of total system memory.
    -   The value must be between zero and one.
 |
    |cache\_prefix|     -   A string that indicates a path. The location where cached data entry IDs and metadata are stored.
    -   The path must be an absolute path.
 |
    |max\_retain\_count|     -   The maximum number of cached data entry IDs.
    -   The value must be an integer.
 |
    |disable\_file\_cache|     -   true: disables a metadata cache.
    -   false: enables a metadata cache.
 |
    |file\_cache\_max\_size\_hint|     -   The maximum size of a cache file. The disk space used may exceed the specified value.
    -   Default value: 2 GB.

**Note:** 

        -   With a cache file of 2 GB, you can back up a maximum 4 TB of data.
        -   If you specify a small amount of data for the parameter, the backup does not fail but the performance of the cache is affected.
        -   The value of the parameter cannot exceed the available disk space.
    -   Unit: B, KB, MB, and GB The default unit is B, which indicates a byte.
 |


## Example {#section_syl_jb5_qfb .section}

```

disable_blob_cache = false
max_blob_cache_weight = 0.15
cache_prefix = D:\CacheFolder
max_retain_count = 16 

disable_file_cache = false
file_cache_max_size_hint = 2g


```

