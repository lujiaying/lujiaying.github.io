---
title: 云主机如何挂载云硬盘
date: 2016-05-06
permalink: /posts/2016/05/cloud-server-mount/
tags: 
  - Linux
---

有时我们需要对云主机扩容，挂载一块新的云硬盘是很好的方法。下面具体介绍如何在云主机上挂载云盘。

## 方法／步骤

1. 查看当前所有硬盘和大小
假设你已经拥有一块云硬盘，并链接了云硬盘和云主机。
那么你可以通过`fdisk -l`命令来查看当前所有硬盘和大小。
(PS: 在执行命令时遇到问题请参照本文的**常见问题和解决方法**)
![查看所有硬盘和大小](http://7xkdra.com1.z0.glb.clouddn.com/image%2Fblog%2Ffdisk.png)

2. 格式化
**初次**挂载云盘需要进行格式化操作（第二次千万别做，否则会丢失数据），使用`mkfs.ext4 /dev/vdd`
![格式化](http://7xkdra.com1.z0.glb.clouddn.com/image%2Fblog%2Fmkfs.png)

3. 挂载
格式化之后需要创建挂载点，创建好挂载点之后就可以使用`mount -t ext4 /dev/vdd /home/your_mount_point`挂载了。
![挂载](http://7xkdra.com1.z0.glb.clouddn.com/image%2Fblog%2Fmount.png)

## 科普一下

对于**挂载**，首先给大家一个定义：
挂载，说白了就是把设备和路径连接起来。下面结合具体的例子说明：
![我的磁盘](http://7xkdra.com1.z0.glb.clouddn.com/image%2Fblog%2Fdf.png)
`/dev`下的`vdX`(从a-z)就是硬盘啦。
那么`vda1`是什么呢? `vda1`是硬盘`vda`底下的一个分区。说明你对vda进行了分区,且只有一个分区vda1(如果有两个会有vda2 vda3.....)
分区可以理解成硬盘的一块区域, 系统对待vda1和vdb都是当一块硬盘设备来处理的(即一旦你进行磁盘分区，在挂载的时候，就不能使用设备vda而得用vda1来挂载了), 那么连接磁盘和路径的方式就是
`mount -t ext4 /dev/vdb /home`

## 常见问题和解决方法

在挂载中，可能会遇到`command not found`的问题，下面以`fdisk`为例说明如何解决此类问题。
```shell
[root@localhost boot]# fdisk-l <--使用 fdisk命令时候 出现如下错误
bash: fdisk-l: command not found 
[root@localhost boot]# whereis fdisk <--查询fdisk命令的位置 
fdisk: /sbin/fdisk /usr/share/man/man8/fdisk.8.gz
[root@localhost boot]# echo $PATH <---查询环境变量
/nfs/smartsvn/bin:/usr/local/sbin:/sbin:/usr/lib/oracle/xe/app/oracle/product/10.2.0/server/bin:/usr/sbin:/usr/local/bin:/usr/bin:/bin:/usr/java/jdk1.7.0_25/bin:/usr/dev/svnclient/smartsvn-7_5_2/bin
[root@localhost boot]# echo $PATH | grep /sbin/fdisk <--再次确认确实没有fdisk命令所在位置
[root@localhost boot]# ln -s /sbin/fdisk /usr/local/sbin <--fdisk添加到当前命令搜索路径中即可
[root@localhost boot]# cd /usr/local/sbin <--确认fdisk已经添加到环境变量
[root@localhost sbin]# ls -F |grep /sbin/fdisk
[root@localhost sbin]# ls -F
fdisk@
 
 
[root@localhost sbin]# fdisk -l<--使用fdisk命令
Disk /dev/sda: 21.5 GB, 21474836480 bytes
255 heads, 63 sectors/track, 2610 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk identifier: 0x000f1e94
   Device Boot      Start         End      Blocks   Id  System
/dev/sda1   *           1          39      307200   83  Linux
Partition 1 does not end on cylinder boundary.
/dev/sda2              39        2354    18598912   83  Linux
/dev/sda3            2354        2611     2064384   82  Linux swap / Solaris
```
如果大家遇到其他类似的问题，可以试着使用该方法解决，也可以联系我。

> 更多精彩内容，请关注我的[个人博客](http://lujiaying.github.io/)。
