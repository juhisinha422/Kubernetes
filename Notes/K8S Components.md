Kubernetes Components Simplified ⚡

🔹 1. Container – Runs your app + dependencies in an isolated environment. (Ex: Docker nginx)

🔹 2. Pod – Smallest deployable unit in K8s, can have multiple containers sharing network/storage. (Ex: nginx + sidecar)

🔹 3. Node – Physical/VM machine hosting Pods. Includes Kubelet, Kube-proxy, and a    container runtime. (Ex: AWS EC2)

🔹 4. Service – Provides a stable way to access Pods even if IPs change. (Types: ClusterIP, NodePort, LoadBalancer)

🔹 5. Cluster – A group of Nodes (workers + control plane) running workloads & services. (Ex: 3 master + 10 worker nodes)

🔹 6. Control Plane – The brain of Kubernetes managing the cluster’s state. Components:

·       API Server

·       Scheduler

·       Controller Manager.

·       etcd

🔹 7. Package – Bundled Kubernetes resources for deployment. (Ex: Helm Chart, Kustomize)

💡 Flow: Container → Pod → Node → Cluster → Managed by Control Plane → Accessed via Service


![Image](https://github.com/user-attachments/assets/a6574d32-76d3-46cc-aa6d-8fe88fd4815f)
