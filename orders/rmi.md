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

- 强制删除本地镜像`ubuntu:latest`

```
docker rmi -f ubuntu:latest
```

-  要删除所有仓库名为 `redis` 的镜像

```
docker rmi $(docker image ls -q redis)
```

- 删除所有在 `mongo:3.2` 之前的镜像

```
docker rmi $(docker image ls -q -f before=mongo:3.2)
```