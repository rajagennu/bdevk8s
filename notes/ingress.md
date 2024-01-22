# Ingress
- object to expose your services to outside world
- host multiple services on the same IP Address.
- host multiple servcices on same port. 
- Terminate SSL
- integrate directly with external DNS and load balancers.

- In production, once you have an ingress configured and have pointed your domain name to it (and perhaps its load balancer), you can access your application from anywhere in the world. 
- 


## enable ingress in minikube

```bash
minikube addons enable ingress
```

- Fear not! Minikube has a command that will forward the ingress to your local machine.

```
minikube tunnel -c
```

The tunnel should expose the ingress controller's load balancer to your local machine on 127.0.01:80, which we mapped to the synchat.internal and synchatapi.internal domains in the previous exercise.

- For minikube case, use `minikube ip` command, get the IP and add host entries to that IP in /etc/hosts for the one given in ingress object

For example, the Boot.dev Kubernetes cluster uses an ingress extension specific to Google Cloud Platform. We use the following annotations so that our controller knows which static IP address to use, which SSL certificate to use, and how to route traffic to our ingress:

```bash
  annotations:
    kubernetes.io/ingress.global-static-ip-name: static-ip-name-here
    networking.gke.io/managed-certificates: cert-name-here
    kubernetes.io/ingress.class: gce
```

In a nutshell, however, the important take-away is that in most production deployments you'll be using annotations specific to the cloud provider you're using. Each major cloud provider has their own products, so you need to use k8s annotations and extensions specific to that cloud provider.




