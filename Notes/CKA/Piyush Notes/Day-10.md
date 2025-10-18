#Day-10

Today’s focus: Kubernetes Namespaces — the backbone of resource organization and isolation within your cluster.

1️⃣ default – The catch-all space where your resources go when you don’t specify a namespace.
 2️⃣ kube-system – The cluster’s control center, hosting critical components like etcd, kube-apiserver, and coredns.
 3️⃣ kube-public – A shared, readable space for resources meant to be visible across the cluster.
 4️⃣ kube-node-lease – Handles node heartbeat data to help detect node health efficiently.

 DNS Insight:
 Namespaces power in-cluster DNS.
 To reach a Service across namespaces, use its FQDN format:
 <service-name>.<namespace>.svc.cluster.local

This keeps communication scoped correctly and avoids naming collisions — essential for multi-environment clusters (Dev, Staging, Prod).

key Takeway:
✅ Use FQDN for cross-namespace Service communication.
✅ Inside any Pod, you can view DNS settings via:  cat /etc/resolv.conf

<img width="800" height="353" alt="Image" src="https://github.com/user-attachments/assets/7aa0f528-a298-4ca1-94dd-53ea755ac426" />
