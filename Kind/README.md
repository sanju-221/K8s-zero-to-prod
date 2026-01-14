KIND - Kubernetes IN Docker
## Install kind on linux:

Official documentation: https://kind.sigs.k8s.io/docs/user/quick-start/

We have to install kind, and install kubectl for communication
Here I'am using shell scripting
Create a file (eg: kind.sh), paste the below commands
give execute permissions (chmod 764 kind.sh)
then ./kind.sh


```

#!/bin/bash

[ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.26.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv ./kubectl /usr/local/bin/kubectl

echo "kind & kubectl Successfully Installed!"

```
After this we can verify the versions of kind and kubectl

As the name indicates, we have to install docker 

```
sudo apt-get install docker.io
```
Then we need to configure yaml file for the cluster creation

## Multi-node clusters

You can also have a cluster with multiple control-plane & worker nodes, create a config file.

Refer: https://kind.sigs.k8s.io/docs/user/quick-start/

```
vi config.yaml
```
```

kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
  image: kindest/node:v1.32.1
- role: worker
  image: kindest/node:v1.32.1
- role: worker
  image: kindest/node:v1.32.1
- role: worker
  image: kindest/node:v1.32.1
  extraPortMappings:
  - containerPort: 80
    hostPort: 80
    protocol: tcp

```


