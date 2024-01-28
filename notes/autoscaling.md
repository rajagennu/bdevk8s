# Autoscaling 

```yaml
apiVersion: autoscaling/v1
kind: HorizontalPodAutoscaler
metadata:
  name: testcpu-hpa
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: x
  minReplicas: x
  maxReplicas: x
  targetCPUUtilizationPercentage: x

```


