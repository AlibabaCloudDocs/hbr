# Restrictions {#concept_89022_zh .concept}

## File Backup Restrictions {#section_cm5_hdy_pfb .section}

-   Volume Snapshot Service \(VSS\) is supported on Windows clients. Only one snapshot can be created at a time.

-   If during backup a file that has read permission is being modified by other applications, then the backup status is Partial Complete. The integrity of application data to be backed up needs to be guaranteed.

-   If during backup a file is occupied by other processes or does not have read permission, then the backup status is Partial Complete.

-   
## Virtual machine backup restrictions { .section}

-   The client to be backed up must be deployed using vSphere Web Client of version 5.5, 6.0, or 6.5.

-   The backup gateway must allow access for VCenter and ESXi that manage virtual machine backups through Fully Qualified Domain Names \(FQDNs\) and IP addresses.

-   Virtual machines to be backed up cannot have snapshots. If you select a virtual machine that has snapshots, the following information is prompted: The virtual machine has snapshots and cannot be backed up. If snapshots exist, delete them.

-   Virtual machines with SCSI devices cannot be backed up because shared SCSI devices are not supported by VSphere VM snapshots.

-   The name of the virtual machine that needs to be backed up cannot contain the following characters:

    \` ^ ~ = ; ! / \( \[ \] \{ \} @ $ \\ & \# % +

-   Incremental backup based on Changed Block Tracking \(CBT\) is not supported in the following scenarios:

    -   The hardware version of the virtual machine is earlier than 7.

    -   CBT is disabled on the virtual machine.

    -   The disk mode of the virtual machine is a physical compatibility mode of RDM.

    -   The disk mode of the virtual machine is independent\_persistent or independent\_nonpersistent.


