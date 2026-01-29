Manifest file for pod creation

Refer: https://kubernetes.io/docs/concepts/workloads/pods/

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80
```
To run:

```
kubectl apply -f <filename.yml>
```
To verify: 
```
kubectl get pods -o wide
```
