# `Redis` 配置
> `Redis` 的配置文件位于 `Redis` 安装目录下，文件名为 `redis.config`

您可以通过 `CONFIG` 关键字查看或设置配置项。

## 语法
### `Redis` `CONFIG` 命令格式如下：
```powershell
redis 127.0.0.1:6379> CONFIG GET CONFIG_SETTING_NAME
```
### 实例
```powershell
redis 127.0.0.1:6379> CONFIG GET loglevel

1) "loglevel"
2) "notice"
```
使用 `*` 号获取所有配置项
### 实例
```powershell
127.0.0.1:6379> CONFIG GET *
  1) "dbfilename"
  2) "dump.rdb"
  3) "requirepass"
  4) ""
  5) "masterauth"
  6) ""
  7) "cluster-announce-ip"
  8) ""
  9) "unixsocket"
 10) ""
 11) "logfile"
 12) ""
 13) "pidfile"
 14) ""
 15) "slave-announce-ip"
 16) ""
 17) "replica-announce-ip"
 18) ""
 19) "maxmemory"
 20) "0"
 21) "proto-max-bulk-len"
 22) "536870912"
 23) "client-query-buffer-limit"
 24) "1073741824"
 25) "maxmemory-samples"
 26) "5"
 27) "lfu-log-factor"
 28) "10"
 29) "lfu-decay-time"
 30) "1"
 31) "timeout"
 32) "0"
 33) "active-defrag-threshold-lower"
 34) "10"
 35) "active-defrag-threshold-upper"
 36) "100"
 37) "active-defrag-ignore-bytes"
 38) "104857600"
 39) "active-defrag-cycle-min"
 40) "5"
 41) "active-defrag-cycle-max"
 42) "75"
 43) "active-defrag-max-scan-fields"
 44) "1000"
 45) "auto-aof-rewrite-percentage"
 46) "100"
 47) "auto-aof-rewrite-min-size"
 48) "67108864"
 49) "hash-max-ziplist-entries"
 50) "512"
 51) "hash-max-ziplist-value"
 52) "64"
 53) "stream-node-max-bytes"
 54) "4096"
 55) "stream-node-max-entries"
 56) "100"
 57) "list-max-ziplist-size"
 58) "-2"
 59) "list-compress-depth"
 60) "0"
 61) "set-max-intset-entries"
 62) "512"
 63) "zset-max-ziplist-entries"
 64) "128"
 65) "zset-max-ziplist-value"
 66) "64"
 67) "hll-sparse-max-bytes"
 68) "3000"
 69) "lua-time-limit"
 70) "5000"
 71) "slowlog-log-slower-than"
 72) "10000"
 73) "latency-monitor-threshold"
 74) "0"
 75) "slowlog-max-len"
 76) "128"
 77) "port"
 78) "6379"
 79) "cluster-announce-port"
 80) "0"
 81) "cluster-announce-bus-port"
 82) "0"
 83) "tcp-backlog"
 84) "511"
 85) "databases"
 86) "16"
 87) "repl-ping-slave-period"
 88) "10"
 89) "repl-ping-replica-period"
 90) "10"
 91) "repl-timeout"
 92) "60"
 93) "repl-backlog-size"
 94) "1048576"
 95) "repl-backlog-ttl"
 96) "3600"
 97) "maxclients"
 98) "10000"
 99) "watchdog-period"
100) "0"
101) "slave-priority"
102) "100"
103) "replica-priority"
104) "100"
105) "slave-announce-port"
106) "0"
107) "replica-announce-port"
108) "0"
109) "min-slaves-to-write"
110) "0"
111) "min-replicas-to-write"
112) "0"
113) "min-slaves-max-lag"
114) "10"
115) "min-replicas-max-lag"
116) "10"
117) "hz"
118) "10"
119) "cluster-node-timeout"
120) "15000"
121) "cluster-migration-barrier"
122) "1"
123) "cluster-slave-validity-factor"
124) "10"
125) "cluster-replica-validity-factor"
126) "10"
127) "repl-diskless-sync-delay"
128) "5"
129) "tcp-keepalive"
130) "300"
131) "cluster-require-full-coverage"
132) "yes"
133) "cluster-slave-no-failover"
134) "no"
135) "cluster-replica-no-failover"
136) "no"
137) "no-appendfsync-on-rewrite"
138) "no"
139) "slave-serve-stale-data"
140) "yes"
141) "replica-serve-stale-data"
142) "yes"
143) "slave-read-only"
144) "yes"
145) "replica-read-only"
146) "yes"
147) "slave-ignore-maxmemory"
148) "yes"
149) "replica-ignore-maxmemory"
150) "yes"
151) "stop-writes-on-bgsave-error"
152) "yes"
153) "daemonize"
154) "no"
155) "rdbcompression"
156) "yes"
157) "rdbchecksum"
158) "yes"
159) "activerehashing"
160) "yes"
161) "activedefrag"
162) "no"
163) "protected-mode"
164) "yes"
165) "repl-disable-tcp-nodelay"
166) "no"
167) "repl-diskless-sync"
168) "no"
169) "aof-rewrite-incremental-fsync"
170) "yes"
171) "rdb-save-incremental-fsync"
172) "yes"
173) "aof-load-truncated"
174) "yes"
175) "aof-use-rdb-preamble"
176) "yes"
177) "lazyfree-lazy-eviction"
178) "no"
179) "lazyfree-lazy-expire"
180) "no"
181) "lazyfree-lazy-server-del"
182) "no"
183) "slave-lazy-flush"
184) "no"
185) "replica-lazy-flush"
186) "no"
187) "dynamic-hz"
188) "yes"
189) "maxmemory-policy"
190) "noeviction"
191) "loglevel"
192) "notice"
193) "supervised"
194) "no"
195) "appendfsync"
196) "everysec"
197) "syslog-facility"
198) "local0"
199) "appendonly"
200) "no"
201) "dir"
202) "/home/ubuntu"
203) "save"
204) "3600 1 300 100 60 10000"
205) "client-output-buffer-limit"
206) "normal 0 0 0 slave 268435456 67108864 60 pubsub 33554432 8388608 60"
207) "unixsocketperm"
208) "0"
209) "slaveof"
210) ""
211) "notify-keyspace-events"
212) ""
213) "bind"
214) ""
```

