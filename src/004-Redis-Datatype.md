# `Redis` 数据类型
> `Redis` 支持五种数据类型：`string` `hash` `list` `set` `zset`

## `String`（字符串）
`string` 是 `redis` 最基本的类型，你可以理解成与 `Memcached` 一模一样的类型，一个 `key` 对应一个 `value`。
`string` 类型是二进制安全的。意思是 `redis` 的 `string` 可以包含任何数据。比如 `jpg` 图片或者序列化的对象。
`string` 类型是 `Redis` 最基本的数据类型，一个键最大能存储 `512MB`。

**实例**
```powershell
redis 127.0.0.1:6379> SET name "jeremy"
OK
redis 127.0.0.1:6379> GET name
"jeremy"
```
在以上实例中我们使用了 `Redis` 的 `SET` 和 `GET` 命令。键为 `name`，对应的值为 `jeremy`。
**注意**：一个键最大能存储 `512MB`。

## `Hash`（哈希）
`Redis hash` 是一个键值 (`key=>value`) 对集合。
`Redis hash` 是一个 `string` 类型的 `field` 和 `value` 的映射表，`hash` 特别适合用于存储对象。

**实例**
```powershell
redis 127.0.0.1:6379> HMSET user:1 username jeremy password 123 points 200
OK
redis 127.0.0.1:6379> HGETALL user:1
1) "username"
2) "jeremy"
3) "password"
4) "123"
5) "points"
6) "200"
redis 127.0.0.1:6379>
```
以上实例中 `hash` 数据类型存储了包含用户脚本信息的用户对象。实例中我们使用了 `Redis HMSET`, `HGETALL` 命令，`user:1` 为键值。每个 `hash` 可以存储 2^32^ - 1 键值对（`40`多亿）。

## `List`（列表）
`Redis` 列表是简单的字符串列表，按照插入顺序排序。你可以添加一个元素到列表的头部（左边）或者尾部（右边）。

**实例**
```powershell
redis 127.0.0.1:6379> lpush obj redis
(integer) 1
redis 127.0.0.1:6379> lpush obj mongodb
(integer) 2
redis 127.0.0.1:6379> lpush obj rabitmq
(integer) 3
redis 127.0.0.1:6379> lrange obj 0 10
1) "rabitmq"
2) "mongodb"
3) "redis"
redis 127.0.0.1:6379>
```
列表最多可存储 2^32^ - 1 元素 (`4294967295`, 每个列表可存储 `40` 多亿)。

## `Set`（集合）
`Redis` 的 `Set` 是 `string` 类型的无序集合。
集合是通过哈希表实现的，所以添加，删除，查找的复杂度都是 O(1)。
### `sadd` 命令
添加一个 `string` 元素到 `key` 对应的 `set` 集合中，成功返回 `1`,如果元素已经在集合中返回`0`,`key` 对应的 `set` 不存在返回错误。
```powershell
sadd key member
```

**实例**
```powershell
redis 127.0.0.1:6379> sadd sobj redis
(integer) 1
redis 127.0.0.1:6379> sadd sobj mongodb
(integer) 1
redis 127.0.0.1:6379> sadd sobj rabitmq
(integer) 1
redis 127.0.0.1:6379> sadd sobj rabitmq
(integer) 0
redis 127.0.0.1:6379> smembers sobj
1) "rabitmq"
2) "mongodb"
3) "redis"
```
**注意**：以上实例中 `rabitmq` 添加了两次，但根据集合内元素的唯一性，第二次插入的元素将被忽略。
集合中最大的成员数为 2^32^ - 1 (`4294967295`, 每个集合可存储`40`多亿个成员)。

## `zset`(`sorted set`：有序集合)
`Redis` `zset` 和 `set` 一样也是 `string` 类型元素的集合,且不允许重复的成员。
不同的是每个元素都会关联一个 `double` 类型的分数。`redis` 正是通过分数来为集合中的成员进行从小到大的排序。
`zset` 的成员是唯一的,但分数(`score`)却可以重复。
### `zadd` 命令
添加元素到集合，元素在集合中存在则更新对应 `score`
```powershell
zadd key score member 
```
**实例**
```powershell
redis 127.0.0.1:6379> zadd zobj 0 redis
(integer) 1
redis 127.0.0.1:6379> zadd zobj 0 mongodb
(integer) 1
redis 127.0.0.1:6379> zadd zobj 0 rabitmq
(integer) 1
redis 127.0.0.1:6379> zadd zobj 0 rabitmq
(integer) 0
redis 127.0.0.1:6379> ZRANGEBYSCORE zobj 0 1000
1) "redis"
2) "mongodb"
3) "rabitmq"
```
