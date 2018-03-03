# Docker rm 命令

删除一个或多少容器

## 语法

```
docker rm [OPTIONS] CONTAINER [CONTAINER...]
```

## 参数说明

参数 | 说明
- | -
`-f` | 通过SIGKILL信号强制删除一个运行中的容器
`-l` | 移除容器间的网络连接，而非容器本身
`-v` | `-v`删除与容器关联的卷

## 实例

- 强制删除容器`db01`、`db02`

```
docker rm -f db01、db02
```

- 移除容器nginx01对容器db01的连接，连接名db

```
docker rm -l db 
```

- 删除容器mynginx,并删除容器挂载的数据卷

```
docker rm -v mynginx
```