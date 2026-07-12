# FluxCD

To apply now what is present on the Git repo over the actual cluster for the `flux-system` kustomization that should owns all other kustomization:

```bash
flux reconcile kustomization flux-system -n flux-system
```

To get the status of FluxCD

```bash
flux get kustomizations -n flux-system
```

To have more details about FluxCD

```bash
kubectl describe kustomization apps -n flux-system
```

Print logs

```bash
flux logs --info --namespace=flux-system --controller=kustomize-controller
```
