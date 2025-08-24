Day 6 (Journey to CKA)

Today’s Topic: Kube-Proxy

Think of Kube-Proxy as the Traffic Controller 🚦 of Kubernetes.

It makes sure network requests find their way to the correct Pod or Service, no matter where it is running in the cluster. ✅

🔹 What does Kube-Proxy do?

Runs on every node in the cluster.
Manages network rules so that:

A Pod can talk to another Pod.

A Pod can talk to a Service.

External traffic can reach cluster services.

Handles load balancing for traffic between multiple pods of the same service.

🔹 How does it work?

1️⃣ When you create a Service, the API server updates iptables/IPVS rules on nodes via kube-proxy.

2️⃣ Incoming traffic to the Service is intercepted.

3️⃣ Kube-Proxy forwards it to one of the backend Pods.

📌 Example:

You expose your app as a Service (ClusterIP, NodePort, or LoadBalancer).

A client sends a request → kube-proxy routes it to one of the healthy pods behind that service. 

If one pod dies, kube-proxy automatically redirects traffic to the remaining pods.

🔹 Important to Note

Kube-Proxy doesn’t understand application-level protocols; it only deals with networking rules.
Modes of operation: iptables (default) or IPVS (faster, 
scalable).
👉 In short, Kube-Proxy = The Network Glue 🌐 of Kubernetes.
Without it, services cannot talk to each other, and external traffic won’t reach your apps.


![Image](https://github.com/user-attachments/assets/8473ea12-065e-4a51-aff1-409c0cc22649)
