# Kubernetes

## Delete empty replicas set

Delete all empty replicas set in the current namespace.
```bash
kubectl delete rs $(kubectl get rs -o jsonpath='{.items[?(@.status.replicas==0)].metadata.name}')
```