# Docker pull 命令

从镜像仓库中拉取或者更新指定镜像

## 语法

```
docker pull [OPTIONS] NAME[:TAG|@DIGEST]
```

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