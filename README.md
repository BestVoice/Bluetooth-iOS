# Bluetooth-iOS

蓝牙开发可谓是越来越火，不论是智能穿戴的兴起还是蓝牙家具，车联网蓝牙等等，很多同学也会接触到蓝牙的项目，我最近的项目中也遇到了蓝牙，简单研究了一下。

废话不多说了，先向大家简单的介绍有关蓝牙开发的知识。蓝牙低能耗(BLE)，以下介绍的都是围绕iOS的框架展开的。  

蓝牙开发分为中心者模式和管理者模式：
1.常用的（其实99.99%）就是使用中心者模式作为开发，就是我们手机作为主机，连接蓝牙外设；
2.管理者模式，这个基本用到的比较少，我们手机自己作为外设，自己创建服务和特征，然后有其他的设备连接我们的手机。

在做蓝牙开发之前，最好先了解一些概念： 
服务（services）：蓝牙外设对外广播的必定会有一个服务，可能也有多个，服务下面包含着一些特征，服务可以理解成一个模块的窗口； 
特征（characteristic）：存在于服务下面的，一个服务下面也可以存在多个特征，特征可以理解成具体实现功能的窗口，一般特征都会有value，也就是特征值，特征是与外界交互的最小单位； 
UUID：可以理解成蓝牙上的唯一标识符（硬件上肯定不是这个意思，但是这样理解便于我们开发），为了区分不同的服务和特征，或者给服务和特征取名字，我们就用UUID来代表服务和特征。  

蓝牙连接可以大致分为以下几个步骤 
1.建立一个Central Manager实例进行蓝牙管理 
2.搜索外围设备 
3.连接外围设备 
4.获得外围设备的服务 
5.获得服务的特征 
6.从外围设备读数据 
7.给外围设备发送数据
