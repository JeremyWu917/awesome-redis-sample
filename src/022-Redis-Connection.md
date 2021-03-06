# `Redis` 连接
> `Redis` 连接命令主要是用于连接 `redis` 服务。

## 实例
以下实例演示了客户端如何通过密码验证连接到 `redis` 服务，并检测服务是否在运行：
```powershell
redis 127.0.0.1:6379> AUTH "password"
OK
redis 127.0.0.1:6379> PING
PONG
```

## `Redis` 连接命令
下表列出了 `redis` 连接的基本命令：

序号|命令|描述
-|-|-
`1`|`AUTH password`|验证密码是否正确
`2`|`ECHO message`|打印字符串
`3`|`PING`|查看服务是否运行
`4`|`QUIT`|关闭当前连接
`5`|`SELECT index`|切换到指定的数据库
