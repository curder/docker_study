# Docker history 命令


查看指定镜像的创建历史。

## 语法

```
docker history [OPTIONS] IMAGE
```

## 举例说明

参数 | 说明
- | -
`-H` | 以可读的格式打印镜像大小和日期，默认为true
`--no-trunc` | 显示完整的提交记录
`-q` | 仅列出提交记录ID


## 实例

- 查看本地镜像`luo/ubuntu:v1`的创建历史

```
docker history luo/ubuntu:v1
```