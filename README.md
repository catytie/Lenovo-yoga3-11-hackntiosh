# Lenovo Yoga3 11 **黑苹果安装**

##一、机型配置如下    
  *  机型：Lenovo Yoga3 11 
  *  CPU：Intel Core M 5Y10 / 5Y71 / 5Y70  
  *  内存：4G/8G
  *  硬盘：三星PM871 256G  
  *  核显：HD5300（1920x1080 11.6寸）
  *  声卡：Realtek ALC286  
  *  无线网卡：bcm94352hmz  （自行更换联想版BCM94352z 带FRU）

##二、工作情况    
  *  显卡HD5300：（亮度调整正常）注入 ig-platform-id 0x16260006   
  *  声卡：注入ID3  
  *  触摸板（i2c触摸板，完美手势）   
  *  休眠唤醒
  *  usb（2.0/3.0正常识别，并且内建内置usb设备）  
  *  蓝牙+WiFi（更换联想版bcm94352z）  
  *  摄像头（免驱）  
  *  HDMI输出
  *  FN声音/亮度快捷键  
  
##三、安装方法    
    *  更新官网最新版bios，UEFI MODE 模式改为Legacy Support  
    *  下载镜像使用用transmac将镜像刻录到U盘  
    *  使用使用我的10.14.3 目录下面的EFI文件夹替换镜像自带的EFI引导  
    *  详细安装过程请参考 daliansky 写的安装教程
 [联想小新Air 13黑苹果安装教程](https://blog.daliansky.net/Lenovo-Xiaoxin-Air-13-macOS-Mojave-installation-tutorial.html)
    *  完成系统安装后，拷贝EFI引导文件夹到硬盘EFI分区，添加到启动项（windows 下面用 diskgenius 复制到EFI分区，然后用 easy uefi 添加启动项，单 mac 系统需要用pe 来添加启动项） 
##三、备注：     
##有问题反馈
  *  在使用中有任何问题，欢迎反馈给我，可以用以下联系方式跟我交流

* 邮件(gdllzkusi@gmail.com)
* QQ: 374593607  
