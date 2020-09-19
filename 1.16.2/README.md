下载清单文件

```
wget https://gitee.com/Outsrkem/flannel/raw/master/1.16.2/kube-flannel.patch
wget https://gitee.com/Outsrkem/flannel/raw/master/1.16.2/kube-flannel.yml

```

修改补丁

```
17  +        image: registry.cn-shanghai.aliyuncs.com/outsrkem/flannel:v0.12.0-amd64
18           command:
19           - /opt/bin/flanneld
20           args:
21           - --ip-masq
22           - --kube-subnet-mgr
23  +        - --iface=eth0  补丁文件此处修改为实际网卡名
24           resources:
```

给清单文件打入补丁

```
patch -p0 < kube-flannel.patch
```


