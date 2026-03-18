# Kubernetes

## Delete empty replicas set

Delete all empty replicas set in the current namespace.

```bash
kubectl delete rs $(kubectl get rs -o jsonpath='{.items[?(@.status.replicas==0)].metadata.name}')
```

## Test a deployed app on local

When your app is deployed on Kubernetes thanks to a `deployment` and a `service` and you want to test it without expose it to Internet, you can use this:

Perform Kubernetes port forwarding:

```bash
kubectl port-forward svc/personal-website-v2 2040:80 -n personal-website-v2
```

Where:

- `80`: is the `svc/personal-website-v2` port
- `2040`: is the port of the remote host (only accessible in localhost)

To access form your browser in your computer on a remote machine:

```bash
ssh ovh-vps -NL 7070:localhost:8080
```

Where:

- `ovh-vps`: is the preconfigured ssh host where the Kubernetes app run
- `-N`: "No command", ssh won't open a TTY on the remote host
- `-L`: "Local port forwarding", to perform port forwarding
- `7070`: is the local port on your machine
- `8080`: is the port of the remote host that we open previously (only accessible in localhost so we tunneled it thanks to ssh)

With this solution, no port will be open the Kubernetes server.
