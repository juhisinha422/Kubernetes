core architecture of Kubernetes (K8s) 

Key Highlights:
1. Control Plane Components(Master Node):
API Server: The communication hub of the cluster.
Scheduler: Decides where pods should run.
Controller Manager: Ensures workloads stay healthy and running.
etcd: Stores cluster data and state.

2. Worker Node Components:
Kubelet: Executes instructions from the control plane.
Kube-Proxy: Manages pod-to-pod networking.
Pods: The smallest deployable unit in Kubernetes.
End-to-End Flow:

A user interacts via kubectl -> API Server ->  etcd -> Scheduler -> Kubelet →-> Pods

This ensures that workloads are automatically scheduled, monitored, and self-healing.

Takeaway:
Kubernetes acts as the brain of container orchestration, providing scalability, reliability, and automation — making it the backbone of modern DevOps workflows.

Read More: https://github.com/juhisinha422/Kubernetes/tree/main/Notes/CKA/Piyush%20Notes/Kubernetes_DevOps/Day-05


![Image](https://github.com/user-attachments/assets/3a74d6c8-12bf-4206-9480-6f155f57f296)
