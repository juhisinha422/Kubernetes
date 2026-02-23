How Kubernetes Routes Traffic (Behind the Scenes)

Ever wondered how a Service always finds the right Pods, even when Pods are recreated?
That magic is called Endpoints 👇

🔹 Pod is created → kubelet starts the container

🔹 kube-api-server stores Pod state in etcd
🔹 Endpoint Controller links Service → Ready Pods

🔹 Endpoints object gets Pod IPs

🔹 kube-proxy programs network rules on every node

✨ Result:

Traffic → Service → Endpoints → Pods (zero downtime!)

🌍 This is pure open-source engineering at scale — small controllers, clean APIs, and eventual consistency working together.

💡 Why it matters for Ops & Contributors

Easy service discovery

Built-in load balancing

Pods can die, Services don’t

🛠️ Kubernetes shows how simple components + strong contracts = massive reliability

![Image](https://github.com/user-attachments/assets/1cf4fed1-dda1-4fdf-875d-d0bada12859a)
