Day 5/60: Kubernetes Architecture 🏗️

Today was all about looking "under the hood" of the K8s cluster. Understanding how the Control Plane and Worker Nodes communicate is a total game-changer for troubleshooting and system design.

Key takeaways from today’s deep dive:

The Control Plane (The Brain): Learned why the API Server is the heart of everything and how etcd acts as the cluster's "single source of truth," storing every detail of the cluster state.

The Scheduler: It’s not just magic—it’s a logic engine that picks the best node for a pod based on resource availability like CPU and memory.

Controller Manager: The ultimate watchdog that ensures the "actual state" of the cluster always matches my "desired state."

Kubelet & Kube-Proxy: The "boots on the ground" on every worker node that make sure containers stay running and networking stays connected.

The Pod: I finally understood why we don't just run containers solo; the Pod acts as the smallest Deployable unit, providing a shared environment for our containers.

<img width="758" height="455" alt="Image" src="https://github.com/user-attachments/assets/0cd984ae-069e-4245-9867-457d29f1e292" />
