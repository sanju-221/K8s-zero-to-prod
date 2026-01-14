Kubernetes (K8s) – Introduction

Official documentation: https://kubernetes.io/docs/home/

What is Kubernetes?

Kubernetes, commonly known as K8s, is an open-source container orchestration platform originally developed by Google and now maintained by the Cloud Native Computing Foundation (CNCF). It helps us deploy, manage, scale, and operate containerized applications efficiently.

Why Kubernetes?

As applications grow, managing containers manually becomes complex. Kubernetes solves this by providing:

#Automated deployment and updates
#Auto-scaling of applications based on load
#Self-healing (restarts failed containers)
#Load balancing and service discovery
#High availability for applications

Key Kubernetes Concepts:

#Cluster: A set of machines (nodes) that run containerized applications
#Node: A worker machine in the cluster
#Pod: The smallest deployable unit in Kubernetes (one or more containers)
#Service: Exposes applications running in pods
#Deployment: Manages application updates and scaling
#Namespace: Logical separation of resources
#Where is Kubernetes Used?

Kubernetes is widely used for:

#Microservices architectures
#Cloud-native applications
#CI/CD pipelines
#High-traffic web applications
#Hybrid and multi-cloud deployments

Cluster Architecture

<img width="688" height="435" alt="K8s architecture" src="https://github.com/user-attachments/assets/5ac87796-a821-41b4-b8e0-4050a4d196e3" />

A Kubernetes cluster is made up of a control plane and a group of worker machines, called nodes, that host containerized workloads. At least one worker node is required for Pods to run. The Kubernetes architecture follows a clustered model where the control plane and worker nodes work together to constantly align the system’s desired state (what you define in YAML) with the actual state (what is currently running in the cluster).

Control plane = the “brain” that stores state and makes decisions

Worker nodes = the “muscles” that actually run containers (in Pods)

Everything communicates through the Kubernetes API and persists in etcd

