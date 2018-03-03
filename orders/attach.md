# Docker attach 命令

连接到正在运行中的容器


## 语法

```
docker attach [OPTIONS] CONTAINER
```

要连接上去的容器必须正在运行，可以同时连接上同一个container来共享屏幕（与`screen`命令的`attach`类似）。

官方文档中说attach后可以通过CTRL-C来detach，但实际上经过我的测试，如果container当前在运行bash，CTRL-C自然是当前行的输入，没有退出；

如果container当前正在前台运行进程，如输出nginx的`access.log`日志，CTRL-C不仅会导致退出容器，而且还stop了。这不是我们想要的，detach的意思按理应该是脱离容器终端，但容器依然运行。

好在attach是可以带上`--sig-proxy=false`来确保`CTRL-D`或`CTRL-C`不会关闭容器。

## 实例

- 容器`mynginx`将访问日志指到标准输出，连接到容器查看访问信息

```
docker attach --sig-proxy=false mynginx
```