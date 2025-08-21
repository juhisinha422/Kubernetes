Day 2 (Journey to CKA)

Today’s Topic: Kube-Controller Manager

If the API Server is the control tower of Kubernetes, then the Controller Manager is like the autopilot system.

It continuously monitors the cluster’s state and takes action to bring it back to the desired state whenever something drifts.

🔹 What is a Controller?

A controller is simply a process that keeps watching the status of different cluster components and remediates situations automatically.

💡 Examples of Key Controllers:

1️⃣ Node Controller

Checks the heartbeat of nodes every 5 seconds

If no heartbeat, waits 40s → marks node as unreachable

If the issue continues for 5 minutes, it will evict pods and reschedule them on healthy nodes.

2️⃣ Replication Controller

Ensures the desired number of pods are always running in the cluster
If one pod dies, it spins up another to maintain the defined replica count.

🔧 There are many other controllers in Kubernetes such as:

Deployment Controller

Namespace Controller

PersistentVolume Protection

Controller

ServiceAccount Controller
…and more!

👉 In short, the Kube-Controller Manager = Kubernetes self-healing engine 💪

![Image](https://github.com/user-attachments/assets/ca162347-f5e6-4490-a050-1409bfb52ac3)
