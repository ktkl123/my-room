# 单硬盘UEFI+Windows10/11环境下安装Ubuntu的一种故障情况导致进不去Windows系统

故障情况还原：单硬盘UEFI+Windows10/11环境下安装Ubuntu后，从Ubuntu启动菜单选择Windows11，会显示 错误：未知的文件系统

![_cgi-bin_mmwebwx-bin_webwxgetmsgimg _MsgID_868018817890151090_skey_@crypt_b15f0057_1163630b40b1c28f4fc51c8d6c3bcd60_mmweb_appid_wx_webfilehelper.jpeg](https://s2.loli.net/2024/03/14/KLBUXycsFWqPClg.jpg)
![_cgi-bin_mmwebwx-bin_webwxgetmsgimg _MsgID_1265723407672634599_skey_@crypt_b15f0057_1163630b40b1c28f4fc51c8d6c3bcd60_mmweb_appid_wx_webfilehelper.jpeg](https://s2.loli.net/2024/03/14/CENZ2cxodsQpBLk.jpg)

原因分析：存放EFI文件的分区（ESP分区）中，由于安装时设置的错误，导致Ubuntu启动菜单无法读取引导Windows的安装文件。只能先进入PE环境把ESP分区中ubuntu文件夹删除，让其能够进入Windows系统。

![_cgi-bin_mmwebwx-bin_webwxgetmsgimg _MsgID_213385754506176173_skey_@crypt_b15f0057_1163630b40b1c28f4fc51c8d6c3bcd60_mmweb_appid_wx_webfilehelper.jpeg](https://s2.loli.net/2024/03/14/SbfcHdiwUG4sxaM.png)

解决措施：删掉ubuntu启动项后，删除掉Ubuntu分区。再在空白分区建立另外的ESP分区，独立引导Ubuntu。在安装Ubuntu时，需要仔细选择引导分区和空白分区。

![_cgi-bin_mmwebwx-bin_webwxgetmsgimg _MsgID_2710640371212052747_skey_@crypt_b15f0057_1163630b40b1c28f4fc51c8d6c3bcd60_mmweb_appid_wx_webfilehelper.jpeg](https://s2.loli.net/2024/03/14/DUjIr82Kfs7OzFl.jpg)

安装完毕后，开机时选择相应的启动项进入相应的系统，一般来说默认进入Windows系统
