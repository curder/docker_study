# Docker top 命令

查看容器中运行的进程信息，支持 [ps 命令](/orders/ps.md)参数


## 语法

```
docker top [OPTIONS] CONTAINER [ps OPTIONS]
```

容器运行时不一定有`/bin/bash`终端来交互执行`top`命令，而且容器还不一定有top命令，可以使用`docker top`来实现查看container中正在运行的进程。

## 实例

- 查看容器`mynginx`的进程信息。

```
~ docker top mynginx
UID    PID    PPID    C      STIME   TTY  TIME       CMD
999    40347  40331   18     00:58   ?    00:00:02   mysqld
```

- 查看所有运行容器的进程信息。

```
for i in  `docker ps |grep Up|awk '{print $1}'`;do echo \ &&docker top $i; done
```