# Docker create 命令

创建一个新的容器但不启动它


用法同 [docker run](/orders/run.md)

## 语法

```
docker create [OPTIONS] IMAGE [COMMAND] [ARG...]
```

语法同 [docker run](/orders/run.md)

## 实例

- 使用docker镜像nginx:latest创建一个容器,并将容器命名为mynginx

```
docker create  --name mynginx  nginx:latest
```
