## secrets

- A Secret is an object that contains a small amount of sensitive data such as a password, 
a token, or a key. Such information might otherwise be put in a Pod specification or 
in a container image. Using a Secret means that you don't need to include confidential data 
in your application code.

```sh
kubectl get secret -A
```

```sh
kubectl apply -f ./secret.yml
```

```sh
kubectl get secret -A
```

- export secret-word

```sh
kubectl get secret secret-word -o yaml
```

### base64 encode

- execute the following commands

```sh
echo "hello world" | base64
```

#### base64 decode

```sh
echo aGVsbG8gd29ybGQK | base64 -d
```

#### reference secret

- check the [following documentation](https://kubernetes.io/docs/concepts/configuration/secret/)
