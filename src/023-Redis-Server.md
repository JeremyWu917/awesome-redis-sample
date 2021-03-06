# `Redis` 服务器
> `Redis` 服务器命令主要是用于管理 `redis` 服务。

## `Redis` 服务器命令
下表列出了 `redis` 服务器的相关命令:

序号|命令|描述
-|-|-
`1`|`BGREWRITEAOF`|异步执行一个 `AOF`（`AppendOnly File`） 文件重写操作
`2`|`BGSAVE`|在后台异步保存当前数据库的数据到磁盘
`3`|`CLIENT KILL [ip:port] [ID client-id]`|关闭客户端连接
`4`|`CLIENT LIST`|获取连接到服务器的客户端连接列表
`5`|`CLIENT GETNAME`|获取连接的名称
`6`|`CLIENT PAUSE timeout`|在指定时间内终止运行来自客户端的命令
`7`|`CLIENT SETNAME connection-name`|设置当前连接的名称
`8`|`CLUSTER SLOTS`|获取集群节点的映射数组
`9`|`COMMAND`|获取 `Redis` 命令详情数组
`10`|`COMMAND COUNT`|获取 `Redis` 命令总数
`11`|`COMMAND GETKEYS`|获取给定命令的所有键
`12`|`TIME`|返回当前服务器时间
`13`|`COMMAND INFO command-name [command-name ...]`|获取指定 `Redis` 命令描述的数组
`14`|`CONFIG GET parameter`|获取指定配置参数的值
`15`|`CONFIG REWRITE`|对启动 `Redis` 服务器时所指定的 `redis.conf` 配置文件进行改写
`16`|`CONFIG SET parameter value`|修改 `redis` 配置参数，无需重启
`17`|`CONFIG RESETSTAT`|重置 `INFO` 命令中的某些统计数据
`18`|`DBSIZE`|返回当前数据库的 `key` 的数量
`19`|`DEBUG OBJECT key`|获取 `key` 的调试信息
`20`|`DEBUG SEGFAULT`|让 `Redis` 服务崩溃
`21`|`FLUSHALL`|删除所有数据库的所有`key`
`22`|`FLUSHDB`|删除当前数据库的所有`key`
`23`|`INFO [section]`|获取 `Redis` 服务器的各种信息和统计数值
`24`|`LASTSAVE`|返回最近一次 `Redis` 成功将数据保存到磁盘上的时间，以 `UNIX` 时间戳格式表示
`25`|`MONITOR`|实时打印出 `Redis` 服务器接收到的命令，调试用
`26`|`ROLE`|返回主从实例所属的角色
`27`|`SAVE`|异步保存数据到硬盘
`28`|`SHUTDOWN [NOSAVE] [SAVE]`|异步保存数据到硬盘，并关闭服务器
`29`|`SLAVEOF host port`|将当前服务器转变为指定服务器的从属服务器(`slave server`)
`30`|`SLOWLOG subcommand [argument]`|管理 `redis` 的慢日志
`31`|`SYNC`|用于复制功能(`replication`)的内部命令