## 编辑配置
> 您可以通过修改 `redis.conf` 文件或使用 `CONFIG set` 命令来修改配置

### 语法
**`CONFIG SET`** 命令的基本语法：
```powershell
redis 127.0.0.1:6379> CONFIG SET CONFIG_SETTING_NAME NEW_CONFIG_VALUE
```
### 实例
```powershell
redis 127.0.0.1:6379> CONFIG SET loglevel "notice"
OK
redis 127.0.0.1:6379> CONFIG GET loglevel

1) "loglevel"
2) "notice"
```
### 参数说明
`redis.conf` 配置项说明如下：

1. `Redis` 默认不是以守护进程的方式运行，可以通过该配置项修改，使用 `yes` 启用守护进程
    **`daemonize no`**
2. 当 `Redis` 以守护进程方式运行时，`Redis` 默认会把 `pid` 写入 `/var/run/redis.pid` 文件，可以通过 `pidfile` 指定
    **`pidfile /var/run/redis.pid`**
3. 指定 `Redis` 监听端口，默认端口为 `6379`，作者在自己的一篇博文中解释了为什么选用 `6379` 作为默认端口，因为 `6379` 在手机按键上 `MERZ` 对应的号码，而 `MERZ` 取自意大利歌女 `Alessia Merz` 的名字
    **`port 6379`**
4. 绑定的主机地址
    **`bind 127.0.0.1`**
5.当客户端闲置多长时间后关闭连接，如果指定为 `0`，表示关闭该功能
    **`timeout 300`**
6. 指定日志记录级别，`Redis` 总共支持四个级别：`debug`、`verbose`、`notice`、`warning`，默认为 `verbose`
    **`loglevel verbose`**
7. 日志记录方式，默认为标准输出，如果配置 `Redis` 为守护进程方式运行，而这里又配置为日志记录方式为标准输出，则日志将会发送给 `/dev/null`
    **`logfile stdout`**
8. 设置数据库的数量，默认数据库为 `0`，可以使用SELECT `<dbid>` 命令在连接上指定数据库 `id`
    **`databases 16`**
9. 指定在多长时间内，有多少次更新操作，就将数据同步到数据文件，可以多个条件配合
    **`save <seconds> <changes>`**
    **`Redis`** 默认配置文件中提供了三个条件：
    **`save 900 1`**
    **`save 300 10`**
    **`save 60 10000`**
    分别表示 `900` 秒（ `15` 分钟）内有 `1` 个更改，`300` 秒（ `5` 分钟）内有 `10` 个更改以及 `60` 秒内有 `10000` 个更改。
10. 指定存储至本地数据库时是否压缩数据，默认为 `yes`，`Redis` 采用 `LZF` 压缩，如果为了节省 `CPU` 时间，可以关闭该选项，但会导致数据库文件变的巨大
    **`rdbcompression yes`**
11. 指定本地数据库文件名，默认值为 `dump.rdb`
    **`dbfilename dump.rdb`**
12. 指定本地数据库存放目录
    **`dir ./`**
13. 设置当本机为 `slav` 服务时，设置 `master` 服务的 `IP` 地址及端口，在 `Redis` 启动时，它会自动从 `master` 进行数据同步
    **`slaveof <masterip> <masterport>`**
