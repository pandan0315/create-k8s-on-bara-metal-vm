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
```
kubectl get pv,pvc
```
>output
```
NAME                                                        CAPACITY   ACCESS MODES   RECLAIM POLICY   STATUS   CLAIM          STORAGECLASS          REASON   AGE
persistentvolume/pvc-f42a8720-52d8-4d64-8687-323f9560a2cb   500Mi      RWX            Delete           Bound    default/pvc1   managed-nfs-storage            45s

NAME                         STATUS   VOLUME                                     CAPACITY   ACCESS MODES   STORAGECLASS          AGE
persistentvolumeclaim/pvc1   Bound    pvc-f42a8720-52d8-4d64-8687-323f9560a2cb   500Mi      RWX            managed-nfs-storage   45s
```
#### check NFS server shared folder
```
lb@ubuntu:~$ ls /srv/nfs/kubedata/
default-pvc1-pvc-f42a8720-52d8-4d64-8687-323f9560a2cb
```


#### create test bubybox
```
kubectl apply -f test-pvc-busybox.yaml
```
create a "test" file under /mydata in busybox pod


```
 kubectl exec -it busybox -- sh
/ # ls /mydata/
/ # cd /mydata/
/mydata # ls
/mydata # touch test
/mydata # ls
test
```
lb@ubuntu:/srv/nfs/kubedata/default-pvc1-pvc-f42a8720-52d8-4d64-8687-323f9560a2cb$ ls
```
>output
```
test

```
