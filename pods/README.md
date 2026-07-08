# kubernetes pod

- Pods are the smallest deployable units of computing that you can create and manage in Kubernetes.

## create pod

```sh
kubectl create deployment --image nginx
```

```sh
kubectl create deployment --image nginx app 
```

```sh
kubectl create deployment --imagen nginx aplicacion
```

- check pods

```sh
kubectl get pods
```

- output format with more information (such as node name)

```sh
kubectl get pod -o wide
```

- output format with more information (json)

```sh
kubectl get pod -o json
```

- output format with more information (yaml)

```sh
kubectl get pod -o yaml
```

Example get specied pod

```sh
kubectl get pod app-86869cd8d8-7fg59 -o yaml
```

- export configuration to yaml file

```sh
kubectl get pod app-86869cd8d8-7fg59 -o yaml > pod.yml
```

## exec

```sh
kubectl exec app2 -- ls
```

- interactive

```sh
kubectl exec -it app2 -- sh
```

## debug

- describe pod

```sh
kubectl describe pod app2
```

- logs pod

```sh
kubectl logs app2
```

## reference kubernetes pod

- check [the following documentation](https://kubernetes.io/docs/concepts/workloads/pods/)
