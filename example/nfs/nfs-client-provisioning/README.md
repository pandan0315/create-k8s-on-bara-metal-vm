## kubernetes NFS-CLient provisioner

nfs-client is an automatic provisioner that use your existing and already configured NFS server to support dynamic provisioning of Kubernetes Persistent Volumes via Persistent Volume Claims. Persistent volumes are provisioned as ${namespace}-${pvcName}-${pvName}.

From https://github.com/kubernetes-retired/external-storage/tree/master/nfs-client
