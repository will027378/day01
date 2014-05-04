#通过Vagrant在Windows下部署linux开发环境
##安装步骤
###1.安装VirtualBox
VirtualBox是一款免费开源虚拟机软件<br>
下载地址：https://www.virtualbox.org/wiki/Downloads<br>
安装：通过步骤一步一步安装就ok<br>
###2.安装Vagrant
Vagrant用于创建和部署虚拟化开发环境<br>
下载地址：http://downloads.vagrantup.com/<br>
安装：通过步骤一步一步安装就ok<br>
###3.下载linux镜像box文件
下载地址：http://www.vagrantbox.es/<br>
###4.正式部署linux环境
#####1.添加镜像到vagrant
在控制台输入：<br>
$vagrant box add  master ~/boxs/UbuntuServer12.04amd64.box<br>
master是我们给这个box命的名字，你可以按你的情况命名；~/boxs/UbuntuServer12.04amd64.box是box所在路径
#####2.初始化开发环境
