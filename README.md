# argo-workflow-demo

```
minikube start
```

### installation - minio
```
kubectl apply -f minio-standalone.yaml
```

### installation - argo
```
kubectl create ns argo
helm repo add argo https://argoproj.github.io/argo-helm
helm install -n argo demo argo/argo-workflows
```

### remove gui authentication
```
'--auth-mode=server'
```

### port forward
```
kubectl -n argo port-forward service/demo-argo-workflows-server 2746:2746
```

### resources
```
kubectl apply -f minio-secret.yaml
kubectl apply -f role.yaml
kubectl apply -f binding.yaml
kubectl apply -f artifact-cm.yaml
kubectl apply -f dag-template.yaml
```
