Services in Kubernetes

Pods in Kubernetes have short lifespans; scaling or self-healing events cause them to restart with new IP addresses, making direct IP-based access unreliable.

Refer: https://kubernetes.io/docs/concepts/services-networking/service/

Kubernetes Pods are transient: their lifecycle ends upon scaling, crashes, or node failures, resulting in new instances with different IP addresses. Hardcoding Pod IPs in applications leads to connectivity failures and downtime.

Role of Services
Services resolve this by acting as a stable network endpoint above Deployments. Key mechanisms include:

Label Selectors: Automatically discover and track Pods matching labels (e.g., app: myapp).

Virtual IP (ClusterIP): Provides a persistent IP and DNS entry (e.g., myapp.default.svc.cluster.local).

Load Balancing: Distributes traffic across healthy Pods transparently.

This decouples clients from Pod volatility, maintaining high availability.

