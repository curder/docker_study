# Docker push 命令



将本地的镜像上传到镜像仓库,要先登陆到镜像仓库

## 语法

```
docker push [OPTIONS] NAME[:TAG]
```

## 参数说明


参数 | 说明
- | -
`--disable-content-trust` | 忽略镜像的校验,默认开启



## 实例
上传本地镜像`myapache:v1`到镜像仓库中。

```
docker push myapache:v1
```