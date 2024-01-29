# Resource Requests

- A resource request is the amount of a resource that a pod requests from the node its running on. This is different from a resource limit.
- Resource limit: maximum amount of a resource that a pod is allowed to consume before its throttled or killed. 

- by creating resource requests, pods are telling to k8s cluster that it need this much resources to be available to run the pod, by this way we are allowing to pods to exit gracefully if requested resources are not existed. 

Generally speaking, my rule of thumb is:

    Set memory requests ~10% higher than the average memory usage of your pods
    Set CPU requests to 50% of the average CPU usage of your pods
    Set memory limits ~100% higher than the average memory usage of your pods
    Set CPU limits ~100% higher than the average CPU usage of your pods


These are just rules of thumb! At the end of the day, you always need to understand how your applications work, and what resources they need. The right numbers for your applications might be drastically different than the numbers I've suggested here.
