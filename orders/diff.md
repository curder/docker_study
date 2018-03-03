# Docker diff 命令


检查容器里文件结构的更改。

## 语法

```
docker diff [OPTIONS] CONTAINER
```

## 实例

- 查看容器`mynginx`的文件结构更改

```
➜  ~ docker diff mynginx
C /run
A /run/nginx.pid
C /var/cache/nginx
A /var/cache/nginx/client_temp
A /var/cache/nginx/fastcgi_temp
A /var/cache/nginx/proxy_temp
A /var/cache/nginx/scgi_temp
A /var/cache/nginx/uwsgi_temp
```