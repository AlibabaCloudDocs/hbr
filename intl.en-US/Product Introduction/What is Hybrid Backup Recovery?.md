# What is Hybrid Backup Recovery?

Hybrid Backup Recovery \(HBR\) is a fully-managed online backup service that allows you to back up data to the cloud in an efficient, secure, and cost-effective way. You can use HBR to back up data from local Internet data centers \(IDCs\), branches, or cloud resources to a cloud vault.

## Architecture

![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7134817161/p63379.jpg)

After an HBR client is deployed in a local IDC, you can use an Express Connect circuit, a virtual private network \(VPN\) gateway, or the Internet to back up data from specified local files, Network Attached Storage \(NAS\) files, VMware virtual machines, and SQL Server databases to a backup vault on Alibaba Cloud. Based on the high-level encryption and efficient deduplication and compression technologies, HBR guarantees the efficiency and security of data transmission.

In addition, HBR provides easy-to-use native data protection for data that comes from various sources on Alibaba Cloud, including files on Elastic Compute Service \(ECS\) instances, SQL Server and SAP HANA deployed on ECS instances, Apsara File Storage NAS, and Object Storage Service \(OSS\).

## Benefits

The following table lists the advantages of HBR over an on-premises backup system that is built in an on-premises IDC or on the cloud.

|Item|On-premises backup system|HBR|
|----|-------------------------|---|
|Permission management|Not supported. No strict permission management is available. Therefore, misoperations such as accidental data deletion may occur.

|Supported. HBR uses Resource Access Management \(RAM\) to grant different permissions to different roles and allow each role to access only authorized resources. |
|Deduplication and compression|Not supported. Duplicate backup data increases storage costs and lowers the backup speed.

|Supported. Using deduplication and compression technologies that are developed by Alibaba Cloud, HBR can effectively reduce the amount of transmitted data and occupied storage. This raises the backup speed and reduces costs. |
|Backup alerting|Not supported. You must manually track backup processes to detect backup failures. Otherwise, you may find backup failures only when you attempt to restore data from backups.

|Supported. HBR provides the backup alerting feature to send alert notifications to specified contacts when a backup fails or a client is disconnected from a server. |
|Lifecycle management|You must manually manage the lifecycle of backup data.|HBR automatically manages the lifecycle of backup data.|
|Remote backup|Not supported.|HBR allows you to create a remote mirror vault for a backup vault. You can use a mirror vault to back up or restore data across regions.|
|Data restoration|You must manually restore data from multiple data replicas.|HBR provides backup versions for you to choose when you attempt to restore data. You can also set restore rules.|
|Management costs|High You must manually compile scripts to back up data and dispatch dedicated engineers to manage backups. The complex and difficult operations and maintenance reduce resource utilization and increase management costs.

|Low HBR manages your backup data in cloud vaults. You do not need to worry about backup management, such as hardware procurement, configuration, cluster scaling, and security. |
|Data encryption|You must build a system to encrypt data.|HBR uses the Advanced Encryption Standard \(AES\) 256-bit algorithm to encrypt and transmit data from a backup source and store the backup data in the cloud. During data transmission, HBR also uses HTTPS to encrypt data.|

## Supported backup sources

|Backup source|Operating system|Backup client|
|:------------|:---------------|:------------|
|On-premises IDC|File directories|Windows/Windows Server/Linux|File backup client|
|Images of VMware vSphere virtual machines|Windows/Windows Server/Linux|Virtual machine client|
|SAP HANA|Linux|File backup client|
|SQL Server|Windows Server|File backup client|
|MySQL|Windows Server/Linux|File backup client|
|MongoDB|Windows Server/Linux|File backup client|
|Alibaba Cloud ECS|File directories of an ECS instance|Windows Server/Linux|ECS backup client|
|SAP HANA databases that are deployed on an ECS instance|Windows Server/Linux|ECS backup client|
|MySQL, Oracle, and SQL Server databases deployed on an ECS instance|Windows Server|ECS backup client|
|Cloud disks \(system disks and data disks\)|N/A|Backup is performed by using the snapshot service without clients.|
|Cloud Storage Gateway \(CSG\)|File gateways deployed on Alibaba Cloud|N/A|Cloud Storage Gateway backup client|
|Apsara File Storage NAS|Data stored in Apsara File Storage NAS|N/A|N/A|
|Alibaba Cloud OSS|Data stored in OSS|N/A|N/A|

## Concepts

|Header|Description|
|:-----|:----------|
|Backup source|The host on which the data to be backed up is stored, such as a server, a virtual machine, or an ECS instance. |
|Client|The client that you install on a backup source to back up and restore data. You must install an appropriate client for different backup sources.

Each client supports resumable upload and timed retry to guarantee backup stability. In this way, data can be backed up even when short-term network jitter occurs. |
|Region|The physical location of an Alibaba Cloud IDC. After a resource is created, you cannot change the region of the resource. For more information, see [Regions and zones](). |
|Backup vault|The HBR cloud backup warehouse used to store backup data in the cloud. Backup data from multiple clients can be stored in the same vault. This helps you manage the backup data and reduce management time and costs.

The number of clients and the storage capacity supported by each backup vault are not limited. You can install a client and extend the storage capacity as needed. Each backup vault features data reliability of 99.9999999999% \(twelve 9's\).

You must specify an appropriate region for each backup vault to improve backup performance and facilitate disaster recovery. After a backup vault is created, you cannot change the region of the backup vault. A backup vault is also the basic unit that you can use to remove duplicates or compress data. |
|Intermediate host|The host that has a graphical user interface \(GUI\). If you attempt to back up data from a file directory in a Linux operating system without a GUI, you can download and install an HBR client on an intermediate host, and deploy the intermediate host on the backup source. Then, you can log on to the client on the intermediate host and back up data from the backup source. |

