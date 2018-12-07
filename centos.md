centos7中的防火墙改成了firewall，使用iptables无作用，开放端口的方法如下：

firewall-cmd --zone=public --add-port=80/tcp --permanent

返回success为成功

命令含义： 

--zone #作用域 

--add-port=80/tcp #添加端口，格式为：端口/通讯协议 

--permanent #永久生效

重启防火墙：

systemctl restart firewalld.service 

关闭防火墙：

systemctl stop firewalld.service 

查看监听(Listen)的端口

netstat -lntp

检查端口被哪个进程占用

netstat -lnp|grep 8080
