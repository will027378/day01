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
创建一个开发目录(比如：~/myhadoop)，也可以用已有目录，切换到开发目录里，用master镜像初始化当前目录的环境,控制台输入命令<br>
$cd ~/myhadoop <br>
$vagrant init master
#####3.启动环境
$vagrant up <br>
这是你就可以看到终端显示了启动过程，启动完成后，我们就可以安装第三方ssh客户端如xshel来登陆虚拟机了。<br>
#####4.修改配置文件
vagrant初始化成功后，会在初始化目录(~/myhadoop)中生成一个Vagrantfile的配置文件，可以修改配置文件进行个性化的定制<br>
Vagrant 默认是使用端口映射方式将虚拟机的端口映射本地从而实现类似 http://localhost:80 这种访问方式，这种方式比较麻烦，新开和修改端口的时候都得编辑。相比较而言，host-only 模式显得方便多了。打开 Vagrantfile，将下面这行的注释去掉（移除 #）并保存：
config.vm.network :private_network, ip: "192.168.33.10"
重启虚拟机，这样我们就能用 192.168.33.10 访问这台机器了，你可以把 IP 改成其他地址，只要不产生冲突就行<br>
#####5.打包分发(这部可选)
当你配置好开发环境后，退出并关闭虚拟机。在控制台里对开发环境进行打包：<br>
$vagrant package
打包完成后会在当前目录生成一个 package.box 的文件，将这个文件传给其他用户，其他用户只要添加这个 box 并用其初始化自己的开发目录就能得到一个一模一样的开发环境了。

