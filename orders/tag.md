# Docker tag 命令

标记本地镜像，将其归入某一仓库。

## 语法

```
docker tag [OPTIONS] IMAGE[:TAG] [REGISTRYHOST/][USERNAME/]NAME[:TAG]
```


## 实例


- 将镜像`ubuntu:14.04`标记为 `luo/ubuntu:v1` 镜像。

```
➜  ~ docker tag ubuntu:14.04 luo/ubuntu:v1
➜  ~ docker images luo/ubuntu:v1
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
luo/ubuntu          v1                  02a63d8b2bfa        6 weeks ago         222MB
```





## 相关命令推荐

[docker images](/orders/images.md)