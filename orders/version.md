# Docker version 命令

docker version :显示 Docker 版本信息。

## 语法

```
docker version [OPTIONS]
```

## 参数说明

参数 | 说明
- | -
-f | 指定返回值的模板文件。


## 实例

- 显示 Docker 版本信息

```
➜  ~ docker version
Client:
 Version:	17.12.0-ce
 API version:	1.35
 Go version:	go1.9.2
 Git commit:	c97c6d6
 Built:	Wed Dec 27 20:03:51 2017
 OS/Arch:	darwin/amd64

Server:
 Engine:
  Version:	17.12.0-ce
  API version:	1.35 (minimum version 1.12)
  Go version:	go1.9.2
  Git commit:	c97c6d6
  Built:	Wed Dec 27 20:12:29 2017
  OS/Arch:	linux/amd64
  Experimental:	true
```