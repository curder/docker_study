# Docker import 命令


从归档文件中创建镜像

## 语法

```
docker import [OPTIONS] file|URL|- [REPOSITORY[:TAG]]
```

## 参数说明

参数 | 说明
- | -
-c | 应用docker 指令创建镜像
-m | 提交时的说明文字

## 实例

从镜像归档文件`my_ubuntu_v1.tar`创建镜像，命名为`luo/ubuntu:v1`

```
docker import my_ubuntu_v1.tar luo/ubuntu:v1 

docker images luo/ubuntu:v1
```

## 相关命令推荐

[docker save](/orders/save.md)