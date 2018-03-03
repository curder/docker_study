# Docker inspect 命令

获取容器/镜像的元数据


## 语法

```
docker inspect [OPTIONS] CONTAINER|IMAGE [CONTAINER|IMAGE...]
```

## 举例说明

参数 | 说明
- | -
`-f` | 指定返回值的模板文件
`-s` | 显示总的文件大小
`--type` | 为指定类型返回JSON

## 实例

- 获取镜像`mysql:5.7`的元信息

```
docker inspect mysql:5.7
[
    {
        "Id": "sha256:f008d8ff927dc527c5a57251b45cead7c9259c16a6a93c144f397eaafc103d36",
        "RepoTags": [
            "mysql:5.7",
            "mysql:latest"
        ],
        "RepoDigests": [
            "mysql@sha256:7cdb08f30a54d109ddded59525937592cb6852ff635a546626a8960d9ec34c30"
        ],
        "Parent": "",
        "Comment": "",
        "Created": "2018-01-15T21:46:14.72214555Z",
        "Container": "1b2164460e40a35986fd3db6d1eec95f03f21566c0a01c46b0162087a7f14451",
        "ContainerConfig": {
            "Hostname": "1b2164460e40",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "3306/tcp": {}
            },
...
```

- 获取正在运行的容器mymysql的 IP

```
docker inspect -f '{{.NetworkSettings.IPAddress}}' mymysql
```