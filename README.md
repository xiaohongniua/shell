# shell
some basic shell codes

## add a user
sudo useradd -s /bin/bash -g group –G root -d /home/username username -m
## password
sudo passwd username

## change the authority of dir or file
chmod 700 -R dir/filename
7:owner
0:group
0:others

## usermod -a -G sudo suveng

## check all user information
cat /etc/passwd


## 查看CPU信息（型号）
cat /proc/cpuinfo | grep name | cut -f2 -d: | uniq -c
## 查看物理CPU个数
cat /proc/cpuinfo| grep "physical id"| sort| uniq| wc -l
## 查看每个物理CPU中core的个数(即核数)
cat /proc/cpuinfo| grep "cpu cores"| uniq
## 查看逻辑CPU的个数
cat /proc/cpuinfo| grep "processor"| wc -l



## .bz2 
解压1：bzip2 -d FileName.bz2

解压2：bunzip2 FileName.bz2 

压缩： bzip2 -z FileName 

## .tar.bz2
解压：tar jxvf FileName.tar.bz2     或tar --bzip xvf FileName.tar.bz2

压缩：tar jcvf FileName.tar.bz2 DirName 

##下载目录下所有文件
wget -r -np -nH -R index.html http://url...
各个参数的含义：

-r : 遍历所有子目录
-np : 不到上一层子目录去
-nH : 不要将文件保存到主机名文件夹
-R index.html : 不下载 index.html 文件
下载完后删掉无用的文件即可

## 把用户加到sudo组
1、切换到root用户：su root

2、找到sudo文件/etc/sudoers，该文件默认是不可写的，添加可写权限

chmod u+w /etc/sudoers

3、修改sudoers文件，找到以下语句

root ALL=(ALL:ALL) ALL

在下面添加

yourUserName ALL=(ALL:ALL) ALL

保存退出。修改此文件风险比较大， 文件如果改坏， 导致所有用户的 sudo 权限都没了，所以修改时请注意

4、鉴于安全考虑修改完后应把sudoers写权限去掉

chmod u-w /etc/sudoers

5、杀某个名称的进程
ps -efww|grep -w 'glide_backend'|grep -v grep|cut -c 9-15|xargs kill -9

