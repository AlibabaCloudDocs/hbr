# FAQ {#concept_62831_zh .concept}

## How much data can I back up by using Hybrid Backup Recovery \(HBR\)? { .section}

The storage space of Alibaba Cloud vaults is unlimited. The vaults can be expanded to store large amounts of backup data.

## How long does it take to back up data by using HBR? { .section}

It depends on factors, such as the total size of data, the total number of files, and the network bandwidth. If the network bandwidth is stable, the time it takes to complete a backup job is calculated as follows: The total size of data/The network bandwidth = The required time.

## What types of data can I back up by using HBR? { .section}

For more information, see [What is Hybrid Backup Recovery](../../../../intl.en-US/Product Introduction/What is Hybrid Backup Recovery?.md).

## Does HBR encrypt backup data that is stored in the cloud? { .section}

Yes, all backups in HBR are protected by using AES-256 encryption.

## Does HBR support data compression and data deduplication? { .section}

Yes, the compression and deduplication ratio depend on the type of source data. The maximum ratio is 30:1.

## Does HBR support incremental backups? { .section}

Yes, successive copies of the data only contain the changes since the previous backup copy is created.

## What can I do if I forget my logon password for a client? { .section}

You can re-download a client from the HBR console, install the client, log on to the client, and enter a new password on the registration page.

## How can I create a backup plan? { .section}

You need to first create backup policies. When creating a backup plan, you need to select the location of a data source and the required policy. After you change a backup policy, the change will be synchronized to the associated backup plan. If you delete a backup policy, the related backup job is also deleted. However, you can continue using completed backups.

## Is actual data backed up when I back up symbolic links? { .section}

No. Linux symbolic links are similar to Windows shortcuts. When you back up symbolic links, only links are backed up rather than the linked data.

## How can I view a failure cause for a backup or restore job? { .section}

Move the pointer over the Failed status to view the cause of the failure.

## Does Hybrid Backup Recovery \(HBR\) support a remote data restoration? { .section}

Yes. When a failure occurs on a protected host, you can install a backup client on another host. Then, you can download a certificate that is used to restore the protected host from the HBR console. You can use the certificate to register an account and log on to the backup client. Locate the required backup on the **Backups** list to restore data.

