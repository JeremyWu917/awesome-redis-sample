# `Redis` 哈希
`Redis hash` 是一个 `string` 类型的 `field` 和 `value` 的映射表，`hash` 特别适合用于存储对象。
`Redis` 中每个 `hash` 可以存储 `2^32^ - 1` 键值对（ `40` 多亿）。

**实例**
```powershell
> HMSET user_infos name "Jeremy Wu" description "Redis User Information Hash Table" age 30 gender "Male" address "Jiangsu, Wuxi, Xinwu, Changjiang street 305-206" state 0
OK
> HGETALL user_infos
30
gender
name
"Jeremy
Wu"
description
"Redis
User
Information
Hash
Table"
age
"Male"
address
"Jiangsu,
Wuxi,
Xinwu,
Changjiang
street
305-206"
state
0
```

## `Redis hash` 命令
下表列出了 `redis hash` 基本的相关命令:
序号|命令|描述
-|-|-
`1`|`HDEL key field2 [field2]`|删除一个或多个哈希表字段
`2`|`HEXISTS key field`|查看哈希表 `key` 中，指定的字段是否存在。
`3`|`HGET key field`|获取存储在哈希表中指定字段的值
`4`|`HGETALL key`|获取在哈希表中指定 `key` 的所有字段和值
`5`|`HINCRBY key field increment`|为哈希表 `key` 中的指定字段的整数值加上增量 `increment` 。
`6`|`HINCRBYFLOAT key field increment`|为哈希表 `key` 中的指定字段的浮点数值加上增量 `increment` 。
`7`|`HKEYS key`|获取所有哈希表中的字段
`8`|`HLEN key`|获取哈希表中字段的数量
`9`|`HMGET key field1 [field2]`|获取所有给定字段的值
`10`|`HMSET key field1 value1 [field2 value2 ]`|同时将多个 `field-value` (域-值)对设置到哈希表 `key` 中。
`11`|`HSET key field value`|将哈希表 `key` 中的字段 `field` 的值设为 `value` 。
`12`|`HSETNX key field value`|只有在字段 `field` 不存在时，设置哈希表字段的值。
`13`|`HVALS key`|获取哈希表中所有值
`14`|`HSCAN key cursor [MATCH pattern] [COUNT count]`| 迭代哈希表中的键值对。

