pods

The smallest deployable unit in Kubernetes. It provides the IP and storage for the container.

How Pods get their IPs

The IP is assigned by the CNI (Container Network Interface) plugin (like Calico, Flannel, or Cilium).
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
Use the command to list the pods and their IP address:
```
kubectl get pods -o wide
```
<img width="1250" height="110" alt="pod" src="https://github.com/user-attachments/assets/56c8dc28-4f2d-42aa-ae7d-6e2c0a770e90" />

