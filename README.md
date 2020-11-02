# kubernetes-for-beginners
จะเป็นการเรียนรู้เกี่ยวกับเรื่อง Kubernetes เบื้องต้น เหมาะสำหรับคนที่กำลังเริ่มต้นศึกษา

## Prepare/Install vagrant and virtualbox on win10

install vagrant
```
choco install vagrant -y 
```

install virtualbox
```
choco install vitualbox -y
```
## Prepare/Install vagrant and virtualbox on MacOS

install vagrant
```
brew cask install vagrant 
```

install virtualbox
```
brew cask install vitualbox
```

## Deploy kubemaster 1 node and kubenode 2 nodes

### Clone git to machine
```
git clone https://github.com/supachai-j/kubernetes-for-beginners.git
cd kubernetes-for-beginners
```

### Check status and start VM with vagrant
```
vagrant status
vagrant up
```

### SSH to each node

```
vagrant ssh kubemaster
vagrant ssh kubenode01
vagrant ssh kubenode02
```
If Win10 can't ssh to all node in vagrant, How to fixed like below.
https://github.com/hashicorp/vagrant/issues/9950

```
$env:VAGRANT_PREFER_SYSTEM_BIN="0"
```

### stop and detroy lab environment

```
vagrant halt
vagrant destroy
```

## Next Step Learning guide
- [How To Install K8S all-in-one with minikube](docs/how-to-install-k8s-with-minikube.md)
- [How To Install K8S Cluster with Kubeadm](docs/how-to-install-k8s-with-kubeadm.md)
