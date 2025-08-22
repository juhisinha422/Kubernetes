 Day 5 (Journey to CKA)

Today’s Topic: Kubelet

Think of Kubelet as the Captain of a Ship 🚢.

It doesn’t make decisions about where to sail (that’s the scheduler’s job), but it executes the orders and ensures everything inside the ship (node) is running smoothly. ✅

🔹 What does Kubelet do?

- Registers the node with the Kubernetes cluster.

- Creates Pods: When instructed by the scheduler, kubelet talks to the container runtime (Docker, containerd, CRI-O, etc.) and requests to pull the required images and sart the containers inside the pod.

- Monitors pods & nodes: Continuously checks if containers are running as expected.

- Reports status back to the kube-apiserver → which updates etcd.

🔹 Important Points about Kubelet

It only cares about PodSpecs provided by the API server. If you manually run a container on a node, kubelet won’t manage it.

It enforces the desired state → If a container crashes, kubelet restarts it automatically.

Kubelet also handles liveness/readiness probes to keep services healthy.

📌 Example Flow:

1️⃣ Scheduler decides PodX should run on Node1.

2️⃣ Kubelet on Node1 receives the instruction.

3️⃣ Kubelet asks container runtime → “Pull image + start container.”

4️⃣ Kubelet monitors the pod & sends regular health updates back to the API server.

👉 In short, Kubelet = The Executor ⚡ + Reporter 📡 of Kubernetes.

Without kubelet, nodes are just empty ships with no captain.

<img width="800" height="481" alt="Image" src="https://github.com/user-attachments/assets/2cc28684-0d2e-4a72-b8fb-9a3f5118eac1" />
