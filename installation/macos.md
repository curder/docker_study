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