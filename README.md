# Lenovo Yoga3 11 **黑苹果安装**

##一、机型配置如下    
  *  机型：Lenovo Yoga3 11 
  *  CPU：Intel Core M 5Y10 / 5Y71 / 5Y70  
  *  内存：4G/8G
  *  硬盘：三星PM871 256G  
  *  核显：HD5300（1920x1080 11.6寸）
  *  声卡：Realtek ALC286  
  *  无线网卡：bcm94352hmz  （自行更换，无白名单）

##二、工作情况    
  *  显卡HD5300：（亮度调整正常）注入 ig-platform-id 0x16260006  
  *  声卡：注入ID3
  *  触摸板（i2c触摸板）   
  *  休眠唤醒
  *  usb（2.0/3.0正常识别，并且内建内置usb设备）  
  *  蓝牙+WiFi（更换联想版bcm94352z）  
  *  摄像头（免驱）  
  *  HDMI输出（hdmi声音还没搞）   

##三、安装方法    
    *  更新官网最新版bios，UEFI MODE 模式改为Legacy Support  
    *  下载镜像使用用transmac将镜像刻录到U盘  
    *  使用我的安装系统使用的EFI（install-EFI）安装系统（无驱动，安装减少报错）   
    *  安装完成后，kext utility 软件重建缓存  
    *  使用安装后使用的EFI（安装后使用的EFI）目录下的EFI引导开机   
    *  详细安装过程请参考 daliansky 写的安装教程
 [联想小新Air 13黑苹果安装教程](https://blog.daliansky.net/Lenovo-Xiaoxin-Air-13-macOS-Mojave-installation-tutorial.html)

##三、备注：     
   *  目录有两个引导，一个安装系统使用，一个是安装系统完成后 重建缓存 更换安装后EFI引导  （重建缓存使用kext utility软件，打开后输入密码，等待重建缓存完成后退出，更换安装后EFI引导）  


   *  打开访达→左上角选择前往→前往文件夹 进入 /System/Library/Extensions 目录下删除AppleIntelLpssI2C.kext AppleIntelLpssI2CController.kext，重建缓存后重启  
    *  目前有10.13.6、版本可以用   ，10.14.3没人给我当小白鼠，如果你愿意试验，联系我   

##有问题反馈
  *  在使用中有任何问题，欢迎反馈给我，可以用以下联系方式跟我交流

* 邮件(gdllzkusi@gmail.com)
* QQ: 374593607  

##感激
   * 感谢以下的大神,排名不分先后
   * 感谢daliansky 帮忙定制applealc声卡驱动  
   * 感谢penghubingzhou 帮忙解决syna触摸板无手势功能  
   * 感谢acidanthera、RehabMan、vit9696 等等大神做出来的q以及出了n多教程的大神前辈们
