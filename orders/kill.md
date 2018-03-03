# Docker kill 命令

杀掉一个运行中的容器

## 语法

```
docker kill [OPTIONS] CONTAINER [CONTAINER...]
```

## 参数说明


-s | 向容器发送一个信号


实例
杀掉运行中的容器mynginx

w3cschool@w3cschool:~$ docker kill -s KILL mynginx
mynginx
