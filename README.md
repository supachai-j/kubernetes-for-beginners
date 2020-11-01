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
set VAGRANT_PREFER_SYSTEM_BIN=0
vagrant ssh kubemaster
vagrant ssh kubenode01
vagrant ssh kubenode02
```

### stop and detroy lab environment

```
vagrant halt
vagrant destroy
```
