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
To access the container shell in a pod that has custom namespace (for kubeadm we have to add the port tcp - 10250, in security group)
```
kubectl exec -it nginx-pod -n my-app-ns --sh
```
We have installed nginx, but it can't be access the nginx home page from our web browser. (For that we have to set up service) We can see the nginx home page,
```
curl 127.0.0.1
```
