# ek8-for-centos7-v1.24.1下载：

[下载](https://github.com/catman002/kubernetes-ek8/releases)


# EK8说明：
```
Ek8[easy kubernetes]是一款快速安装和高可用性的kubernetes产品，简单易用 【v1.23.3及以上版本go语言重新实现】
通过一条命令即可完成k8s集群环境安装、配置。该产品具有以下特点：
1) 集群安装包主要由Kube-apiserver、kuber-controller-manager、kuber-scheduler、kuelet、coredns、calico、etcd、keepalived、haproxy、docker、containerd和registry组成
2) 支持灵活的安装类型。用户可以选择全部安装或选择性安装
3) 安装程序自动检查配置。包括IP合法性，服务器连通性、帐户可用性和IP可用性
4) 安装程序自动设置群集服务器环境所需的环境
```
- **下载ek8-for-v1.2x.x-on-{os}.tar.gz, 拷贝到安装机并解压**
- **安装前先配置 config.cfg 文件，设置相关服务器信息[注释为 “需修改“ 的是必须要修改]**
- **请确保ek8安装程序所在的计算机可以通过SSH登录集群服务器，并且各个服务器的root密码一致**
- **安装机支持centos和mac；集群服务器必须为centos7.x**

```
- 当前的ek8版本支持的集群服务器为CentOS7.x；安装机可以是mac或者centos7.x
- 如果您需要支持k8s更高版本或支持其他服务器版本，请在GitHub上给作者留言

```

# 安装步骤：
```
1)修改config.cfg，配置服务器相关信息
2)ek8 create all , 根据配置生成集群可安装文件（执行1次即可，初次执行需要提供产品秘锁：123456）
3)ek8 install all，开始安装集群(根据提示输入远程服务器的ssh的root密码)
```

# 注意:
```
- 初次安装需要产品key：123456 
- 安装过充中需要提供集群服务器登录密码，根据提示输入即可！
- 安装前，在安装机安装 go1.18.x 环境;安装机包含sshpass
- kubernetes1.24.x及以上版本容器用的是containerd!!!
```

# 安装示例：
```
- ek8 help 查看命令帮助
- ek8 install  all 安装集群环境所需的所有组件 (全新安装采用)
- ek8 install  all  --exclude=docker,etcd 安装集群环境所需的所有组件,但无需重新安装docker和etcd
- ek8 install kubelet,kubeproxy 重新安装kubelet和kubeproxy
- ek8 delete all 删除集群环境
```
