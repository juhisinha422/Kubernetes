exciting step into the world of Kubernetes (K8s) — by setting it up locally using Kind (Kubernetes in Docker).

Before moving to managed services like GKE, AKS, or EKS, I wanted to understand how Kubernetes actually runs under the hood  and Kind makes that possible locally!

Kubernetes can be installed in many ways — minikube, k3s, k3d, or kind.
 But Kind (Kubernetes in Docker) is lightweight, fast, and perfect for learning or testing.

A) Single-node Cluster (space9)
 → Only one node acts as both control plane and worker.
 → All components (API Server, Scheduler, Controller Manager, etcd, Kubelet, and Kube-proxy) run inside a single Docker container.

B) Multi-node Cluster (space9-v2)
 → One master (control-plane) node and two worker nodes.
 → Each node runs inside a separate Docker container.
 → Control plane handles cluster management; workers handle workloads (Pods).

This setup helped me visualize how real-world Kubernetes clusters are structured and how kubectl communicates with the API server to manage nodes and pods.

Takeaway:
Understanding Kubernetes starts with building it — even if it’s on your local machine.
By spinning up clusters locally, I learned how the control plane, worker nodes, and API server actually coordinate inside containers.


![Image](https://github.com/user-attachments/assets/de03c8ee-0b39-4efd-a468-386dc9e7b63b)

Read More: https://lnkd.in/dVFnZjV5
