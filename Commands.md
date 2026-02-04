Commands that are using for K8s
________________________________________________________________________________________________
👉To list the nodes:
```
kubectl get nodes
```
👉To list the pods:
```
kubectl get pods
```
👉To list namespaces:
```
kubectl get namespace
```
👉To list pods in a kube-system namespace:
```
kubectl get -n kube-system pods
```
👉To run a Nginx image: (it will run in the default namespace because we didn't specify any name space)
```
kubectl run nginx --image=nginx:alpine
```
👉To show label of pods:
```
kubectl get pods -n <namespace> --show-labels
```
👉To know the IP of the pod:
```
kubectl get pods -n <namespace> -o wide
```
👉To access the container shell in a pod that has custom namespace: (for kubeadm enable the port tcp - 10250, in security group)
```
kubectl exec -it <podname> -n <namespace> -- sh
```
👉To delete a pod:
```
kubectl delete pod <pod_name>
```
👉To run a config file:
```
kubectl apply -f <filename.yml>
```
👉To delete the config file:
```
kubectl delete -f <filename.yml>
```
👉To access the logs:
```
kubectl logs <pod-name> <namespace>
```
👉To list the cron jobs in a namespace:
```
kubectl get cronjob -n <namespace>
```
👉To show the deployments status:
```
kubectl get deployments -n <namespace>
```
👉To Scale Up/Down pods:
```
kubectl scale deployment nginx-deployment --replicas=3
```
