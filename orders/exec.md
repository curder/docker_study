# Docker exec 命令

在运行的容器中执行命令

## 语法

```
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```

## 参数说明

参数 | 说明
- | -
`-d` | 分离模式: 在后台运行
`-i` | 即使没有附加也保持STDIN 打开
`-t` | 分配一个伪终端

## 实例

- 在容器mynginx中以交互模式执行容器内`/root/backup.sh`脚本

```
docker exec -it mynginx /bin/sh /root/backup.sh
```

- 在容器mynginx中开启一个交互模式的终端

```
$ docker exec -i -t  mynginx /bin/bash
#
```