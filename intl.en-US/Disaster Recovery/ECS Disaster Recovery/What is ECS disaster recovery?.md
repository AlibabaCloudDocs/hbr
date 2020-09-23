# What is ECS disaster recovery?

Elastic Compute Service \(ECS\) disaster recovery is a scheme that Alibaba Cloud Hybrid Backup Recovery \(HBR\) provides to serve the needs of key enterprise applications and guarantee business continuity. It features disaster recovery with a second-level or minute-level recovery point objective \(RPO\) and recovery time objective \(RTO\).

## Scenarios

ECS Disaster Recovery can be used across regions and zones in the following two scenarios:

-   The primary and disaster recovery systems are deployed in different regions of Alibaba Cloud. When the primary system encounters a failure, workloads are switched to the disaster recovery system. By deploying the primary and disaster recovery systems in different regions, ECS disaster recovery provides a highly reliable disaster recovery service. This service features a recovery point objective \(RPO\) of as low as 1 minute and a recovery time objective \(RTO\) of as low as 15 minutes. Cross-region disaster recovery can guarantee business continuity and effectively avoid system failures that are caused by regional disasters. For more information, see [Cross-region disaster recovery](/intl.en-US/Disaster Recovery/ECS Disaster Recovery/Cross-region disaster recovery.md).
-   When a production site encounters force majeure events such as a fire disaster or an earthquake or equipment failures such as software or hardware failures, applications may fail to run in a certain period. In this case, ECS disaster recovery provides cross-zone disaster recovery for you to back up application data and run applications in another zone to deal with failures in a single zone at the required RTO and RPO. For more information, see [Cross-zone disaster recovery](/intl.en-US/Disaster Recovery/ECS Disaster Recovery/Cross-zone disaster recovery.md).

## Features

ECS disaster recovery provides the following features:

-   Application data replication in real time: ECS disaster recovery can monitor data changes in disks of operating systems and ECS instances, capture changed data, and then synchronize such data to disaster recovery sites in real time. In this way, it provides real-time protection for your data with a second-level or minute-level RPO.
-   Quick application running in another region or zone: You can quickly run applications in another region or zone within minutes.
-   Disaster recovery drills without business interruption: You can perform disaster recovery drills on application servers deployed on the cloud at any time to verify that the business can be recovered. Disaster recovery drills do not affect the source production environment or interrupt data replication.

## Benefits

ECS disaster recovery has the following benefits:

-   Cost-effective: ECS disaster recovery consumes only disk resources and a small number of computing resources. It only requires software authorization such as authorization from operating and application systems during disaster recovery.
-   Easy to use: You can start data replication for disaster recovery, perform disaster recovery drills, and restore data in one click without deploying a disaster recovery center.
-   Highly reliable: ECS disaster recovery can guarantee continuous data replication and resumable upload even when errors occur, for example, the source server is overloaded or restarted, the disaster recovery gateway is restarted upon power-off, or the data replication link encounters network jitter. Alibaba Cloud guarantees the reliability of cloud data.
-   Highly secure: ECS disaster recovery uses the Advanced Encryption Standard \(AES\) 256-bit algorithm and HTTPS to encrypt your data and guarantee end-to-end security.
-   Verifiable: You can perform disaster recovery drills on cloud systems at any time without affecting the production system. This overcomes the difficulties in verifying the disaster recovery system.

