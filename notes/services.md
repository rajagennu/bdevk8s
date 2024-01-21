after creating the pods, we need to distribute the real traffic across those pods. 

servics provide a stable endpoint for pods, they are abstraction used to provide a stable end point and load balance traffic across a group of pods. 

stable endpoint: the service will always be available at given URL even a pod is destroyed or crecreated.


# definiing ports for service . 

```yaml
spec:
  selector:
    app: synergychat-web 
  ports:
  - protocol: TCP
    port: 80
    targetPort: 8080
```

# port-forward in service 

```bash
kubectl port-forward service/web-service 8080:80
```
# service types
- ClusterIP
  - default
  - up address the servie is bound to on internal k9s network
  - suitable for internal cluster 
- NodePort
  - exposes the service on each nodes ip at a static port.
  - NodePort service is just a ClusterIP service with addedfunctionality of exposing the service on each node's IP at a static port. 
  - for external networks 
- LoadBalancer:
  - exernal load balancer is the ucrrent cloud environment and assigns a fixed, external IP to the service. ( only cloud)
  - NodePort with added functioanlity of creating load balancer in the current cloud env. 

- ExternalName: 
  - maps the servie to externalName field. mapping configures your cluster's DNS server to return a CNAME record with that exernal hostname value. 
