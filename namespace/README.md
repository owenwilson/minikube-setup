# kubernetes namespace

- In Kubernetes, namespaces provide a mechanism for isolating groups of resources within a single cluster. Names of resources need to be unique within a namespace, but not across namespaces. Namespace-based scoping is applicable only for namespaced objects (e.g. Deployments, Services, etc.) and not for cluster-wide objects (e.g. StorageClass, Nodes, PersistentVolumes, etc.).

## Namespace Naming Conventions

- Consistent Naming Strategy

Format: {team}-{application}-{environment}

Examples:

```text
frontend-web-production
backend-api-staging
data-pipeline-dev
ml-training-experiment-pr-456
```

## create namespace

- list all namespace

```sh
kubectl get namespace
```

- create a new namespace

```sh
kubectl create namespace
```

- specified namespace

```sh
kubectl get all -n kube-system
```

```sh
kubectl get all -n team-a-dev
```

### delete namespace

```sh
kubectl delete name-space
```

### namespace best practice

- best for: large organizations, multi-team environments, clear separation needed (recommended for most production environments)

#### namespace per team per environment (recommended)

```sh
# Team A
kubectl create namespace team-a-dev
kubectl create namespace team-a-staging
kubectl create namespace team-a-production
```

```sh
# Team B
kubectl create namespace team-b-dev
kubectl create namespace team-b-staging
kubectl create namespace team-b-production
```

Rules:

```text
Lowercase only (Kubernetes requirement)
Hyphens for separation (not underscores or periods)
Max 63 characters (DNS label limit)
Start and end with alphanumeric (not hyphen)
```

- Full isolation: Teams separated, environments separated

## refence kubernetes namespace

- check [the following documentation](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/)

- check [the following blog kubernetes](https://atmosly.com/blog/kubernetes-namespace-management-best-practices-2025)
