# Overview

This topic describes the supported versions, operating systems, and features of database instances that are deployed on Elastic Compute Service \(ECS\) instances when these database instances are backed up.

## Oracle

The following table describes the supported versions, operating systems, and features of Oracle instances.

|Database type|Supported version|Supported operating system|Minimum backup granularity|Feature|
|Full Backup|Incremental Backup|Log Backup \(Scheduled Backup\)|Log Backup \(Continuous Backup\)|
|:-----------:|-----------------|--------------------------|--------------------------|-------|
|:---------:|------------------|-------------------------------|--------------------------------|
|Oracle|9i|SUSE 9.3, RHEL 4, RHEL 5, SLES 9, and CentOS 4.5|Tablespace|Supported|Supported|Supported|Supported|
|10g|RHEL 9, RHEL 4, RHEL 5, CentOS 4.6, SUSE Linux Enterprise Server 11 SP4, and RHEL 6.5|Tablespace|Supported|Supported|Supported|Supported|
|11g|RHEL 5, RHEL 6, CentOs 6.4, RHEL 6.5, CentOS 6.5, Oracle Enterprise Linux 6.7, RHEL 7, Windows Server 2008 R2, Windows Server 2012 R2, and RHEL 6.0|Tablespace|Supported|Supported|Supported|Supported|
|12c|Windows Server 2008 R2, RHEL 6.5, RHEL 6.5, and RHEL 7.5|Tablespace|Supported|Supported|Supported|Supported|
|18c|RHEL 7.0 and Windows Server 2008 R2|Tablespace|Supported|Supported|Supported|Supported|
|19c|Oracle Enterprise Linux7.0|Tablespace|Supported|Supported|Supported|Supported|

## Oracle RAC

The following table describes the supported versions, operating systems, and features of Oracle Real Application Clusters \(RAC\) instances.

|Database type|Supported version|Supported operating system|Minimum backup granularity|Feature|
|Full Backup|Incremental Backup|Log Backup \(Scheduled Backup\)|Log Backup \(Continuous Backup\)|
|:-----------:|-----------------|--------------------------|--------------------------|-------|
|:---------:|------------------|-------------------------------|--------------------------------|
|Oralce RAC|9i|SUSE 9.3 and RHEL|Tablespace|Supported|Supported|Supported|Supported|
|10g|RHEL 5 and Windows Server 2008 R2|Tablespace|Supported|Supported|Supported|Supported|
|11g|Windows Server 2008 R2, RHEL 5, Oracle Enterprise Linux 6.4, RHEL 6.5, and iSoft Server OS V3.0|Tablespace|Supported|Supported|Supported|Supported|
|12c|CentOS 6, RHEL 6.5, Windows Server 2008 R2, CentOS 6.7, and Oracle Enterprise Linux 6|Tablespace|Supported|Supported|Supported|Supported|
|18c|Windows 2008 R2|Tablespace|Supported|Supported|Supported|Supported|
|19c|RHEL 7.6|Tablespace|Supported|Supported|Supported|Supported|

## Oracle Data Guard

The following table describes the supported versions, operating systems, and features of Oracle Data Guard instances.

|Database type|Supported version|Supported operating system|Minimum backup granularity|Feature|
|Full Backup|Incremental Backup|Log Backup \(Scheduled Backup\)|Log Backup \(Continuous Backup\)|
|:-----------:|-----------------|--------------------------|--------------------------|-------|
|:---------:|------------------|-------------------------------|--------------------------------|
|Oracle Data Guard|11g|CentOS 6.4, CentOS 6.5, RHEL 6, and Windows Server 2008 R2|Tablespace|Supported|Supported|Supported|Supported|
|12c|Oracle Enterprise Linux6|Tablespace|Supported|Supported|Supported|Supported|

## MySQL

The following table describes the supported versions, operating systems, and features of MySQL instances.

