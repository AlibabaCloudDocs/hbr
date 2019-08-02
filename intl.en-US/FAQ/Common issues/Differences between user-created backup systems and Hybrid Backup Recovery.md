# Differences between user-created backup systems and Hybrid Backup Recovery {#concept_185139 .concept}

This topic describes the differences between user-created backup systems and Hybrid Backup Recovery \(HBR\) and the advantages of HBR. User-created backup systems include those you build on the cloud or in local data centers.

|Item|User-created backup system|Hybrid Backup Recovery|
|----|--------------------------|----------------------|
|Permission management|Not supported No strict permission management is available to performing a manual backup. Improper operations such as accidental file deletion are prone to occur.

 |Supported With Resource Access Management, HBR users are categorized multiple permission groups. This is designed to reduce data security risks.

 |
|Deduplication and compression|Not supported Repeated backups increase a large number of storage costs and reduce backup speed.

 |Supported HBR supports deduplication and compression technologies that are developed by Alibaba Cloud. These technologies help you to reduce the amount of transmitted data and occupied storage. This is designed to reduce costs and increase the backup speed.

 |
|Backup alerts|Not supported You need to manually track backup processes to identify whether backup failures occur. Several backup failures are only found when you attempt to restore data from the backups.

 |Supported HBR provides users with notifications, such as when a backup fails or when a client is disconnected from a server.

 |
|Lifecycle of data backups|Manual management|Automatic management|
|Data restoration|You must manually restore data from multiple data copies.|You only need to select a backup version from which data is restored. You can also set restore rules.|
|Management cost|High Manual backups require custom scripts to run backups and dedicated backup engineers to manage backups. This brings difficulties for backup management and administration, reduces resource utilization, and increases management costs.

 |Low With HBR, you do not need to be concerned with issues, such as hardware procurement, configuration, cluster expanding, and security. Instead, you only need to upload backups onto cloud vaults.

 |

