Day 08 
Today’s learning was all about ensuring high availability and self-healing in Kubernetes applications. 

1) Replication Controller (RC):
Ensures the desired number of Pods are always running.
Automatically replaces crashed Pods.
A legacy concept — now mostly replaced by ReplicaSets.

2) ReplicaSet (RS):
The modern version of Replication Controller.
Uses label selectors to identify and manage Pods.
Maintains the desired number of Pods across nodes for high availability.

3) Deployment:
A higher-level abstraction that manages ReplicaSets.
Enables rolling updates, rollbacks, and version control for Pods.
Simplifies scaling and ensures zero-downtime updates.

Flow:
Deployment -> ReplicaSet -> Pod -> Container

Read More: https://lnkd.in/d9YkNzCb

![Image](https://github.com/user-attachments/assets/7abf6d85-fac7-44ea-8874-f21c70a2c2a6)
