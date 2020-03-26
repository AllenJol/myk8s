这里存放了关于构建kafka镜像的文件

```
1.当前kafka版本：kafka_2.11-0.10.2.0.tgz
2.当前JDK版本：jdk-8u161-linux-x64.tar.gz
```

如需更换版本，请更改 Dokerfile 文件

Makefile和Dockerfile放在同一个层级。构建镜像的时候直接利用Makefile进行构建。方法如下：

```
1. make build  # 利用当前Dockerfile构建一个版本的镜像
2. make start  # 构建完毕，运行一下镜像，看看内容是否正确
3. make push   # 推送到仓库
```

Makefile使用参考地址：`https://www.cnblogs.com/woshimrf/p/make-docker.html`

1.相关的jdk包和kafka的包可以自行下载。这里由于包太大，我就不贴出来了
2.`registry.cn-hangzhou.aliyuncs.com/allenjol_containers/centos:7.4.1708`为
我个人阿里云私有镜像仓库中放的centos镜像。具体可改成你们自己的centos镜像
