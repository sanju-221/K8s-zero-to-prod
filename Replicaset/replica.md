Relicaset follows the rule assign to it, we can't scale the pods

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

<img width="1310" height="390" alt="replica" src="https://github.com/user-attachments/assets/c954170b-1e4c-4c81-ad31-49391398ad10" />


