# 开启Oralce归档模式

Oracle数据库的归档模式默认为关闭状态，需将其开启才能进行HBR备份。本文介绍开启Oracle数据库归档模式的操作方法。

1.  以sysdba身份登录Oracle数据库。

2.  执行SQL命令`ARCHIVE LOG LIST`查询当前数据库的归档状态。

    返回示例如下。

    ```
    Database log mode              No Archive Mode  #非存档模式
    Automatic archival             Disabled
    Archive destination            USE_DB_RECOVERY_FILE_DEST  
    Oldest online log sequence     1    
    Current log sequence           2  
    ```

    **说明：** 若`Database log mode`参数返回`Archive Mode #存档模式`，则表示当前已开启Oracle归档模式。

3.  由于无法在`OPEN`状态下开启归档模式，需要执行SQL命令`SHUTDOWN IMMEDIATE`关闭数据库。

    **说明：** 请管理员在非业务高峰时期操作。

4.  执行SQL命令`STARTUP MOUNT`启动数据库至MOUNT状态。

5.  执行SQL命令`ALTER DATABASE ARCHIVELOG`启动归档模式。

6.  再次执行SQL命令`ARCHIVE LOG LIST`查询归档状态。

    返回示例如下。

    ```
    Databaselog mode             Archive Mode #存档模式
    Automatic archival           Enabled 
    Archive destination          USE_DB_RECOVERY_FILE_DEST 
    Oldest online log sequence  1
    Next log sequence to archive 2 
    Currentlog sequence         2
    ```

    **说明：** 开启后，Oracle默认的日志归档路径为闪回恢复区（$ORACLE\_BASE/fast\_recovery\_area），该目录默认仅有4 GB的空间，同时也是备份文件和闪回日志的默认路径。为避免该磁盘空间不足导致数据库服务异常，您可按需调整该目录的空间大小或修改日志归档路径。

7.  执行SQL命令`ALTER DATABASE OPEN`启动数据库。


