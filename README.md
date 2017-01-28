# 我的树莓派记录
## 1 samba文件共享  
让Rasbian系统支持NTFS格式的磁盘  
>sudo apt-get install ntfs-3g

查找新挂上的硬盘的未挂载分区
>sudo fdisk -l

生成一个目录来挂载硬盘，在/tmp目录，没有权限问题
>sudo mkdir /tmp/**

挂载硬盘到目录
>sudo mount -t auto /dev/sda1 /tmp/**

安装Samba
>sudo apt-get install samba samba-common-bin

编辑Samba配置文件
>sudo nano /etc/samba/smb.conf

输入
>[Public]  
comment = Public Storage  # 共享文件夹说明  
path = /home/pi/Public # 共享文件夹目录  
read only = no # 不只读  
create mask = 0777 # 创建文件的权限  
directory mask = 0777 # 创建文件夹的权限  
guest ok = yes # guest访问，无需密码  
browseable = yes # 可见

重启Samba服务
>sudo samba restart

完成
## 2 自动挂载的硬盘权限有问题
现在无法读写，
