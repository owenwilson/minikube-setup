# Minikube

## minimal requirements

> 2 CPUs or more
> 
> 2GB of free memory
>
> 20GB of free disk space
> 
> Internet connection
> 
> Container or virtual machine manager, such as: Docker, QEMU, Hyperkit, Hyper-V, KVM, Parallels, Podman, VirtualBox, or VMware Fusion/Workstation

## install Minikube

- To install the latest minikube state release on x86-64 linux

```sh
curl -LO https://github.com/kubernetes/minikube/releases/latest/download/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64
```

- check the [minikube documentation for installation](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download)

## start service

- Example start minikube 
- Start a cluster using the docker driver:
```sh
minikube start --driver=docker
```

- To make docker the default driver
```sh
minikube config set driver docker
```

- check [driver docker documentation](https://minikube.sigs.k8s.io/docs/drivers/docker/)

## configure alias

- please edit bashrc file

```sh
alias kubectl="minikube kubectl --"
```

```sh
source ~/.bashrc
```

- test command kubernetes

```sh
kubectl get all
```

## kubernetes commands
- help commands
```sh
kubectl create --help
```
- create a pod using the deployment command in kubernetes
```sh
kubectl create deployment --image nginx app
```
```sh
kubectl create deployment --image nginx application
```
- output information kubernetes
```sh
kubectl get pods -o wide
```
```sh
kubectl get pods -o json
```
```sh
kubectl get pods -o yaml
```
- delete pod
```sh
kubectl describe pod app-6b97cd8cbd-6kpc9 | grep -E "Controlled By"
output
Controlled By:  ReplicaSet/app-6b97cd8cbd
```
- if it is a deployment
```sh
kubectl scale deployment app --replicas=0
```
- if it is a ReplicaSet
```sh
kubectl scale replicaset app --replicas=0
```
- if it is a StateFullSet
```sh
kubectl scale statefulset app --replicas=0
```

- recommended option
```sh
kubectl scale deployment app --replicas=0
```
```sh
kubectl delete deployment app
```
- check if exists pod deleted
```sh
kubectl get pods -o wide
```

## debbug

```sh
kubectl describe pod aplication2
```

```sh
kubectl logs aplication2
```

```sh
kubectl exec -it aplication2 -- bash
```

## reference documentation

- check [the following blog about mikube basic steps](https://medium.com/@ravipatel.it/getting-started-with-minikube-a-beginners-guide-924fc1c9bb7d)
- check [the first cluster kubernetes with minikube](https://medium.com/@ravipatel.it/getting-started-with-minikube-a-beginners-guide-924fc1c9bb7d)
- check [the install minikube and first pod](https://medium.com/@ravipatel.it/getting-started-with-minikube-a-beginners-guide-924fc1c9bb7d)
