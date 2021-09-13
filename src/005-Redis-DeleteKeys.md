# `Redis` 清理数据

1. 首先通过密码登陆 `redis`
```powershell
>redis-cli
>auth 密码
```

2. 执行清理前查看(若不需要清理全部则清理指定 `key` 即可)
```powershell
>keys * //查看所有key值，此命令正式服务器不要使用，会炸，改用scan
>scan 0 count 1000
```

3. 清理 `redis`
```powershell
>del key //①删除指定key
>Flushdb //②删除当前数据库中的所有Key
>flushall //③删除所有数据库中的key
```
