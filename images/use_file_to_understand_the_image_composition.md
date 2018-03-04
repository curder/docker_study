# 使用 Dockerfile 定制镜像

镜像的定制实际上就是定制每一层所添加的配置、文件。

如果我们可以把每一层修改、安装、构建、操作的命令都写入一个脚本，用这个脚本来构建、定制镜像，那么之前使用`docker commit`命令生成镜像中的种种问题就会得到解决。

比如无法重复的问题、镜像构建透明性的问题、体积的问题就都会解决。这个脚本就是 `Dockerfile`。

`Dockerfile` 是一个文本文件，其内包含了一条条的指令\(**Instruction**\)，每一条指令构建一层，因此每一条指令的内容，就是描述该层应当如何构建。

还以之前使用`docker commit`定制 `nginx` 镜像为例，这次我们使用 `Dockerfile` 来定制。

## 新建`Dockerfile`

在一个空白目录中，建立一个文本文件，并命名为 `Dockerfile`

```
➜ mkdir mynginx && cd mynginx && touch Dockerfile
```

## 编辑`Dockerfile`

向`Dockerfile`文件中写入如下内容：

```
FROM nginx
RUN echo 'Hello, Docker!' > /usr/share/nginx/html/index.html
```

这个 `Dockerfile` 很简单，一共就两行。涉及到了两条指令，`FROM` 和 `RUN`。

## 构建镜像

在 Dockerfile 文件所在目录执行 [docker build](/orders/build.md)

```
➜  mynginx docker build -t nginx:v3 .
Sending build context to Docker daemon  2.048kB
Step 1/2 : FROM nginx
 ---> 3f8a4339aadd
Step 2/2 : RUN echo 'Hello, Docker!' > /usr/share/nginx/html/index.html
 ---> Running in c9c9fca75e0f
Removing intermediate container c9c9fca75e0f
 ---> 579738872a32
Successfully built 579738872a32
Successfully tagged nginx:v3
```

从命令的输出结果中，我们可以清晰的看到镜像的构建过程。

在 Step 2 中，如同我们之前所说的那样，RUN 指令启动了一个容器 c9c9fca75e0f，执行了所要求的命令，并最后提交了这一层 579738872a32，随后删除了所用到的这个容器 c9c9fca75e0f。

在这里我们指定了最终镜像的名称 `-t nginx:v3`，构建成功后，我们可以像使用`docker commit`运行 `nginx:v2` 那样来运行这个镜像，其结果会和 `nginx:v2` 一样。

这里使用了`docker build`命令进行镜像构建。其格式为：

```
docker build [选项] <上下文路径/URL/->
```

## 运行镜像

使用`docker images nginx`查看所有`nginx`相关的镜像，并运行`nginx:v3`这个我们使用`Dockerfile`文件构建出来的目标镜像。

```
➜  mynginx docker images nginx
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
nginx               v3                  579738872a32        2 minutes ago       108MB
nginx               v2                  c82ebcae988f        21 minutes ago      108MB
nginx               latest              3f8a4339aadd        2 months ago        108MB
➜  mynginx docker run --name webserver3 -d -p 8890:80 nginx:v3
a84759fc3b4afe07cec9258f5e880f4e2d4e6bdc2d99bf96bbeb1fc3a9da33d1
➜  mynginx
```

> 映射容器端口 `80` 端口，到本地主机的`8890`端口。

## 访问结果

使用`http://localhost:8890`访问运行中的`nginx:v3`容器。

![](/assets/nginx-modify-welcome-page-hello-docker-from-dockerfile.png)

