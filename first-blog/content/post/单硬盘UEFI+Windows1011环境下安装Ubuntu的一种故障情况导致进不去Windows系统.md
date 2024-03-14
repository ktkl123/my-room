# 单硬盘UEFI+Windows10/11环境下安装Ubuntu的一种故障情况导致进不去Windows系统

故障情况还原：单硬盘UEFI+Windows10/11环境下安装Ubuntu后，从Ubuntu启动菜单选择Windows11，会显示 错误：未知的文件系统

![f6746ba1ece697774700e7f00db12d2](D:\weixinhuancun\WeChat Files\wxid_zaf72ri06sag22\FileStorage\Temp\f6746ba1ece697774700e7f00db12d2.png)![ba8da75c465be98ff46e1bf7df40d7b](D:\weixinhuancun\WeChat Files\wxid_zaf72ri06sag22\FileStorage\Temp\ba8da75c465be98ff46e1bf7df40d7b.png)

原因分析：存放EFI文件的分区（ESP分区）中，由于安装时设置的错误，导致Ubuntu启动菜单无法读取引导Windows的安装文件。只能先进入PE环境把ESP分区中ubuntu文件夹删除，让其能够进入Windows系统。

![bae1a5c3ef01fb83f1f3936ad7a801c](D:\weixinhuancun\WeChat Files\wxid_zaf72ri06sag22\FileStorage\Temp\bae1a5c3ef01fb83f1f3936ad7a801c.png)

解决措施：删掉ubuntu启动项后，删除掉Ubuntu分区。再在空白分区建立另外的ESP分区，独立引导Ubuntu。在安装Ubuntu时，需要仔细选择引导分区和空白分区。

![de08ff2b14ad0f1516eb949f96e920c](D:\weixinhuancun\WeChat Files\wxid_zaf72ri06sag22\FileStorage\Temp\de08ff2b14ad0f1516eb949f96e920c.png)

安装完毕后，开机时选择相应的启动项进入相应的系统，一般来说默认进入Windows系统
