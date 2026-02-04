In Kubernetes clusters, DaemonSets ensure one pod runs on every worker node (or selected nodes), making them perfect for per-node services like monitoring agents,
unlike regular Deployments that let the scheduler shuffle pods dynamically across nodes.

Refer: https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/

Why DaemonSets Fit Monitoring Apps

The master (control plane) uses the scheduler to place pods on worker nodes based on resource availability, node selectors, taints/tolerations, and affinity rules—leading to pods moving between nodes during scaling, failures, or drains.
DaemonSets override this by automatically deploying and maintaining exactly one pod replica per matching node, ensuring consistent coverage for node-level tasks.

```
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: ngin-daemon
  namespace: nginx-ns
  labels:
    app: nginx
spec:
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      -  name: my-nginx
         image: nginx:alpine
         ports:
         - containerPort: 80
```
```
kubectl apply -f daemon.yml
```
<img width="2020" height="214" alt="daemon-1" src="https://github.com/user-attachments/assets/2e719f38-643c-4a07-b307-b931e29ae609" />

<img width="1164" height="180" alt="worker" src="https://github.com/user-attachments/assets/d8dde56e-21ee-4862-b80f-87ab5f1e0394" />

Two worker nodes are running, we didn't specify the replicas in the yml file - the daemonset will install the pods on each worker node.

<img width="2334" height="158" alt="nodes" src="https://github.com/user-attachments/assets/6848c48e-fc97-4391-90bf-4fce9621e943" />

