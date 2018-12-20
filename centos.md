CentOS7使用firewalld打开关闭防火墙与端口  
####1、firewalld的基本使用 
	- 启动： systemctl start firewalld 
	- 关闭： systemctl stop firewalld 
	- 查看状态： systemctl status firewalld   
	- 开机禁用  ： systemctl disable firewalld -
	- 开机启用  ： systemctl enable firewalld 
 
 
####2.systemctl是CentOS7的服务管理工具中主要的工具，它融合之前service和chkconfig的功能于一体。
 	- 启动一个服务：systemctl start firewalld.service
 	- 关闭一个服务：systemctl stop firewalld.service
 	- 重启一个服务：systemctl restart firewalld.service
 	- 显示一个服务的状态：systemctl status firewalld.service
 	- 在开机时启用一个服务：systemctl enable firewalld.service
 	- 在开机时禁用一个服务：systemctl disable firewalld.service
 	- 查看服务是否开机启动：systemctl is-enabled firewalld.service
 	- 查看已启动的服务列表：systemctl list-unit-files|grep enabled
 	- 查看启动失败的服务列表：systemctl --failed

####3.配置firewalld-cmd

 	- 查看版本： firewall-cmd --version
 	- 查看帮助： firewall-cmd --help
 	- 显示状态： firewall-cmd --state
 	- 查看所有打开的端口： firewall-cmd --zone=public --list-ports
 	- 更新防火墙规则： firewall-cmd --reload
 	- 查看区域信息:  firewall-cmd --get-active-zones
 	- 查看指定接口所属区域： firewall-cmd --get-zone-of-interface=eth0
 	- 拒绝所有包：firewall-cmd --panic-on
 	- 取消拒绝状态： firewall-cmd --panic-off
 	- 查看是否拒绝： firewall-cmd --query-panic
 
####那怎么开启一个端口呢
#####添加
 	- firewall-cmd --zone=public --add-port=80/tcp --permanent    （--permanent永久生效，没有此参数重启后失效）
#####重新载入
 	- firewall-cmd --reload
#####查看
 	- firewall-cmd --zone= public --query-port=80/tcp
#####删除
 	- firewall-cmd --zone=public --remove-port=80/tcp --permanent


#### 查看centos 版本
	- cat /etc/issue
	- cat /etc/redhat-release

1、查看服务器端口是否被占用

>lsof  -i:8081

2、查看服务器所有端口

>netstat -ntlp

3、查看服务器是否开放某端口

tcp端口：>netstat -ntpl

udp端口：>netstat -nupl

常用参数：

-a (all)显示所有选项，默认不显示LISTEN相关
-t (tcp)仅显示tcp相关选项
-u (udp)仅显示udp相关选项
-n 拒绝显示别名，能显示数字的全部转化成数字。
-l 仅列出有在 Listen (监听) 的服務状态

-p 显示建立相关链接的程序名
-r 显示路由信息，路由表
-e 显示扩展信息，例如uid等
-s 按各个协议进行统计
-c 每隔一个固定时间，执行该netstat命令。

提示：LISTEN和LISTENING的状态只有用-a或者-l才能看到 