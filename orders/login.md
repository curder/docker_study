# Docker login 命令


登陆到一个Docker镜像仓库，如果未指定镜像仓库地址，默认为官方仓库 Docker Hub

## 语法

```
docker login [OPTIONS] [SERVER]
```

## 参数说明

参数 | 说明
- | -
-u | 登陆的用户名
-p | 登陆的密码

## 实例

- 登陆到Docker Hub

```
docker login -u 用户名 -p 密码
```