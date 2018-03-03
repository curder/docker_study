# Docker info 命令


显示 Docker 系统信息，包括镜像和容器数


## 语法

```
docker info [OPTIONS]
```

## 实例

查看docker系统信息。

```
➜  ~ docker info
Containers: 12
 Running: 1
 Paused: 0
 Stopped: 11
Images: 8
Server Version: 17.12.0-ce
Storage Driver: overlay2
 Backing Filesystem: extfs
 Supports d_type: true
 Native Overlay Diff: true
Logging Driver: json-file
Cgroup Driver: cgroupfs
Plugins:
 Volume: local
 Network: bridge host ipvlan macvlan null overlay
 Log: awslogs fluentd gcplogs gelf journald json-file logentries splunk syslog
Swarm: inactive
Runtimes: runc
Default Runtime: runc
Init Binary: docker-init
containerd version: 89623f28b87a6004d4b785663257362d1658a729
runc version: b2567b37d7b75eb4cf325b77297b140ea686ce8f
...
```