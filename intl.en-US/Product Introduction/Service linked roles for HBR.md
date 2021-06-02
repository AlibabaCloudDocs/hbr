Service linked roles for HBR 
=================================================

This topic describes four service linked roles for Hybrid Backup Recovery (HBR): AliyunServiceRoleForHbrEcsBackup, AliyunServiceRoleForHbrOssBackup, AliyunServiceRoleForHbrNasBackup, and AliyunServiceRoleForHbrCsgBackup. This topic also describes how to delete these RAM roles.

Background information 
-------------------------------------------

HBR needs to access other Alibaba Cloud services to implement a feature. In this case, HBR must create and assume service linked roles to obtain required permissions. For more information, see [Service linked roles](/intl.en-US/RAM Role Management/Service-linked roles.md).

When HBR requires access to Elastic Compute Service (ECS), Virtual Private Cloud (VPC), Object Storage Service (OSS), Apsara File Storage NAS, or Cloud Storage Gateway (CSG), the corresponding service linked role is automatically created.

* When the ECS backup features of HBR require access to ECS and VPC, the AliyunServiceRoleForHbrEcsBackup role is automatically created.

  

* When the OSS backup feature of HBR requires access to OSS, the AliyunServiceRoleForHbrOssBackup role is automatically created.

  

* When the NAS backup feature of HBR requires access to NAS, the AliyunServiceRoleForHbrNasBackup role is automatically created.

  

* When the CSG backup feature of HBR requires access to CSG, the AliyunServiceRoleForHbrCsgBackup role is automatically created.

  




Permissions of service linked roles 
--------------------------------------------------------

This section lists the permission policy that is attached to each service linked role.

* The policy that is attached to the AliyunServiceRoleForHbrEcsBackup role includes the permissions on ECS. After HBR assumes the role, HBR obtains the permissions on ECS.

       {
            "Action": [
              "ecs:RunCommand",
              "ecs:CreateCommand",
              "ecs:InvokeCommand",
              "ecs:DeleteCommand",
              "ecs:DescribeCommands",
              "ecs:StopInvocation",
              "ecs:DescribeInvocationResults",
              "ecs:DescribeCloudAssistantStatus",
              "ecs:DescribeInstances",
              "ecs:DescribeInstanceRamRole",
              "ecs:DescribeInvocations"
            ],
            "Resource": "*",
            "Effect": "Allow"
          },
          {
            "Action": [
              "ecs:AttachInstanceRamRole",
              "ecs:DetachInstanceRamRole"
            ],
            "Resource": [
              "acs:ecs:*:*:instance/*",
              "acs:ram:*:*:role/aliyunecsaccessinghbrrole"
            ],
            "Effect": "Allow"
          },
          {
            "Action": [
              "ram:GetRole",
              "ram:GetPolicy",
              "ram:ListPoliciesForRole"
            ],
            "Resource": "*",
            "Effect": "Allow"
          },
          {
            "Action": [
              "ram:PassRole"
            ],
            "Resource": "*",
            "Effect": "Allow",
            "Condition": {
              "StringEquals": {
                "acs:Service": [
                  "ecs.aliyuncs.com"
                ]
              }
            }
          },
          {
            "Action": [
              "ecs:DescribeSecurityGroups",
              "ecs:DescribeImages",
              "ecs:CreateImage",
              "ecs:DeleteImage",
              "ecs:DescribeSnapshots",
              "ecs:CreateSnapshot",
              "ecs:DeleteSnapshot",
              "ecs:DescribeSnapshotLinks",
              "ecs:DescribeAvailableResource",
              "ecs:ModifyInstanceAttribute",
              "ecs:CreateInstance",
              "ecs:DeleteInstance",
              "ecs:AllocatePublicIpAddress",
              "ecs:CreateDisk",
              "ecs:DescribeDisks",
              "ecs:AttachDisk",
              "ecs:DetachDisk",
              "ecs:DeleteDisk",
              "ecs:ResetDisk",
              "ecs:StartInstance",
              "ecs:StopInstance",
              "ecs:ReplaceSystemDisk",
              "ecs:ModifyResourceMeta"
            ],
            "Resource": "*",
            "Effect": "Allow"
          }

  

  

* The policy that is attached to the AliyunServiceRoleForHbrEcsBackup role includes the permissions on VPC. After HBR assumes the role, HBR obtains the permissions on VPC.

      {
            "Action": [
              "vpc:DescribeVpcs",
              "vpc:DescribeVSwitches"
            ],
            "Resource": "*",
            "Effect": "Allow"
          }

  

  

* The policy that is attached to the AliyunServiceRoleForHbrOssBackup role includes the permissions on OSS. After HBR assumes the role, HBR obtains the permissions on OSS.

      {
            "Action": [
              "oss:ListObjects",
              "oss:HeadBucket",
              "oss:GetBucket",
              "oss:GetBucketAcl",
              "oss:GetBucketLocation",
              "oss:GetBucketInfo",
              "oss:PutObject",
              "oss:CopyObject",
              "oss:GetObject",
              "oss:AppendObject",
              "oss:GetObjectMeta",
              "oss:PutObjectACL",
              "oss:GetObjectACL",
              "oss:PutObjectTagging",
              "oss:GetObjectTagging",
              "oss:InitiateMultipartUpload",
              "oss:UploadPart",
              "oss:UploadPartCopy",
              "oss:CompleteMultipartUpload",
              "oss:AbortMultipartUpload",
              "oss:ListMultipartUploads",
              "oss:ListParts"
            ],
            "Resource": "*",
            "Effect": "Allow"
          }

  

  

* The policy that is attached to the AliyunServiceRoleForHbrNasBackup role includes the permissions on NAS. After HBR assumes the role, HBR obtains the permissions on NAS.

      {
            "Action": [
              "nas:DescribeFileSystems",
              "nas:CreateMountTargetSpecial",
              "nas:DeleteMountTargetSpecial",
              "nas:CreateMountTarget",
              "nas:DeleteMountTarget",
              "nas:DescribeMountTargets",
              "nas:DescribeAccessGroups"
            ],
            "Resource": "*",
            "Effect": "Allow"
          }

  

  

* The policy that is attached to the AliyunServiceRoleForHbrCsgBackup role includes the permissions on CSG. After HBR assumes the role, HBR obtains the permissions on CSG.

      {
            "Action": [
              "hcs-sgw:DescribeGateways"
            ],
            "Resource": "*",
            "Effect": "Allow"
          }

  




Delete a service linked role 
-------------------------------------------------

You may need to delete a service linked role. For example, if you no longer need to use the ECS backup features, you can delete the AliyunServiceRoleForHbrEcsBackup role to ensure security.
**Notice**

Make sure that no backup vaults exist under the Alibaba Cloud account before you delete the AliyunServiceRoleForHbrEcsBackup role. Otherwise, the service linked role cannot be deleted.

To delete the AliyunServiceRoleForHbrEcsBackup role, perform the following steps:

1. Log on to the [RAM console](http://ram.console.aliyun.com).

   

2. In the left-side navigation pane, click **RAM Roles** .

   

3. On the **RAM Roles** page, enter AliyunServiceRoleForHbrEcsBackup in the search box to find the role.

   

4. In the **Actions** column, click **Delete** .

   

5. In the **Delete RAM Role** dialog box, click **OK** .

   




If you want to delete the AliyunServiceRoleForHbrOssBackup, AliyunServiceRoleForHbrNasBackup, or AliyunServiceRoleForHbrCsgBackup role, enter the role name instead of AliyunServiceRoleForHbrEcsBackup in the search box.
