# kubernetes-for-beginners

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

### Deploy kubemaster 1 node and kubenode 2 nodes

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
If Win10 can't ssh to all node in vagrant
https://github.com/hashicorp/vagrant/issues/9950

```
$env:VAGRANT_PREFER_SYSTEM_BIN="0"
```

### stop and detroy lab environment

```
vagrant halt
vagrant destroy
```
