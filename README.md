# kubernetes-for-beginners

## Install vagrant and virtualbox on win10

install vagrant
```
choco install vagrant -y 
```

install virtualbox
```
choco install vitualbox -y
```

### Deploy kubemaster 1 node and kubenode 2 nodes

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
