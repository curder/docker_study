# macOS 安装 Docker

## 系统要求
[Docker for Mac](https://docs.docker.com/docker-for-mac/) 要求系统最低为 macOS 10.10.3 Yosemite。如果系统不满足需求，可以安装 [Docker Toolbox](https://docs.docker.com/toolbox/overview/)。

## 安装

### 使用 Homebrew 安装

[Homebrew](https://brew.sh/) 的 [Cask](https://caskroom.github.io/) 已经支持 Docker for Mac，因此可以很方便的使用 Homebrew Cask 来进行安装：

```
brew cask install docker
```

### 手动下载安装

如果需要手动下载，请点击以下链接下载 [Stable](https://download.docker.com/mac/stable/Docker.dmg) 或 [Edge](https://download.docker.com/mac/edge/Docker.dmg) 版本的 Docker for Mac。

如同 macOS 下安装其它软件一样，双击下载的 `.dmg` 文件，然后将鲸鱼图标拖拽到 `Application` 文件夹即可（其间需要输入用户密码）。


### 运行

从应用中找到 `Docker` 图标或者使用Alfred查找 `Docker` 并点击运行起来。

运行之后，会在右上角菜单栏看到多了一个鲸鱼图标，这个图标表明了 Docker 的运行状态。

启动终端后，通过命令可以检查安装后的 Docker 版本。

```
☁  Docker  docker --version
Docker version 17.12.0-ce, build c97c6d6
☁  Docker  docker-compose --version
docker-compose version 1.18.0, build 8dd22a9
☁  Docker  docker-machine --version
docker-machine version 0.13.0, build 9ba6da9
```

如果 docker version、docker info 都正常的话，可以尝试运行一个 [Nginx 服务器](https://store.docker.com/images/nginx)：

```
docker run -d -p 1111:80 --name webserver nginx
```

服务运行后，可以访问 `http://localhost:1111`，如果看到了 "Welcome to nginx!"，就说明 Docker for Mac 安装成功了。

停止刚刚开启的Nginx服务器并删除它，执行下面的命令：

```
docker stop webserver
doker rm webserver
```
