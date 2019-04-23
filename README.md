# k8s-roles
## 使用方法
首先下载项目
git clone https://github.com/airring/k8s-roles

四个初始化文件分别为

1. initsys 初始化操作系统
2. docker 安装docker容器
3. kubernetes 安装master节点
4. kube-node node节点加入master

修改ansible host文件
vim  /etc/ansible/hosts
```angular2
[docker]
192.168.3.32    ansible_ssh_user=root host_name=kubernetes-master

[kubenode]
192.168.3.33    ansible_ssh_user=root host_name=kubernetes-node1
192.168.3.34    ansible_ssh_user=root host_name=kubernetes-node2
192.168.3.35    ansible_ssh_user=root host_name=kubernetes-node3
```

其中 192.168.3.32为master节点 另外三台为node节点

进入k8s-roles，执行命令

### master节点安装

```angular2
ansible-playbook kube_master.yml
```

### node节点安装
```angular2
ansible-playbook kube_node.yml
```
