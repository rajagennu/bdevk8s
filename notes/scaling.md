# Scaling
- we need to know about how pods are consuming the resources.

```bash
minikube addons enable metrics-server
```

- wait for a while, for metric pod to get deployed

```bash
kubectl get pods -n kube-system
```

## check load

```bash
kubectl top pod
``` 


