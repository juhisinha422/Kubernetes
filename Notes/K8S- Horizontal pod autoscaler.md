Kubernetes Horizontal Pod Autoscaler — explained simply:

1. When your app gets more traffic, a single pod may not be enough- CPU spikes, response times slow down, and users start feeling it.

2. The Horizontal Pod Autoscaler (HPA) keeps watching pod metrics like CPU, memory, or custom app metrics (via Prometheus, KEDA, etc.).

3. When the load goes up, HPA automatically creates more pods to share the traffic.

4. When the load drops, HPA scales the pods back down so you don’t pay for unused capacity.

5. Instead of making 1 pod bigger, HPA adds more copies of the same pod to handle the workload.

👉 HPA = scale out (more pods)

👉 VPA = scale up (stronger pod)

<img width="800" height="413" alt="Image" src="https://github.com/user-attachments/assets/95266fbe-7190-4e5f-8698-a32461e086a7" />
