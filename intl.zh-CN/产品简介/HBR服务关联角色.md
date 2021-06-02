HBR服务关联角色 
==============================

本文介绍混合云备份HBR服务包含四种服务关联角色，分别为AliyunServiceRoleForHbrEcsBackup、AliyunServiceRoleForHbrOssBackup、AliyunServiceRoleForHbrNasBackup和AliyunServiceRoleForHbrCsgBackup，以及如何删除上述角色。

背景信息 
-------------------------

HBR服务关联角色是指HBR在某些情况下，为了完成自身的某个功能，需要获取其他云服务的访问权限而提供的RAM角色。更多关于服务关联角色的信息请参见[服务关联角色](/intl.zh-CN/角色管理/服务关联角色.md)。

HBR需要访问云服务器ECS、专有网络VPC、对象存储OSS、文件存储NAS和云存储网关CSG等云服务的资源时，可通过自动创建的HBR服务关联角色获取对应的访问权限。

* HBR ECS备份功能需要访问云服务器ECS和专有网络VPC云服务的资源时，可通过自动创建的HBR服务关联角色AliyunServiceRoleForHbrEcsBackup获取访问权限。

  

* HBR OSS备份功能需要访问对象存储OSS云服务的资源时，可通过自动创建的HBR服务关联角色AliyunServiceRoleForHbrOssBackup获取访问权限。

  

* HBR NAS备份功能需要访问文件存储NAS云服务的资源时，可通过自动创建的HBR服务关联角色AliyunServiceRoleForHbrNasBackup获取访问权限。

  

* HBR云存储网关备份功能需要访问云存储网关CSG云服务的资源时，可通过自动创建的HBR服务关联角色AliyunServiceRoleForHbrCsgBackup获取访问权限。

  




权限说明 
-------------------------

HBR服务关联角色需具备以下云服务的访问权限。

* 通过AliyunServiceRoleForHbrEcsBackup获取访问ECS的权限。

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

  

  

* 通过AliyunServiceRoleForHbrEcsBackup获取访问VPC的权限。

      {
            "Action": [
              "vpc:DescribeVpcs",
              "vpc:DescribeVSwitches"
            ],
            "Resource": "*",
            "Effect": "Allow"
          }

  

  

* 通过AliyunServiceRoleForHbrOssBackup获取访问OSS的权限。

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

  

  

* 通过AliyunServiceRoleForHbrNasBackup获取访问NAS的权限。

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

  

  

* 通过AliyunServiceRoleForHbrCsgBackup获取访问CSG的权限。

      {
            "Action": [
              "hcs-sgw:DescribeGateways"
            ],
            "Resource": "*",
            "Effect": "Allow"
          }

  




删除服务关联角色 
-----------------------------

假设您在使用了HBR ECS备份功能后，出于安全考虑，需要删除HBR服务关联角色AliyunServiceRoleForHbrEcsBackup。
**注意**

删除AliyunServiceRoleForHbrEcsBackup前，请确保当前账号下没有备份仓库，否则删除失败。

删除AliyunServiceRoleForHbrEcsBackup的操作步骤如下：

1. 登录[RAM控制台](http://ram.console.aliyun.com)。

   

2. 在左侧导航栏中单击 **RAM角色管理。**

   

3. 在 **RAM角色** 管理页面的搜索框中，输入AliyunServiceRoleForHbrEcsBackup，自动搜索到名称为AliyunServiceRoleForHbrEcsBackup的RAM角色。

   

4. 在右侧 **操作** 列，单击 **删除** 。

   

5. 在 **删除RAM角色** 对话框，单击 **确定** 。

   




删除AliyunServiceRoleForHbrOssBackup、AliyunServiceRoleForHbrNasBackup和AliyunServiceRoleForHbrCsgBackup等服务关联角色与删除AliyunServiceRoleForHbrEcsBackup服务关联角色步骤类似，仅需替换为对应的RAM角色即可。
