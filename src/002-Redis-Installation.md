# `Redis` 安装

## `Window` 下安装
下载地址：[Download](https://github.com/dmajkic/redis/downloads)

下载到的 `Redis` 支持 `32bit` 和 `64bit` ，根据自己实际情况选择。本教程将 `64bit` 的内容 `cp` 到自定义盘符安装目录取名 `redis` 。 如 `C:\redis`

打开一个 `cmd` 窗口 使用 `cd` 命令切换目录到 `C:\redis` 运行 `redis-server.exe` `redis.conf` 。（如果下载的是 `Redis-x64-3.2.100` 版本，是运行 `redis-server.exe redis.windows.conf`）

如果想方便的话，可以把 `redis` 的路径加到系统的环境变量里，这样就省得再输路径了，后面的那个 `redis.conf` 可以省略，如果省略，会启用默认的。

## `Linux` 下安装
下载地址：[Download](http://redis.io/download)，下载最新文档版本。
```linux
$ wget http://download.redis.io/releases/redis-6.2.5.tar.gz
$ tar xzf redis-6.2.5.tar.gz
$ cd redis-6.2.5
$ make
```
`make` 完后 `redis-6.2.5` 目录下会出现编译后的 `redis` 服务程序`redis-server`,还有用于测试的客户端程序 `redis-cli` 都会位于安装目录中的 `src` 目录下。

下面启动 `redis` 服务.
```
$ cd src
$ ./redis-server
```
注意这种方式启动 `redis` 使用的是默认配置。也可以通过启动参数告诉 `redis` 使用指定配置文件使用下面命令启动。

`$ ./redis-server redis.conf`
`redis.conf` 是一个默认的配置文件。我们可以根据需要使用自己的配置文件。

启动 `redis` 服务进程后，就可以使用测试客户端程序 `redis-cli` 和 `redis` 服务交互了。 比如：
```
$ cd src
$ ./redis-cli
redis> set foo bar
OK
redis> get foo
"bar"
```

## `Ubuntu` 下安装
在 `Ubuntu` 系统安装 `Redis` 可以使用以下命令:
```
$sudo apt-get update
$sudo apt-get install redis-server
```
启动 `Redis`
```
$redis-server
```
查看 `redis` 是否启动？
```
$redis-cli
```
以上命令将打开以下终端：

`redis 127.0.0.1:6379>`
`127.0.0.1` 是本机 `IP` `，6379` 是 `redis` 服务端口。现在我们输 `PING` 命令。
```
redis 127.0.0.1:6379> ping
PONG
```
以上说明我们已经成功安装了 `redis`
