# FROM 指定基础镜像


所谓定制镜像，那一定是以一个镜像为基础，在其上进行定制。

就像我们之前运行了一个 `nginx` 镜像的容器，再进行修改一样，基础镜像是必须指定的。而 `FROM` 就是指定基础镜像，因此一个 `Dockerfile` 中 `FROM` 是**必备的指令**，**并且必须是第一条指令**。


在 [Docker Store](https://store.docker.com/) 上有非常多的高质量的官方镜像，有可以直接拿来使用的服务类的镜像，如 [nginx](https://store.docker.com/images/nginx/)、[redis](https://store.docker.com/images/redis/)、[mongo](https://store.docker.com/images/mongo/)、[mysql](https://store.docker.com/images/mysql/)、[httpd](https://store.docker.com/images/httpd/)、[php](https://store.docker.com/images/php/) 等；

也有一些方便开发、构建、运行各种语言应用的镜像，如 [node](https://store.docker.com/images/node)、[python](https://store.docker.com/images/python/)、[ruby](https://store.docker.com/images/ruby/)、[golang](https://store.docker.com/images/golang/) 等。

可以在其中寻找一个最符合我们最终目标的镜像为基础镜像进行定制。

如果没有找到对应服务的镜像，官方镜像中还提供了一些更为基础的操作系统镜像，如 [ubuntu](https://store.docker.com/images/ubuntu/)、[debian](https://store.docker.com/images/debian/)、[centos](https://store.docker.com/images/centos/)、[fedora](https://store.docker.com/images/fedora/)、[alpine](https://store.docker.com/images/alpine/) 等，这些操作系统的软件库为我们提供了更广阔的扩展空间。

除了选择现有镜像为基础镜像外，Docker 还存在一个特殊的镜像，名为 `scratch`。这个镜像是虚拟的概念，并不实际存在，它表示一个空白的镜像。

```
FROM scratch
...
```

如果是以 `scratch` 为基础镜像的话，意味着不以任何镜像为基础，接下来所写的指令将作为镜像第一层开始存在。