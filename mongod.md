###一、mongod的启动和关闭 

####mogodb 启动

1. 缺省的启动方式
   `./mongod`  
   缺省的启动方式，数据存储目录里是/data/db，监听端口是27017
2. 带基本参数的启动方式
   ./mongod --port 51017 --dbpath /home/mongo/data --logpath /home/mongo/log/log.log --logappend --fork --journal 1000 

#####基本参数：
-   -f                     指定配置文件 （参考：http://www.mongodb.org/display/DOCS/File+Based+Configuration）
-   --port                 指定端口，默认是27017
-   --dbpath               数据目录路径
-   --logpath              日志文件路径
-   --logappend            日志append而不是overwrite
-   --fork                 以创建子进程的方式运行
-   --journal              日志提交间隔，默认100ms
-   --nojournal            关闭日志功能，2.0版本以上是默认开启的

####mongodb关闭
`> use admin`  
`> db.shutdownServer()` 
`> db.shutdownServer({force : true}) 强制关闭Mongod，应对副本集中主从时间差超过10s时不允许关闭主库的情况不要使用kill直接杀mongo进程的方式关闭数据节点，会造成数据损坏`

