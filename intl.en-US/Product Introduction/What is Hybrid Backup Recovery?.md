# What is Hybrid Backup Recovery? {#concept_62362_zh .concept}

Hybrid Backup Recovery \(HBR\) is an efficient, secure, cost-effective, and fully managed backup and storage service. You can use HBR to back up data from local data centers, branches, or cloud resources to a cloud vault.

## Architecture {#section_ddj_phr_sfb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40327/156464051354081_en-US.jpg)

## Benefits {#section_fq1_5hr_sfb .section}

Compared with the setup of a user-created local backup system, Hybrid Backup Recovery has the following advantages:

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

## Supported backup sources {#section_scl_rkr_sfb .section}

|Backup source|Operating system|Backup client|
|:------------|:---------------|:------------|
|Local data center|File directory|Windows, Windows Server, and Linux|File client|
|Images of VMware vSphere virtual machines|Windows, Windows Server, and Linux|Virtual machine client|
|SAP HANA|Linux|File client|
|SQL Server|Windows Server|File client|
|MySQL|Windows Server and Linux|File client|
|MongoDB|Windows Server and Linux|File client|
|Alibaba Cloud ECS|File directories of an ECS instance|Windows Server and Linux|ECS backup client|
|SAP HANA databases that are located in an ECS instance|Windows Server and Linux|ECS backup client|
|SQL Server databases that are located in an ECS instance|Windows Server|ECS backup client|

## Concepts {#section_ef5_5wx_pfb .section}

|Name|Description|
|:---|:----------|
|Backup source| The hosts where the data to be backed up is located, such as servers, virtual machines, and ECS instances.

 |
|Client| A client is installed on a backup source. You can use the client to back up and restore data. You must install corresponding clients for different backup sources.

 |
|Region| Regions are Alibaba Cloud on-premises data centers. After a resource is created, you cannot change the region of the resource. For more information, see [Regions and zones](../../../../../intl.en-US/General Reference/Regions and zones.md).

 |
|Backup vaults| A backup vault is an HBR cloud backup warehouse used to store backup data in the cloud. Backup data from multiple clients can be stored in the same vault. This helps you to manage the backup of data and reduce management time and costs.

 You must specify a region for each backup vault. An appropriate region for a backup vault helps improve backup performance and facilitate disaster recovery. After a backup vault is created, you cannot change the region of the backup vault. A backup vault is the basic unit that you can use to eliminate duplicate copies of repeated data or compress data.

 |
|Mirror vaults| A mirror vault is the mirror of a backup vault. However, the two vaults are located in different regions. You can use a mirror vault for geo-disaster recovery or cross-region data restoration.

 |
|Intermediate hosts| If you attempt to back up data from a Linux system without a desktop environment, you must download an HBR client on an intermediate host with a desktop environment. Then, you need to deploy the HBR client on a host where a data source is located. You can log on to the client on the intermediate host.

 |

