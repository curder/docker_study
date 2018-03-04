# RUN 执行命令

RUN 指令是用来执行命令行命令的。由于命令行的强大能力，RUN 指令在定制镜像时是最常用的指令之一。

其格式有两种：

* _shell_ 格式：`RUN <命令>`，就像直接在命令行中输入的命令一样。

```
RUN echo 'Hello, Docker!' > /usr/share/nginx/html/index.html
```

* _exec_ 格式：`RUN ["可执行文件", "参数1", "参数2"]`，这更像是函数调用中的格式。

既然`RUN`命令就像 `Shell` 脚本一样可以执行命令，那么我们是否就可以像 `Shell` 脚本一样把每个命令对应一个 `RUN` 呢？比如这样：

```
FROM debian:jessie

RUN apt-get update
RUN apt-get install -y gcc libc6-dev make
RUN wget -O redis.tar.gz "http://download.redis.io/releases/redis-3.2.5.tar.gz"
RUN mkdir -p /usr/src/redis
RUN tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1
RUN make -C /usr/src/redis
RUN make -C /usr/src/redis install
```

`Dockerfile` 中每一个指令都会建立一层，`RUN` 也不例外。每一个 `RUN` 的行为，就和我们使用 `docker commit` 手工建立镜像的过程一样。

新建立一层，在其上执行这些命令，执行结束后，`commit` 这一层的修改，构成新的镜像。

而上面的这种写法，创建了 **7** 层镜像。

这是完全没有意义的，而且很多运行时不需要的东西，都被装进了镜像里，比如编译环境、更新的软件包等等。

结果就是产生非常臃肿、非常多层的镜像，不仅仅增加了构建部署的时间，也很容易出错。

> Union FS 是有最大层数限制的，比如 AUFS，曾经是最大不得超过 42 层，现在是不得超过 127 层。

上面的 Dockerfile 正确的写法应该是这样：

```
FROM debian:jessie

RUN buildDeps='gcc libc6-dev make' \
    && apt-get update \
    && apt-get install -y $buildDeps \
    && wget -O redis.tar.gz "http://download.redis.io/releases/redis-3.2.5.tar.gz" \
    && mkdir -p /usr/src/redis \
    && tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1 \
    && make -C /usr/src/redis \
    && make -C /usr/src/redis install \
    && rm -rf /var/lib/apt/lists/* \
    && rm redis.tar.gz \
    && rm -r /usr/src/redis \
    && apt-get purge -y --auto-remove $buildDeps
```

之前所有的命令只有一个目的，就是编译、安装 `redis` 可执行文件。因此没有必要建立很多层。因此，这里没有使用很多个 RUN 对一一对应不同的命令，而是仅仅使用一个 `RUN` 指令，并使用`&&` 将各个所需命令串联起来。将之前的 **7** 层，简化为了 **1** 层。在撰写 `Dockerfile` 的时候，要经常提醒自己这并不是在写 `Shell` 脚本，而是在定义每一层该如何构建。

并且，这里为了格式化还进行了换行。`Dockerfile` 支持 `Shell` 类的行尾添加 `\` 的命令换行方式，以及行首 `#` 进行注释的格式。比如换行、缩进、注释等，会让维护、排障更为容易。

此外，还可以看到这一组命令的最后添加了清理工作的命令，删除了为了编译构建所需要的软件，清理了所有下载、展开的文件，并且还清理了 `apt` 缓存文件。这是很重要的一步，镜像是多层存储，每一层的东西并不会在下一层被删除，会一直跟随着镜像。因此镜像构建时，一定要确保每一层只添加真正需要添加的东西，任何无关的东西都应该清理掉。

