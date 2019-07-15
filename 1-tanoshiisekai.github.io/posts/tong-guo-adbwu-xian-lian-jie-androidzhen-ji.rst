.. title: 通过ADB无线连接Android真机
.. slug: tong-guo-adbwu-xian-lian-jie-androidzhen-ji
.. date: 2019-07-15 18:00:57 UTC+08:00
.. tags: Android
.. category: Android
.. link: 
.. description: 
.. type: text


1、先通过USB连接手机，打开调试。

::

    long@happyhome:~$ adb devices
    * daemon not running; starting now at tcp:5037
    * daemon started successfully
    List of devices attached
    T3Q4C15B04017525	device

::

    long@happyhome:~$ adb tcpip 5555
    restarting in TCP mode port: 5555

2、查看手机IP地址。

::

    long@happyhome:~$ adb shell ip -f inet addr show wlan0
    39: wlan0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1400 qdisc mq state UP qlen 1000
        inet 192.168.2.111/24 brd 192.168.2.255 scope global wlan0
           valid_lft forever preferred_lft forever

3、根据上一步中得到IP地址，通过无线连接手机。

::

    long@happyhome:~$ adb connect 192.168.2.111:5555
    connected to 192.168.2.111:5555


4、断开USB线，查看连接状态。

::

    long@happyhome:~$ adb devices
    List of devices attached
    192.168.2.111:5555	device


5、可以看出已经通过无线连接到手机。

