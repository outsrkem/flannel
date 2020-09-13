

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

```
patch -p0 < kube-flannel.patch
```


