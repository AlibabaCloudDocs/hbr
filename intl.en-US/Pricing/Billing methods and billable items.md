# Billing methods and billable items

This topic describes the billing methods and billable items of Hybrid Backup Recovery \(HBR\).

## Billing methods

HBR supports the pay-as-you-go billing method.

-   You are billed only for the resources that you have used.
-   Bills are generated on an hourly basis and payments are settled on a monthly basis.
-   When you activate HBR, pay-as-you-go is used as the default billing method.

## Billable items

The following table describes the billing items of HBR.

|Billable items|Description|Billing method|Pricing|
|:-------------|:----------|:-------------|:------|
|Backup clients and data migration from VMware virtual machines to Elastic Compute Service \(ECS\) instances|HBR provides clients that can be used to back up files, applications, and virtual machines. HBR also allows you to migrate data from VMware virtual machines to ECS instances. **Note:**

-   You are billed for file backup based on the number of devices. This applies to devices that have HBR clients installed. You can use HBR clients to back up Cloud Storage Gateway \(CSG\) instances, files stored in ECS instances, and local files.
-   You are billed for application backup based on the number of ECS instances. This applies to instances that have HBR clients installed. You can use HBR clients to back up SQL Server and SAP HANA applications that are deployed on ECS instances.
-   You are billed for virtual machine backup based on the capacity of the virtual disks to be backed up. You can use HBR clients to back up VMware virtual machines.
-   You are billed for virtual machine migration to ECS based on the number of virtual machines to be migrated. The unit price is USD 108.00 per virtual machine. Bills are generated after virtual machines are migrated.

|Pay-as-you-go

|The standard pricing scheme for HBR is used for all regions. For more information, see [Hybrid Backup Recovery \(HBR\) Pricing](https://www.alibabacloud.com/product/hybrid-backup-recovery/pricing). |
|Backup storage|HBR deduplicates and compresses data for backup. You are billed for the backup storage based on the capacity consumed by the deduplicated and compressed data.|Pay-as-you-go

|The standard pricing scheme for HBR is used for all regions. For more information, see [Hybrid Backup Recovery \(HBR\) Pricing](https://www.alibabacloud.com/product/hybrid-backup-recovery/pricing). |
|Outbound traffic over the Internet during data restore.|If you restore data from HBR to your local device over the Internet, you are charged for the traffic that is consumed for data download. -   If you restore data from HBR to ECS instances over the internal network of Alibaba Cloud, you are not charged for the generated traffic.
-   If you upload data to HBR, you are not charged for the generated traffic.

|Pay-as-you-go|The standard pricing scheme for HBR is used for all regions. For more information, see [Hybrid Backup Recovery \(HBR\) Pricing](https://www.alibabacloud.com/product/hybrid-backup-recovery/pricing). |
|Cross-region replication traffic|When you restore data backed up in HBR from a region to another, you may need to replicate the data from a backup vault to an image vault. In this case, you are charged for the generated traffic.|Pay-as-you-go|The standard pricing scheme for HBR is used for all regions. For more information, see [Hybrid Backup Recovery \(HBR\) Pricing](https://www.alibabacloud.com/product/hybrid-backup-recovery/pricing). |

**Note:** HBR provides a one-month free trial free of charge. This allows you to back up each Apsara File Storage NAS file system and Object Storage Service \(OSS\) bucket. During the trial period, you are also not charged for the backup vault.

