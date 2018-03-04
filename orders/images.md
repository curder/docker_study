# Docker images 命令

列出本地镜像。

## 语法

```
docker images [OPTIONS] [REPOSITORY[:TAG]]
```

## 参数说明

参数 | 说明
- | -
`-a` |列出本地所有的镜像（含中间映像层，默认情况下，过滤掉中间映像层）；
`--digests` | 显示镜像的摘要信息；
`-f` | 显示满足条件的镜像；
`--format` | 指定返回值的模板文件；
`--no-trunc` | 显示完整的镜像信息；
`-q` | 只显示镜像ID。


## 实例

- 查看本地镜像列表

```
docker images
```

- 列出本地镜像中REPOSITORY为ubuntu的镜像列表

```
docker images  ubuntu
```

- 通过`since`关键字过滤镜像对应镜像之后建立的镜像

```
➜  ~ docker images -f since=ubuntu:16.04
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
debian              jessie              ce40fb3adcc6        2 weeks ago         123MB
mysql               5.7                 f008d8ff927d        6 weeks ago         409MB
mysql               latest              f008d8ff927d        6 weeks ago         409MB
```
> 希望看到在 `ubuntu:16.04` 之后建立的镜像，可以用下面的命令
> 想查看某个位置之前的镜像也可以，只需要把 `since` 换成 `before` 即可

- 以特定格式显示

```
➜  ~ docker images -q
ce40fb3adcc6
f008d8ff927d
f008d8ff927d
2a4cca5ac898
2a4cca5ac898
02a63d8b2bfa
26d147d2310f
ff426288ea90
3f8a4339aadd
6fae60ef3446
```

```
➜  ~ docker images --format "{{.ID}}: {{.Repository}}"
ce40fb3adcc6: debian
f008d8ff927d: mysql
f008d8ff927d: mysql
2a4cca5ac898: ubuntu
2a4cca5ac898: ubuntu
02a63d8b2bfa: ubuntu
26d147d2310f: ubuntu
ff426288ea90: centos
3f8a4339aadd: nginx
6fae60ef3446: training/webapp
```

```
➜  ~ docker images --format "table {{.ID}}\t{{.Repository}}\t{{.Tag}}"
IMAGE ID            REPOSITORY          TAG
ce40fb3adcc6        debian              jessie
f008d8ff927d        mysql               5.7
f008d8ff927d        mysql               latest
2a4cca5ac898        ubuntu              16.04
2a4cca5ac898        ubuntu              latest
02a63d8b2bfa        ubuntu              14.04
26d147d2310f        ubuntu              17.10
ff426288ea90        centos              latest
3f8a4339aadd        nginx               latest
6fae60ef3446        training/webapp     latest
```



## 其他

### 磁盘占用

`docker images` 列表中的镜像体积总和并非是所有镜像实际硬盘消耗。

由于 Docker 镜像是多层存储结构，并且可以继承、复用，因此不同镜像可能会因为使用相同的基础镜像，从而拥有共同的层。

由于 Docker 使用 Union FS，相同的层只需要保存一份即可，因此实际镜像硬盘占用空间很可能要比这个列表镜像大小的总和要小的多。

可以通过以下命令来便捷的查看镜像、容器、数据卷所占用的空间。

```
➜  ~ docker system df
TYPE                TOTAL               ACTIVE              SIZE                RECLAIMABLE
Images              8                   3                   1.626GB             1.089GB (66%)
Containers          12                  0                   62B                 62B (100%)
Local Volumes       5                   0                   234MB               234MB (100%)
Build Cache                                                 0B                  0B
```



