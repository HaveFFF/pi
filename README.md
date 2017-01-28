# 我的树莓派记录
## 1 samba文件共享  
让Rasbian系统支持NTFS格式的磁盘  
>sudo apt-get install ntfs-3g
查找新挂上的硬盘的未挂载分区  
sudo fdisk -l  
生成一个目录来挂载硬盘，在/tmp目录，没有权限问题  
sudo mkdir /tmp/**  
