### zk in k8s
```
1.需要创建一个名为: zk-secret 的secret用来拉取个人私有仓库下的zk镜像
2.storageClass这里采用NFS作为后端存储进行动态PV提供
3.注意命名空间，这里我用的是default。必要时请自行修改
4.这里用到的镜像，我已经放到了我自己的镜像仓库
```
