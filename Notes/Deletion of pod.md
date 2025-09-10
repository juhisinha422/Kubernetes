How a Pod is deleted in Kubernetes (behind the scenes).

🔎 Step-by-Step: What Happens When a Pod is Deleted in Kubernetes

1. User Deletes Pod

	•	Command executed:

kubectl delete pod <pod-name>

	•	This sends a delete request to the Kubernetes API Server.

⸻

2. API Server Updates ETCD

	•	The API Server writes the pod’s deletionTimestamp and deletionGracePeriodSeconds into etcd.

	•	Pod’s status becomes Terminating.

⸻

3. Endpoint Controller Removes Pod from Endpoints

	•	The Endpoint Controller updates the Endpoints object (removes the pod’s IP).

	•	This change propagates to:

	•	Kube-Proxy

	•	iptables

	•	Ingress

	•	CoreDNS

	•	This ensures no new traffic is sent to the terminating pod.

⸻

4. Kubelet Gets Notified

	•	The API Server notifies the kubelet running on the node where the pod is scheduled.

	•	Kubelet initiates pod termination.

⸻

5. PreStop Hook (Optional)

	•	If a PreStop Hook is defined, kubelet executes it.

	•	Example: Closing database connections, draining requests, etc.
	
•	Default timeout: 10 seconds.

⸻

6. SIGTERM Signal

	•	After PreStop hook (or immediately if not defined), kubelet sends a SIGTERM signal to the pod’s main container process.

	•	This gives the application a chance to gracefully shut down.

⸻

7. Grace Period

	•	Pod has up to terminationGracePeriodSeconds (default 30s) to shut down gracefully.

	•	During this period:

	•	App should stop serving requests

	•	Clean up resources (e.g., flush logs, close connections)

⸻

8. SIGKILL (Forced Termination)

	•	If pod does not exit after the grace period, kubelet sends SIGKILL to forcefully terminate the container.

⸻

9. Pod Deleted

	•	Kubelet notifies API Server that the pod has been terminated.

	•	API Server removes pod entry from etcd.

	•	Pod state becomes Deleted.

⸻

⚡ Timeline Example (Based on Image)
	•	PreStop Hook timeout: 10s
	•	Graceful shutdown after SIGTERM: 10s

	•	Total max time before SIGKILL: ~20s (if app doesn’t exit itself).

⸻

✅ In summary:

kubectl delete pod → API Server → ETCD → Endpoint Controller → Remove from service/endpoints → Kubelet notified → PreStop Hook → SIGTERM → Graceful Shutdown → SIGKILL (if needed) → Pod Deleted.


![Image](https://github.com/user-attachments/assets/d39a7036-6eb5-4160-b193-a36180fa4f93)
