How to create a custom namespace & pod

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  namespace: my-app-ns
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
kubectl get pod -n <pod_name>
```

To delete:
```
kubectl delete -f <filename.yml>
```