14. 当 `master` 服务设置了密码保护时，`slav` 服务连接 `master` 的密码
    **`masterauth <master-password>`**
15. 设置 `Redis` 连接密码，如果配置了连接密码，客户端在连接 `Redis` 时需要通过 `AUTH` `<password>` 命令提供密码，默认关闭
    **`requirepass foobared`**
16. 设置同一时间最大客户端连接数，默认无限制，`Redis` 可以同时打开的客户端连接数为 `Redis` 进程可以打开的最大文件描述符数，如果设置 `maxclients 0`，表示不作限制。当客户端连接数到达限制时，`Redis` 会关闭新的连接并向客户端返回 `max number of clients reached` 错误信息
    **`maxclients 128`**
17. 指定 `Redis` 最大内存限制，`Redis` 在启动时会把数据加载到内存中，达到最大内存后，`Redis` 会先尝试清除已到期或即将到期的 `Key`，当此方法处理后，仍然到达最大内存设置，将无法再进行写入操作，但仍然可以进行读取操作。`Redis` 新的 `vm` 机制，会把 `Key` 存放内存，`Value` 会存放在 `swap` 区
    **`maxmemory <bytes>`**
18. 指定是否在每次更新操作后进行日志记录，`Redis` 在默认情况下是异步的把数据写入磁盘，如果不开启，可能会在断电时导致一段时间内的数据丢失。因为 `redis` 本身同步数据文件是按上面 `save` 条件来同步的，所以有的数据会在一段时间内只存在于内存中。默认为 `no`
    **`appendonly no`**
19. 指定更新日志文件名，默认为 `appendonly.aof`
    **`appendfilename appendonly.aof`**
20. 指定更新日志条件，共有 `3` 个可选值：
    `no`：表示等操作系统进行数据缓存同步到磁盘（快）
    `always`：表示每次更新操作后手动调用 `fsync()` 将数据写到磁盘（慢，安全）
    `everysec`：表示每秒同步一次（折衷，默认值）
    **`appendfsync everysec`** 
21. 指定是否启用虚拟内存机制，默认值为 `no`，简单的介绍一下，`VM` 机制将数据分页存放，由 `Redis` 将访问量较少的页即冷数据 `swap` 到磁盘上，访问多的页面由磁盘自动换出到内存中（在后面的文章我会仔细分析 `Redis` 的 `VM` 机制）
     **`vm-enabled no`**
22. 虚拟内存文件路径，默认值为 `/tmp/redis.swap`，不可多个 `Redis` 实例共享
     **`vm-swap-file /tmp/redis.swap`**
23. 将所有大于 `vm-max-memory` 的数据存入虚拟内存,无论 `vm-max-memory` 设置多小,所有索引数据都是内存存储的( `Redis` 的索引数据 就是 `keys`),也就是说,当 `vm-max-memory` 设置为 `0` 的时候,其实是所有 `value` 都存在于磁盘。默认值为 `0`
     **`vm-max-memory 0`**
24. `Redis swap` 文件分成了很多的 `page`，一个对象可以保存在多个 `page` 上面，但一个 `page` 上不能被多个对象共享，`vm-page-size` 是要根据存储的 数据大小来设定的，作者建议如果存储很多小对象，`page` 大小最好设置为 `32` 或者 `64bytes`；如果存储很大大对象，则可以使用更大的 `page`，如果不确定，就使用默认值
    **`vm-page-size 32`**
25. 设置 `swap` 文件中的 `page` 数量，由于页表（一种表示页面空闲或使用的 `bitmap`）是在放在内存中的，，在磁盘上每 `8` 个 `pages` 将消耗 `1byte` 的内存。
    **`vm-pages 134217728`**
26. 设置访问swap文件的线程数,最好不要超过机器的核数,如果设置为 `0`,那么所有对 `swap` 文件的操作都是串行的，可能会造成比较长时间的延迟。默认值为 `4`
    **`vm-max-threads 4`**
27. 设置在向客户端应答时，是否把较小的包合并为一个包发送，默认为开启
    **`glueoutputbuf yes`**
28. 指定在超过一定的数量或者最大的元素超过某一临界值时，采用一种特殊的哈希算法
    **`hash-max-zipmap-entries 64`**
    **`hash-max-zipmap-value 512`**
29. 指定是否激活重置哈希，默认为开启（后面在介绍 `Redis` 的哈希算法时具体介绍）
    **`activerehashing yes`**
30. 指定包含其它的配置文件，可以在同一主机上多个 `Redis` 实例之间使用同一份配置文件，而同时各个实例又拥有自己的特定配置文件
    **`include /path/to/local.conf`**
