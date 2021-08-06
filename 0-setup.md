## Vmware / VirualBox

Download and install vmware fusion or VirtualBox, my host is windows platform, but it supportes many different platfors.

## three nodes(ubuntu) on host

|Role|IP|OS|RAM|CPU|
|----|----|----|----|----|
|master|192.168.186.130|Ubuntu 20.04.2|2G|2|
|worker1|192.168.186.131|Ubuntu 20.04.2|8G|2|
|worker1|192.168.186.132|Ubuntu 20.04.2|8G|2|

## on all nodes

#### disable firewall
```
sudo ufw disable
```
#### disable swap
```
sudo swapoff -a; 
sudo sed -i '/swap/d' /etc/fstab
```
#### config ssh access
```
sudo apt install openssl-server
```

## Networking
I will use static networks in this guide:


* node network(virtual networks):               192.168.186.0/24 
* Service Network:                              10.32.0.0/24 
* Cluster CIDR:                                  10.200.0.0/16 
* Pod CIDR on worker1:                           10.200.0.0/24
* Pod CIDR on worker2:                           10.200.1.0/24




