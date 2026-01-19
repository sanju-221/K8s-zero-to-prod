Install Minikube on Linux

Refer: https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download

```
curl -LO https://github.com/kubernetes/minikube/releases/latest/download/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64
```


```
minikube start
```
or 
```
minikube start --driver=docker --vm=true
```

👏We have configured our minikube!
<img width="2124" height="920" alt="Minikube" src="https://github.com/user-attachments/assets/a8898b6d-f482-4a52-bc79-98da29e51e04" />

