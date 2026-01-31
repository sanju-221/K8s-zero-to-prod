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
