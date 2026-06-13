# FluxCD

To apply now what is present on the Git repo over the actual cluster

```bash
flux reconcile kustomization apps -n flux-system
```

To get the status of FluxCD

```bash
flux get kustomizations apps -n flux-system
```

To have more details about FluxCD

```bash
kubectl describe kustomization apps -n flux-system
```

Print logs

```bash
flux logs --info --namespace=flux-system --controller=kustomize-controller
```
