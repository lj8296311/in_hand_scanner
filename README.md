# in_hand_scanner
In hand scanner from PCL 1.8.0 with enhanced depth filter

参考：http://pointclouds.org/documentation/tutorials/in_hand_scanner.php

A) 默认支持PrimeSense摄像头，支持其他摄像头如奥比，需要修改PCL代码并重新编译
b) 依赖库： PCL 1.8.0 + opencv2.4.9 + openNI1.5.x +  QT5.6.0 + GLUT

PCL 1.8.0：先安装AllInOne，其中有第三方库和头文件，然后下载PCL source重新编译
  （因为需要添加对奥比摄像头的支持，需要修改openni_grabber对应的vendor id的判断）。
   使用cmake-gui,指定第三方库和头文件路径,生成PCL.sln(我用的vs2013)。 
openNI1.5.x：用以前编译好的
QT5.6.0:  直接下载可以安装的包
GLUT： 直接下载可以使用的库文件，反正PCL能找到的地方，或者放到 system/win32下
opencv2.4.9： 直接下载可安装的 

C) cmake-gui 生成project.sln (vs2013), debug下帧速很低0.5fps, release下可到20fps(深度VGA，color VGA). 深度QVGA时ICP报错，说是点太少.
