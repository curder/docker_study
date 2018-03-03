# Docker search 命令

从Docker Hub查找镜像

## 语法

```
docker search [OPTIONS] TERM
```

## 参数说明

参数 | 说明
- | -
`--automated` | 只列出 automated build类型的镜像；
`--no-trunc` | 显示完整的镜像描述；
`-s` | 列出收藏数不小于指定值的镜像。

## 实例

从Docker Hub查找所有镜像名包含nginx，并且收藏数大于10的镜像

```
docker search -s 10 nginx
```