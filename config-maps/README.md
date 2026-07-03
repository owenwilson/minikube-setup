- A ConfigMap is an API object used to store non-confidential data in key-value pairs.
Pods can consume ConfigMaps as environment variables, command-line arguments,
or as configuration files in a volume.
```sh
kubectl get configmap -A
```
```sh
kubectl apply -f ./config-maps/configmap.yml
```
- check configmap
```sh
kubectl get configmap
```
- export configmap registered
```sh
kubectl get configmap my-custom-configmap -o yaml > ./config-maps/output-configmap-registered.yml
```
#### reference config maps
- check the following [documentation config maps](https://kubernetes.io/docs/concepts/configuration/configmap/)
