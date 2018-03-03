# Docker save 命令


将指定镜像保存成 `tar` 归档文件。

## 语法

```
docker save [OPTIONS] IMAGE [IMAGE...]
```


## 参数说明

参数 | 说明
- | -
-o | 输出到的文件。

## 实例

将镜像`luo/ubuntu:v1` 生成`my_ubuntu_v1.tar`文档

```
docker save -o my_ubuntu_v1.tar luo/ubuntu:v1
``` 

## 相关命令推荐

[docker import](/orders/import.md)