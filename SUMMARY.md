# Docker

* [安装 Docker](installation/README.md)
    * [MacOS](installation/macos.md)
    * [Windows PC](installation/windows.md)
    * [CentOS](installation/centos.md)

* [使用 Docker 镜像](images/README.md)
    * [利用 commit 理解镜像构成](images/use_commit_to_understand_the_image_composition.md)
    * [使用 Dockerfile 定制镜像](images/use_file_to_understand_the_image_composition.md)
    * [Dockerfile指令](dockerfile/README.md)
        
        * [FROM 指定基础镜像](dockerfile/from.md)
        * [RUN 执行命令](dockerfile/run.md)
        * [COPY 复制文件](dockerfile/copy.md)
        * [ADD 更高级的复制文件](dockerfile/add.md)
        * [CMD 启动容器命令](dockerfile/cmd.md)
        * [ENTRYPOINT 入口点](dockerfile/entrypoint.md)
        * [ENV 环境变量设置](dockerfile/env.md)
        * [ARG 构建参数](dockerfile/arg.md)    
        * [VOLUME 定义匿名卷](dockerfile/volume.md)
        * [EXPOSE 暴露端口](dockerfile/expose.md)
        * [WORKDIR 指定工作目录](dockerfile/workdir.md)
        * [USER 指定当前用户](dockerfile/user.md)
        * [HEALTHCHECK 健康检查](dockerfile/healthcheck.md)
        * [ONBUILD 为他人做嫁衣](dockerfile/onbuild.md)
            
* [Docker 常用命令](orders/docker_commonly_used_commands.md)

* [Docker命令大全](orders/README.md)
     
    * [run 创建并运行容器](/orders/run.md)
    * [start 启动被停掉的容器](/orders/start.md)
    * [stop 停止正在运行的容器](/orders/stop.md)
    * [restart 重启容器](/orders/restart.md)
    * [kill 杀掉运行中的容器](/orders/kill.md)
    * [rm 删除容器](/orders/rm.md)
    * [pause/unpause 暂停或恢复容器中的进程](/orders/pause_unpause.md)
    * [create 创建一个新的容器但不启动它](/orders/create.md)
    * [exec 在运行的容器中执行命令](/orders/exec.md)
    
    * [ps 列出容器](/orders/ps.md)
    * [inspect 获取容器/镜像的元数据](/orders/inspect.md)
    * [top 查看容器中运行的进程信息](/orders/top.md)
    * [attach 连接到正在运行中的容器](/orders/attach.md)
    * [events 从服务器获取实时事件](/orders/events.md)
    * [logs 获取容器的日志](/orders/logs.md)
    * [wait 阻塞运行直到容器停止，然后打印出它的退出代码](/orders/wait.md)
    * [export 将文件系统作为一个tar归档文件导出到STDOUT](/orders/export.md)
    * [port 列出指定的容器的端口映射](/orders/port.md)
    
    * [commit 从容器创建一个新的镜像](/orders/commit.md)
    * [cp 用于容器与主机之间的数据拷贝](/orders/cp.md)
    * [diff 检查容器里文件结构的更改](/orders/diff.md)
    
    * [login 登陆到一个Docker镜像仓库](/orders/login.md)
    * [logout 退出登录到一个Docker镜像仓库](/orders/logout.md)
    * [pull 从镜像仓库中拉取或者更新指定镜像](/orders/pull.md)
    * [push 将本地的镜像上传到镜像仓库](/orders/push.md)
    * [search 从Docker Hub查找镜像](/orders/search.md)
    
    * [images 列出本地镜像](/orders/images.md)
    * [rmi 删除本地一个或多少镜像](/orders/rmi.md)
    * [tag 标记本地镜像，将其归入某一仓库](/orders/tag.md)
    * [build 使用Dockerfile创建镜像](/orders/build.md)
    * [history 查看指定镜像的创建历史](/orders/history.md)
    * [save 将指定镜像保存成 tar 归档文件](/orders/save.md)
    * [import 从归档文件中创建镜像](/orders/import.md)
    
    * [info 显示 Docker 系统信息](/orders/info.md)
    * [version 显示 Docker 版本信息](/orders/version.md)
    
    