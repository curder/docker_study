# Docker rmi 命令

删除本地一个或多少镜像。

## 语法

```
docker rmi [OPTIONS] IMAGE [IMAGE...]
```

参数说明：

参数 | 说明
`-f` | 强制删除
`--no-prune` | 不移除该镜像的过程镜像，默认移除

## 实例

强制删除本地镜像`ubuntu:latest`

```
docker rmi -f ubuntu:latest
```