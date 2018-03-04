# Docker pull 命令

从镜像仓库中拉取或者更新指定镜像

## 语法

```
docker pull [OPTIONS] NAME[:TAG|@DIGEST]
```

- Docker 镜像仓库地址：地址的格式一般是 `<域名/IP>[:端口号]`。默认地址是 Docker Hub。

- 仓库名：如之前所说，这里的仓库名是两段式名称，即 `<用户名>/<软件名>`。对于 Docker Hub，如果不给出用户名，则默认为 library，也就是官方镜像。

## 举例说明

参数 | 说明
- | -
`-a` | 拉取所有 tagged 镜像
`--disable-content-trust` | 忽略镜像的校验,默认开启

## 实例

从Docker Hub下载ubuntu最新版镜像。

```
docker pull ubuntu
```

- 从Docker Hub下载REPOSITORY为ubuntu的所有镜像。

```
docker pull -a ubuntu
```

## 相关命令推荐

[docker run](/orders/run.md)