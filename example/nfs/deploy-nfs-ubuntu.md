##  Install the NFS kernel Server package
```
sudo apt update
sudo apt install nfs-kernel-server
```

## Create an NFS directory share
```
sudo mkdir /srv/nfs/kubedata -p
sudo chown nobody:nogroup /srv/nfs/kubedata
```

## Allow NFS client access to NFS server

edit  /etc/exports file

```
sudo vi /etc/exports

```
