# Docker cp 命令


用于容器与主机之间的数据拷贝。


## 语法

```
docker cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH|-

docker cp [OPTIONS] SRC_PATH|- CONTAINER:DEST_PATH
```

## 参数说明

参数 | 说明
- | -
-L | 保持源目标中的链接


## 实例

- 将主机`/Users/luo/docker`目录拷贝到容器`3294f2a0efce`的`/www`目录下

```
docker cp /Users/luo/docker 3294f2a0efce:/www/
```

- 将主机`/Users/luo/docker`目录拷贝到容器`3294f2a0efce`中，目录重命名为`www`

```
docker cp /Users/luo/docker 3294f2a0efce:/www
```

- 将容器`3294f2a0efce`的`/www`目录拷贝到主机的`/tmp`目录中。

```
docker cp  3294f2a0efce:/www /tmp/
```