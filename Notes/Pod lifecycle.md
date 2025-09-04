Lifecycle of a Kubernetes #Pod to explain how it actually works.

A Pod might look simple, but behind the scenes it goes through multiple stages:

✅ Pod Manifest submitted to API Server

✅ Scheduler selects the right Node

✅ Kubelet creates the Pod Sandbox (runtime, volumes, networking, IP allocation)

✅ Pod Stages → Pending ➝ Running ➝ Succeeded/Failed

✅ Termination → Cleanup of containers, volumes & network

This diagram perfectly summarizes the complete journey of a Pod in Kubernetes.

 -Understanding this flow helps in debugging issues like Pending Pods, CrashLoopBackOff, or Termination delays.

![Image](https://github.com/user-attachments/assets/949eb51b-27e1-4163-b956-eb66789ab832)