|Database type|Supported version|Supported operating system|Minimum backup granularity|Feature|
|Full Backup|Incremental Backup|Log Backup \(Scheduled Backup\)|Log Backup \(Continuous Backup\)|
|:-----------:|-----------------|--------------------------|--------------------------|-------|
|:---------:|------------------|-------------------------------|--------------------------------|
|MySQL|4.1|CentOS 4.6, RHEL 6.5, and SUSE Linux Enterprise Server 11 SP4|Instance|Supported|Supported|Supported|Supported|
|5|RHEL 5.0, RHEL 6.0, Ubuntu 12.10, SLES 10, Ubuntu 11.10, and Neokylin 6.0|Instance|Supported|Supported|Supported|Supported|
|5.0|RHEL 5, RHEL 6.5, and SUSE Linux Enterprise Server 11 SP4|Instance|Supported|Supported|Supported|Supported|
|5.1|RHEL 6.5, SUSE Linux Enterprise Server 11 SP4, RHEL 6.5, and RHEL 6.0|Instance|Supported|Supported|Supported|Supported|
|5.4|RHEL 6.5 and SUSE Linux Enterprise Server 11 SP4|Instance|Supported|Supported|Supported|Supported|
|5.5|Ubuntu 12.04, Ubuntu 14.04, Debian 7.8, Debian 8.3, CentOS 6.0, and RHEL 6.5|Instance|Supported|Supported|Supported|Supported|
|5.6|RHEL 5.0, RHEL 6.0, RHEL 6.5, Ubuntu 14.04, CentOS 6.0, and CentOS 7.2|Instance|Supported|Supported|Supported|Supported|
|5.7|RHEL 6.0, RHEL 7.0, CentOS 7.0, RHEL 6.5, Ubuntu 16.04, CentOS 7.2, RHEL 7.0, and Neokylin 7.0|Instance|Supported|Supported|Supported|Supported|
|8.0|CentOS 6.7, RHEL 6.5, and CentOS 7.0|Instance|Supported|Supported|Supported|Supported|

## SQL Server

The following table describes the supported versions, operating systems, and features of SQL Server instances.

|Database type|Supported version|Supported operating system|Minimum backup granularity|Feature|
|Full Backup|Incremental Backup|Log Backup \(Scheduled Backup\)|Log Backup \(Continuous Backup\)|
|:-----------:|-----------------|--------------------------|--------------------------|-------|
|:---------:|------------------|-------------------------------|--------------------------------|
|SQL Server|2005|Windows 2008 R2 SP1|Instance|Supported|Supported|Supported|Unsupported|
|2008|Windows Server 2008 R2 and Windows Server 2008 R2 Service Pack 1|Instance|Supported|Supported|Supported|Unsupported|
|2008 R2|Windows 2008 R2|Instance|Supported|Supported|Supported|Unsupported|
|2012|Windows 2012 RC|Instance|Supported|Supported|Supported|Unsupported|
|2014|Windows Server 2008 R2 Service Pack 1 and Windows 2016|Instance|Supported|Supported|Supported|Unsupported|
|2016 \(RTM\)|Windows 2012 R2|Instance|Supported|Supported|Supported|Unsupported|
|2017|Windows 2012 and Windows 2016|Instance|Supported|Supported|Supported|Unsupported|
|2019|Windows 2016|Instance|Supported|Supported|Supported|Unsupported|

## SQL Server Always On

The following table describes the supported versions, operating systems, and features of SQL Server Always On instances.

|Database type|Supported version|Supported operating system|Minimum backup granularity|Feature|
|Full Backup|Incremental Backup|Log Backup \(Scheduled Backup\)|Log Backup \(Continuous Backup\)|
|:-----------:|-----------------|--------------------------|--------------------------|-------|
|:---------:|------------------|-------------------------------|--------------------------------|
|SQL Server Always On|2012, 2016, and 2017|Windows 2012 R2|Instance|Supported|Supported|Supported|Unsupported|

