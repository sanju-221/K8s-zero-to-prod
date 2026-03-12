NameSpace

What is Name-space?

A way to organize and isolate resources inside the same kubernetes cluster.

To create a namespace:
```
kubectl create namespace <give a name to the ns>
```
To list the namespace:
```
kubectl get namespaces
```
To run a pod in a namespace (eg: nginx)
```
kubectl run nginx --image=nginx:alpine -n <namespace name>
```

Manifest file for the namespace:

Refer: https://kubernetes.io/docs/tutorials/cluster-management/namespaces-walkthrough/

```
apiVersion: v1
kind: Namespace
metadata:
  name: nginx-ns
  labels:
    name: nginx-namespace

```

To run:
```
kubectl apply -f <filename.yml>
```
<img width="836" height="238" alt="namespace" src="https://github.com/user-attachments/assets/c1e60f78-de57-4669-97ed-df5c2cabc5d5" />
