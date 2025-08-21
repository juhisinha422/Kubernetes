Day 4 (Journey to CKA)

Today’s Topic: ETCD

A distributed, reliable, key-value store 👉 simple, secure, and fast.
It is the “source of truth” for Kubernetes. ✅

🔹 Role of etcd in Kubernetes

Stores the entire cluster state: nodes, pods, configs, secrets, roles, service accounts, CRDs and more.

Every kubectl get command fetches data from the etcd server.

Any cluster change (adding a node, deploying a pod, updating config) is persisted in etcd only after the operation is successful.

🔹 Why etcd is critical?

Without etcd, Kubernetes has no memory of what exists in the cluster.

It enables recovery after failures since the state is stored reliably.
Designed to be highly available (runs as a distributed system with leader election).

🔹 How etcd works (High-level)

1️⃣ Client requests (from kube-apiserver) update or read data.

2️⃣ Leader node in etcd cluster ensures strong consistency.

3️⃣ Data is replicated across etcd peers for reliability.

📌 Example:

Run kubectl get pods → kube-apiserver fetches info from etcd.
Deploy a new pod → Scheduler decides placement → Kubelet runs it → etcd updates the new state once pod is successfully running.

👉 In short, etcd = The Brain of Kubernetes 🧠.

If etcd is down, the cluster cannot function properly.

![Image](https://github.com/user-attachments/assets/a35b5def-0c2a-4417-ac55-53fe00722208)
