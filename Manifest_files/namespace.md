Manifest file for the namespace:

Refer: https://kubernetes.io/docs/tutorials/cluster-management/namespaces-walkthrough/

```
apiVersion: v1
kind: Namespace
metadata:
  name: nginx
  labels:
    name: nginx-namespace

```

To run:
```
kubectl apply -f <filename.yml>
```
