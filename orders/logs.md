# Docker logs 命令

获取容器的日志

## 语法

```
docker logs [OPTIONS] CONTAINER
```

## 参数说明

参数 | 说明
- | -
`-f` | 跟踪日志输出
`--since` | 显示某个开始时间的所有日志
`-t` | 显示时间戳
`--tail` | 仅列出最新N条容器日志

## 实例

- 跟踪查看容器mynginx的日志输出。

```
docker logs -f mynginx
```

- 查看容器`mynginx`从2018年3月3日后的最新10条日志。

```
docker logs --since="2018-03-03" --tail=10 mynginx
```