# Limits

This topic describes the limits for Elastic Compute Service \(ECS\) disaster recovery, including the limits on operating systems, architectures, databases, and applications.

## Operating systems

The following table lists the operating systems that support ECS disaster recovery.

|Operating system|Version|
|:---------------|:------|
|Windows Server|2008 R2, 2012, 2012 R2, and 2016|
|Linux|-   Red Hat Enterprise Linux 7.0~7.8
-   Red Hat Enterprise Linux 6.0~6.10
-   CentOS 7.0~7.8
-   CentOS 6.0~6.10

**Note:** Disaster recovery is supported for ECS instances that run CentOS 6.x 64-bit operating systems. To implement disaster recovery for ECS instances that run CentOS 6.x 32-bit operating systems, submit a ticket.

-   SuSE Linux Enterprise Server 12.0~12.3

**Note:** Disaster recovery is supported for ECS instances that run SuSE Linux Enterprise Server 12.x 64-bit operating systems. To implement disaster recovery for ECS instances that run SuSE Linux Enterprise Server 12.x 32-bit operating systems, submit a ticket. If SUSE Linux Enterprise Server 12.1 runs on a VMware virtual machine, a black screen appears after the virtual machine is restarted. This is caused by system errors of the operating system, irrelevant to ECS disaster recovery. |

**Note:** Disaster recovery for ECS instances that run other Linux distributions will be supported in the near future.

## Architectures

ECS disaster recovery is implemented based on the disk-level data replication. It is independent of the underlying architecture. The following table lists the platforms that support ECS disaster recovery. Support for more architectures are under development. For more information, submit a ticket.

|Architecture|Supported version|
|:-----------|:----------------|
|Physical machine|Full support|
|Hyper-V|2008 R2, 2012, and 2012 R2|
|vSphere|5.5, 6.0, and 6.5|

## Databases and applications

The replication technology of ECS disaster recovery can be applied to all types of databases and applications.

In most cases, automated scripts are required for various applications to keep consistency among updates. When you implement ECS disaster recovery, you can use the available tools that are provided by Alibaba Cloud along with scripts to guarantee smooth recovery of applications.

## Other limits

ECS disaster recovery also has the following limits:

-   If the size of a physical volume where the system disk of an ECS instance resides exceeds 2 TB, you cannot perform a full restoration on the ECS instance.
-   A single physical volume of a data disk cannot exceed 32 TB.

