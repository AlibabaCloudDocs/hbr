# Limits {#concept_89022_zh .concept}

## Back up files {#section_cm5_hdy_pfb .section}

-   Windows clients support Volume Shadow Copy Service \(VSS\). You can only create a single VSS snapshot at a time.

-   An incomplete backup occurs if one or more files are changed by other applications during the backup job. The status of the backup job is displayed as partially completed when the backup job is complete. You must ensure the integrity of data in each backup job.

-   During a backup job, if one or more files are locked by processes or cannot be read by the backup job, this results in an incomplete backup of data. The status of the backup job is displayed as partially completed when the backup job is complete.


## Back up virtual machines {#section_jn5_286_hh5 .section}

-   You must install a VCenter Web Client \(5.5, 6.0, or 6.5\) on each virtual machine for which a backup is to be created.

-   A VCenter client and ESXi hypervisor must allow access from a backup gateway by using a fully qualified domain name \(FQDN\) or an IP address.

-   Snapshots cannot exist if you want to back up a virtual machine. Otherwise, you will be prompted a message when selecting a virtual machine: You cannot back up the virtual machine because you have already created a snapshot of the virtual machine. If a snapshot exists, you can delete it.

-   You cannot back up virtual machines that have SCSI devices because vSphere virtual machines do not support shared SCSI devices.

-   The name of a virtual machine to be backed up cannot contain the following characters.

    \` ^ ~ = ; ! / \( \[ \] \{ \} @ $ \\ & \# % +

-   When you attempt to use Changed Block Tracking \(CBT\) to perform an incremental backup for a virtual machine, the backup cannot be performed in the following scenarios:

    -   The hardware version of the virtual machine is earlier than version 7.

    -   CBT is disabled on the virtual machine.

    -   The disk of the virtual machine uses raw device mapping \(RDM\) in physical compatibility mode.

    -   The disk mode of the virtual machine is independent\_persistent or independent\_nonpersistent.


