Relicaset follows the rule assign to it

To create a replicaset:
```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: nginx-replica
  namespace: nginx-ns
  labels:
    app: nginx
spec:
  # modify replicas according to your case
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
      - name: my-nginx
        image: nginx:alpine
        ports:
        - containerPort: 80

```
