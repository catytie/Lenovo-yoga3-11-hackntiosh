# Lenovo Yoga3 11 **黑苹果安装**

##一、机型配置如下    
  *  机型：Lenovo Yoga3 11 
  *  CPU：Intel Core M 5Y10 / 5Y71 / 5Y70  
  *  内存：4G/8G
  *  硬盘：三星PM871 256G  
  *  核显：HD5300（1920x1080 11.6寸）
  *  声卡：Realtek ALC235  
  *  无线网卡：bcm94352z （自行更换联想版BCM94352z 带FRU）

##二、工作情况    

  |设备|驱动方法|
  |:-----:|-----|
  |显卡HD5300|使用[WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen) 注入ig-platform-id 0x16260006 HDMI音视频输出正常|
  |声卡ALC235|使用[AppleALC.kext](https://github.com/acidanthera/AppleALC) 注入 layout-id:3 和 [CodecCommander.kext](https://github.com/RehabMan/EAPD-Codec-Commander) 修复睡眠无声|
  |触摸板|使用核心驱动[VoodooI2C.kext](https://github.com/alexandred/VoodooI2C)+目标驱动VoodooI2CSynaptics.kext(需要修改IOPropertyMatch 为SYNA2B33) 或者 VoodooI2CELAN.kext需要修改IOPropertyMatch 为ELAN0600|
  |usb设备|使用[OS-X-USB-Inject-All](https://github.com/RehabMan/OS-X-USB-Inject-All) +SSDT-UIAC.aml|
  |FN热键|SSDT-BrightKey-lenovoAir/IKB/IKBR/IWL.aml（仅适用于SYNA版本，ELAN版本无法使用）|
  |蓝牙WIFI|WIFI使用FakePCIID.kext+FakePCIID_Broadcom_WiFi.kext [AirportBrcmFixup](https://github.com/acidanthera/AirportBrcmFixup)  蓝牙使用[BrcmPatchRAM2.kext+BrcmFirmwareData.kext)](https://github.com/RehabMan/OS-X-BrcmPatchRAM) |
  |Apple SMC仿真器|使用[OS-X-FakeSMC-kozlek](https://github.com/RehabMan/OS-X-FakeSMC-kozlek) |
  |电源管理|使用 [ACPIBatteryManager.kext](https://github.com/RehabMan/OS-X-ACPI-Battery-Driver) |
  |SD卡/摄像头|[摄像头免驱、SD卡屏蔽无法使用|
  
  
##三、安装方法    
    *  更新官网最新版bios，修改 bios 设置 Secure Boot → disable、Boot MODE → Legacy Support、Boot MODE → Legacy Support  
    *  下载镜像使用用transmac将镜像刻录到U盘  
    *  使用使用我的10.14.3 目录下面的EFI文件夹替换镜像自带的EFI引导  
    *  详细安装过程请参考 daliansky 写的安装教程
 [联想小新Air 13黑苹果安装教程](https://blog.daliansky.net/Lenovo-Xiaoxin-Air-13-macOS-Mojave-installation-tutorial.html)
    *  完成系统安装后，拷贝EFI引导文件夹到硬盘EFI分区，添加到启动项（windows 下面用 diskgenius 复制到EFI分区，然后用 easy uefi 添加启动项，单 mac 系统需要用pe 来添加启动项） 
##三、备注：     
  1.打开访达→左上角选择前往→前往文件夹 进入 /System/Library/Extensions 目录下删除  AppleIntelLpssI2C.kext / AppleIntelLpssI2CController.kext两个文件，重建缓存后重启，syna的目标驱动现在有个bug，就是如果进入了Windows系统，然后再进去mac系统将会不能使用触摸板，唯一解决方法就是多重启两次mac系统。该bug等待以后驱动作者更新版本解决。    

  2.目前发现该机型具有两种触控板型号，一种是SYNA2b33，另一个是ELAN0600，请根据自己型号保留对应触控板驱动，如果是 syna 的触控板，删除VoodooI2CELAN.kext （如果是ELAN触控板，删除VoodooI2CSynaptics.kext)  
  

  3.EFI里面已经放置了BCM94352z 网卡驱动以及蓝牙驱动，如果没有更换内置网卡，请在/EFI/CLOVER/kexts/Other目录下删除BrcmFirmwareData.kext/BrcmPatchRAM2.kext/FakePCIID_Broadcom_WiFi.kext/AirportBrcmFixup.kext（已更换BCM94352z 请忽略本条）  
  
  4.如果没有更换内置网卡，请在/EFI/CLOVER/kexts/Other 下放置NullEthernet.kext & 在EFI/CLOVER/ACPI/patched 目录下放置ssdt-rmne.aml  （使用USB WiFi和这个“假的以太网”驱动程序，使系统仍允许Mac App Store访问，没有它将无法使用Mac App Store访问，已更换BCM94352z 请忽略本条）
  
##有问题反馈
  *  在使用中有任何问题，欢迎反馈给我，可以用以下联系方式跟我交流  

* 邮件(gdllzkusi@gmail.com)
* QQ: 374593607  
