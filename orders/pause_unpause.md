# Docker pause/unpause 命令

暂停、恢复容器中所有的进程



## 语法

```
docker pause [OPTIONS] CONTAINER [CONTAINER...]
```

```
docker unpause [OPTIONS] CONTAINER [CONTAINER...]
```

## 实例

- 暂停数据库容器mynginx提供服务。

```
docker pause mynginx
```

- 恢复数据库容器mynginx提供服务。

```
docker unpause mynginx
```
