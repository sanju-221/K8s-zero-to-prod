Deployments:

"Docker containers are deployed within Pods, which are managed and scaled by Deployments."

Refer: https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

Key Features:

Self-Healing: If a Pod crashes or a node fails, the Deployment notices the "actual state" doesn't match your "desired state" and automatically starts a new Pod.
Zero-Downtime Updates (Rolling Updates): When you update your app to a new version, the Deployment replaces old Pods with new ones one-by-one, ensuring your app stays online during the transition.
Rollbacks: If a new update has a bug, you can revert to a previous version with a single command.
Scaling: You can instantly scale your app from 2 replicas to 20 by changing one number in your configuration.

Manifest file eg: deplyment.yaml
if we have custom namespace, we have to mention it in the yml file - (metadata - namespace)
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80
```
Task - Command

Apply/Create:
```
kubectl apply -f deployment.yaml
```
Check Status:
```
kubectl get deployments
```
Scale Up/Down:
```
kubectl scale deployment nginx-deployment --replicas=5
```
Undo Update: 
```
kubectl rollout undo deployment nginx-deployment
```

<img width="2256" height="354" alt="deployment" src="https://github.com/user-attachments/assets/c6b04c2e-5f74-438a-a794-8036a8bdeb92" />

