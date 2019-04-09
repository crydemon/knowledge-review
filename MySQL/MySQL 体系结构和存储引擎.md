#  MySQL 体系结构和存储引擎 



数据库：文件的集合

实例：由后台线程和一个共享的内存区域组成，用以操作数据库，表现为一个进程

数据实例启动时配置加载顺序：

~~~ sql
mysql --help
~~~



![1554830192592](.\conf加载顺序.png)

datadir 指定了数据库的存储位置， 必须保证相应的权限

![1554830817684](.\1554830817684.png)

mysql结构

![img](.\MySQL Architecture.png)

存储引擎是插件式，基于表的

##### InnoDB

面向OLTP (online transaction processing)

mvcc实现高并发

默认隔离级别：repeatable

next-key-locking避免幻读(phantom)

clusted方式存储数据

索引文件格式.ibd

##### MyISAM

数据库只缓存器索引文件，缓存区文件大小？

.MYD 存放数据文件

.MYI 存放索引

面向OLAP 

各种存储引擎

![1554832222396](1554832222396.png)

