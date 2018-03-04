# Docker 命令大全

## 容器生命周期管理

| 命令 | 作用 |
| --- | --- |
| [run](/orders/run.md) | 创建一个新的容器并运行一个命令 |
| [start](/orders/start.md) | 启动一个容器 |
| [stop](/orders/stop.md) | 关闭一个容器 |
| [restart](/orders/restart.md) | 重启一个容器 |
| [kill](/orders/kill.md) | 杀掉一个运行中的容器 |
| [rm](/orders/rm.md) | 删除一个或多少容器 |
| [pause/unpause](/orders/pause_unpause.md) | 暂停、恢复容器中所有的进程 |
| [create](/orders/create.md) | 创建一个新的容器但不启动它 |
| [exec](/orders/exec.md) | 在运行的容器中执行命令 |

## 容器操作

| 命令 | 作用 |
| --- | --- |
| [ps](/orders/ps.md) | 列出容器 |
| [inspect](/orders/inspect.md) | 获取容器/镜像的元数据 |
| [top](/orders/top.md) | 查看容器中运行的进程信息，支持 ps 命令参数。 |
| [attach](/orders/attach.md) | 连接到正在运行中的容器 |
| [exec](/orders/exec.md)| 连接到正在运行中的容器 |
| [events](/orders/events.md) | 从服务器获取实时事件 |
| [logs](/orders/logs.md) | 获取容器的日志 |
| [wait](/orders/wait.md) | 阻塞运行直到容器停止，然后打印出它的退出代码。 |
| [export](/orders/export.md) | 将文件系统作为一个tar归档文件导出到STDOUT |
| [port](/orders/port.md) | 列出指定的容器的端口映射，或者查找将PRIVATE\_PORT NAT到面向公众的端口 |

## 容器`rootfs`命令

| 命令 | 作用 |
| --- | --- |
| [commit](/orders/commit.md) | 从容器创建一个新的镜像 |
| [cp](/orders/cp.md) | 用于容器与主机之间的数据拷贝 |
| [diff](/orders/diff.md) | 检查容器里文件结构的更改 |

## 镜像仓库

| 命令 | 作用 |
| --- | --- |
| [login](/orders/login.md) | 登陆到一个Docker镜像仓库，如果未指定镜像仓库地址，默认为官方仓库 Docker Hub |
| [logout](/orders/logout.md) | 登出一个Docker镜像仓库，如果未指定镜像仓库地址，默认为官方仓库 Docker Hub |
| [pull](/orders/pull.md) | 从镜像仓库中拉取或者更新指定镜像 |
| [push](/orders/push.md) | 将本地的镜像上传到镜像仓库,要先登陆到镜像仓库 |
| [search](/orders/search.md) | 从Docker Hub查找镜像 |

## 本地镜像管理

| 命令 | 作用 |
| --- | --- |
| [images](/orders/images.md) | 列出本地镜像 |
| [rmi](/orders/rmi.md) | 删除本地一个或多少镜像 |
| [tag](/orders/tag.md) | 标记本地镜像，将其归入某一仓库 |
| [build](/orders/build.md) | 使用Dockerfile创建镜像 |
| [history](/orders/history.md) | 查看指定镜像的创建历史 |
| [save](/orders/save.md) | 将指定镜像保存成 tar 归档文件 |
| [import](/orders/import.md) | 从归档文件中创建镜像 |

## `info|version`

| 命令 | 作用 |
| --- | --- |
| [info](/orders/info.md) | 显示 Docker 系统信息，包括镜像和容器数... |
| [version](/orders/version.md) | 显示 Docker 版本信息 |



