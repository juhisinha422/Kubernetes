Kubernetes Architecture – Detailed Breakdown  with simple explanation

Kubernetes is a container orchestration platform that automates deployment, scaling, and management of containerized applications. It follows a master-worker architecture, now referred to as Control Plane and Nodes.

🧭 1. Control Plane (Brain of the Cluster)

The Control Plane manages the overall state of the cluster – scheduling, scaling, and monitoring.

🟦 kube-apiserver

Main entry point for all REST commands (from kubectl, UI, etc.).

Validates and processes API requests.

Talks to all other control plane components.

Acts as a gateway between users and Kubernetes.

🟩 Controller Manager

Runs multiple controllers (like ReplicationController, NodeController).

Reconciles the current state of the cluster with the desired state.

Example: If a pod dies, it ensures a new one is created.

🟧 Scheduler

Watches for new pods that don't have a node assigned.

Selects the best available node based on resource needs, affinity, taints, etc.

🟪 etcd

A highly available key-value store.
Stores all cluster data: nodes, pods, configs, secrets.

Acts as the source of truth for the cluster.

🖥️ 2. Nodes (Workers that Run Your Applications)

Each node hosts one or more Pods, and each pod runs one or more containers.

🟩 kubelet

Agent that runs on each node.

Ensures containers are running in pods.

Talks to the API Server for instructions.

Sends pod status back to the control plane.

🟦 kube-proxy

Manages network routing and traffic forwarding.

Handles internal cluster networking via iptables or IPVS.

Ensures each service gets a stable IP and DNS name.

📦 3. Pods and Containers

A Pod is the smallest deployable unit.

A pod contains one or more containers that share:

Network (same IP/port space)
Storage (volumes)

Containers inside pods communicate via localhost.

🖥️ 4. kubectl (CLI Tool)

CLI used by admins and developers to interact with the cluster.

Sends requests to the kube-apiserver.

Example:

kubectl get pods

kubectl apply -f deployment.yaml

🔄 Communication Flow

➡️ User sends request via kubectl → kube-apiserver

➡️ kube-apiserver stores config/state in etcd

➡️ Scheduler assigns pod to a node

➡️ Controller Manager ensures replication, health, etc.

➡️ kubelet on that node creates and runs the pod

➡️ kube-proxy ensures traffic reaches the pod


![Image](https://github.com/user-attachments/assets/9ae7e850-05ac-4966-903c-fe91e68d7ddb)
