## Dynamically provision NFS persistent volumes in k8s

###  Install NFS server

nfs/deploy-nfs-ubuntu.md

### Deploy nfs-client-provision in k83

nfs/nfs-client-provisioning/

### Test
#### create pvc
```
kubectl apply -f create-pvc-nfs.yaml
```

#### create test bubybox
```
kubectl apply -f test-pvc-busybox.yaml
```
