+++
title = "Deploy Kubernetes"
description = ""
tags = [
    "deploy",
    "kubernetes",
]
<<<<<<< HEAD
date = "2018-09-19"
=======
date = "2019-09-19"
>>>>>>> add posts
categories = [
    "kubernetes",
]
menu = "main"
+++

## local up cluster
```shell
<<<<<<< HEAD
cd $GOPATH/src/k8s.io/kubernetes
hack/local-up-cluster.sh
# success info:
# Local Kubernetes cluster is running. Press Ctrl-C to shut it down.

# open another terminal/tab
export KUBECONFIG=/var/run/kubernetes/admin.kubeconfig
cd $GOPATH/src/k8s.io/kubernetes
cluster/kubectl.sh get node
```
### Debug
1. The `kube-dns` Pod is `Running` but `Ready: 2/3`
```
NAME                       READY     STATUS    RESTARTS   AGE
kube-dns-7f59844b4-gxl87   2/3       Running   111        102m
```
When describing the Pod
```
Readiness probe failed
Liveness probe failed
```
It happens frequently in a env with proxy.

*Solutions*
```shell
unset http_proxy http_proxy
hack/local-up-cluster.sh

# if no access to internet after `unset ...`
# download `cfssl` first 
# fetch the link in `hack/lib/util.sh`:
grep -E "curl.*cfssl" hack/lib/util.sh
```


## kubeadm
## kops
=======
cde $GOPATH/src/k8s.io/kubernetes
hack/local-up-cluster.sh
`
>>>>>>> add posts
