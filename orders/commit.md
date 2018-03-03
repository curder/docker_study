# Docker commit 命令


从容器创建一个新的镜像。

## 语法

```
docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
```

## 参数说明

参数 | 说明
 - | -
`-a` | 提交的镜像作者；
`-c` | 使用Dockerfile指令来创建镜像；
`-m` | 提交时的说明文字；
`-p` | 在commit时，将容器暂停。

## 实例

将容器`3294f2a0efce`保存为新的镜像,并添加提交人信息和说明信息。

```
docker commit -a "some commit message" -m "my apache" 3294f2a0efce  mymysql:v1 
```