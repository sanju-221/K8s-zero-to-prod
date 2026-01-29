Commands that are using for K8s

To list the nodes:
```
kubectl get nodes
```
To list the pods:
```
kubectl get pods
```
To list namespaces
```
kubectl get namespace
```
To list pods in a kube-system namespace
```
kubectl get -n kube-system pods
```
To run a Nginx image (it will run in the default namespace because we didn't specify any name space)
```
kubectl run nginx --image=nginx:alpine
```
To delete a pod
```
kubectl delete pod <pod_name>
```
