- A StorageClass provides a way for administrators to describe the classes of storage they offer.
```sh
kubectl get storageclass
```

- Create first volume
```sh
kubectl get persistentvolumeclain
```
```sh
mkdir my-volume && cd my-volume
```
```sh
touch pvc.yml
```
```sh
kubectl apply -f pvc.yml
```
- check volumeclaim and volume
```sh
kubectl get persistentvolumeclain
kubectl get persistentvolume
```
- create a deploy example
```sh
kubectl apply -f deploy.yml
```
```sh
kubectl get pods
```
- run exec into nginx cluster
```sh
kubectl exec -it nginx-ID -- sh
# cd /etc/mi-volumen
# touch hi.txt
```
- we remove the pod to verify that the file still existed
```sh
kubectl delete pod nginx-ID
```
```sh
kubectl get pods
kubectl exec -it nginx-ID -- sh
# ls -ls /etc/mi-volumen
```

#### reference storage class

- check the following [documentation storage class](https://kubernetes.io/docs/concepts/storage/storage-classes/)
