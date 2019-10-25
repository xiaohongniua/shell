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

