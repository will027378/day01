#通过vagrant安装虚拟机

##安装前工具准备
1VirtualBox-4.3.10-93012-Win<br>
2vagrant_1.5.4.msi<br>
3UbuntuServer12.04amd64.box<br>
##开始安装
1首先安装虚拟机VirtualBox<br>
直接下一步下一步就ok了<br>
2接下来安装vagrant<br>
直接下一步下一步安装<br>
完成后在控制台中输入vagrant验证安装是否成功<br>
3安装操作系统<br>
(1)在你某个盘(你想要将虚拟机安装的位置)中建立一个文件夹(名字随意比如boxs),然后
将UbuntuServer12.04amd64.box拷贝到这个文件夹中<br>
(2)在控制台执行命令vagrant box add master UbuntuServer12.04amd64.box<br>
(3)修改boxs中配置文件Vagrantfile，自己百度下<br>
(4)执行命名vagrant init<br>
(5)执行命令vagrant up<br>
到此安装完成
