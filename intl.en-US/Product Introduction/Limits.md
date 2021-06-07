# Limits

This topic describes the limits of Hybrid Backup Recovery \(HBR\).

## Back up files

-   Windows clients support Volume Shadow Copy Service \(VSS\). You can create only one single VSS snapshot at a time.
-   If a file is being modified by other applications but the applications have read permissions on the file during a backup job, an incomplete backup occurs. You must ensure the integrity of backup data at the application layer.
-   If one or more files are locked by processes or the permissions on the files are disabled during a backup job, an incomplete backup occurs. The status of the backup job is displayed as partially completed when the job ends.

## VMware VM backup

-   You must install a VCenter Web Client in version 5.5, 6.0, 6.5, or 6.7.
-   A VCenter client and ESXi hypervisor must allow access from a backup gateway by using a fully qualified domain name \(FQDN\) or an IP address.
-   If you want to back up a VM, you cannot create snapshots for the VM. Otherwise, you will be prompted the following message when you select the VM: You cannot back up the virtual machine because you have already created a snapshot. If a snapshot exists, you must delete it before you can back up the VM.
-   You cannot back up VMs that have SCSI devices because vSphere VMs do not support shared SCSI devices.
-   The name of a VM that you want to back up cannot contain the following characters.

    \` ^ ~ = ; ! / \( \) \[ \] \{ \} @ $ \\ & \# % +

-   If you use Changed Block Tracking \(CBT\) to perform an incremental backup for a VM, the backup fails in the following scenarios:
    -   The hardware version of the VM is earlier than version 7.
    -   CBT is disabled on the VM.
    -   The disk of the VM uses raw device mapping \(RDM\) in physical compatibility mode.
    -   The disk mode of the VM is independent\_persistent or independent\_nonpersistent.

## Back up data from an SAP HANA database on an ECS instance

You can install only one SAP HANA instance on an ECS instance. Otherwise, you will be prompted the following error message: Failed to install SAP HANA.

## Back up data from an SQL Server database on an ECS instance

You can use HBR to back up data from the following supported versions of SQL Server databases.

|Version|Full backup|Differential backup|Log backup|Data restoration|
|:------|:----------|:------------------|:---------|:---------------|
|SQL Server 2008R2|Yes|Yes|Yes|Yes|
|SQL Server 2012|Yes|Yes|Yes|Yes|
|SQL Server 2014|Yes|Yes|Yes|Yes|
|SQL Server 2016|Yes|Yes|Yes|Yes|
|SQL Server 2017|Yes|Yes|Yes|Yes|

