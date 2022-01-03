# 各种类型的备份

> 原文:[https://www.geeksforgeeks.org/various-types-of-backup/](https://www.geeksforgeeks.org/various-types-of-backup/)

先决条件–[备份安全措施](https://www.geeksforgeeks.org/backup-security-measures/)
备份和恢复策略对于大多数操作系统来说至关重要。许多系统管理员使用分层备份计划。

**各种类型的备份:**

1.  **Full backup –**
    A full backup is a technique for backup where all documents and envelopes chosen for backup are upheld up. At the point when backup is run later, full rundown of documents will be upheld up once more. The upside of this backup is that recuperation is snappy and simple on grounds that total rundown of documents is put away unfailingly.

    缺点是每次备份运行都需要大量的精力，因为文档的整个纲要都要重复一次。与开发或分离备份相比，完整备份占用大量额外空间。

2.  **Incremental backup –**
    Developing backup is backup of all progressions made since last backup. With expanding backup, full backup happens first and following backup runs progressions produced using last backup. The outcome is quick backup, and afterward full backup for every backup run. Extra room use is extremely low contrasted with full backup and distinction with backup is little. Reestablishing is slower than full backup and differential backup.
3.  **Differential backup –**
    Differential backup is backup of all progressions made since last full backup. With differential backup, full backup is done first and resulting backup runs progressions produced using last full backup. The outcome is an exceptionally quick backup, and afterward full backup for every backup run. Extra room utilization is low contrasted with full backup, yet again with expanding backup. Reclamation’s are slower than full backups, yet are typically quicker, with expanding backups later.
4.  **Mirror Backup –**
    Mirror Backup As the name suggests, mirror of source is being supported up. With Mirror Backup, when record is erased from source, that document is inevitably erased in Mirror Backup too. Hence, Mirror Backup ought to be utilized with alert as record decimated unintentionally or infection and Mirror Backup can likewise be demolished.
5.  **Full PC backup or full PC backup –**
    In this backup, it’s not supported up close to home documents, however whole picture of PC’s hard drive, which is backup. With full PC backup, you can reestablish PC hard drive to its careful state when sponsored up. With full PC backup, you can not just reestablish work records, pictures, recordings, and sound documents, yet in addition reestablish working frameworks, equipment drivers, framework records, libraries, programs, messages, and so on.

6.  **Local backup –**
    Local backup is any kind of backup where capacity medium is kept close within reach or in structure with source. This can be backup of second inward hard drive, connected outer hard drive, CD/DVD-More, or [Network Attached Storage (NAS)](https://www.geeksforgeeks.org/network-attached-storage-in-dbms/). Local backups shield an advanced substance from hard drive disappointments and infection assaults. They give assurance or dispense with botches made unintentionally. Backups are consistently close by and they are quick and helpful to reestablish.
7.  **Offsite backup –**
    At the point when backup stockpiling medium is set in an alternate topographical area from source, it is called offsite backup. Backups should be possible locally from outset, however, in wake of moving capacity media to another area, it turns into an offsite backup. Instances of offsite backup are moving backup media or hard drives at home, in another place of business, or in bank safe store box.

    Notwithstanding similar insurance given by local backups, offsite backups give extra assurance against burglary, fire, flood, and other cataclysmic events. Setting backup media in following room isn’t considered offsite backup as it doesn’t give backup security against robbery, fire, flood, and other cataclysmic events.
8.  **Online backup –**
    These are backups, made constantly or over and over through capacity or capacity media, which are constantly associated with source being upheld up. Capacity media is as rule off-website and associated with backup source by means of system or Internet association. It doesn’t include human mediation to connect drives and capacity media to run backups. Numerous business server farms currently offer it as membership administration to clients. Capacity server farms are found away from source and are safely sent from information source to put-away farm through Internet.
9.  **Remote backup –**
    Remote backup is type of offsite backup that fluctuates relying upon whether you can utilize, reestablish, or keep up backups situated at your base area or somewhere else. You shouldn’t be present in backup storeroom to make backup. For instance, keeping your backup hard drive in your bank safe store box isn’t viewed as remote backup. You can’t do this without making trip to bank. Online backup is additionally commonly considered as remote backup.
10.  **Cloud backup –**
    The term is frequently utilized with online backup and remote backup. This is place information is sponsored up to help storerooms associated with Internet. With appropriate login accreditation’s, that backup can be gotten to or reestablished from another PC with Internet.
11.  **Ftp 备份–**
    这是一种备份，通过[文件传输协议(FTP)](https://www.geeksforgeeks.org/file-transfer-protocol-ftp-in-application-layer/) 对互联网上的 Ftp 工作人员进行备份。FTP 工作人员通常位于远离源信息的业务服务器场中。当 FTP 工作人员在备用区域时，这是另一种类型的异地备份。