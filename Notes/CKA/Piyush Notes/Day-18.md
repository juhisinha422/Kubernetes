#Day18 

Today I explored Kubernetes Health Probes: Liveness, Readiness, and Startup.

Key Takeaways: 

1️⃣ Liveness Probe: Asks, "Is my app running?" If it fails (e.g., a deadlock), Kubernetes restarts the container. This is the core of self-healing. 

2️⃣ Readiness Probe: Asks, "Is my app ready to serve traffic?" If it fails (e.g., still warming up), Kubernetes stops sending it new requests. This prevents users from seeing errors. 

3️⃣ Startup Probe: Asks, "Is my app still starting?" This is crucial for slow-booting applications, preventing the Liveness probe from restarting them before they are fully up. 

4️⃣ Hands-on Experiments: ✅ Configured an exec liveness probe to check for a file (/tmp/healthy). 🚀 Watched Kubernetes automatically restart the container after the file was deleted and the probe failed. 💡 Explored the three probe types: httpGet (for APIs), tcpSocket (for ports), and exec (for custom commands). 

5️⃣ Health probes are essential for building robust, self-healing applications. They ensure reliability, prevent traffic from being sent to unhealthy pods, and automate recovery from failures.


![Image](https://github.com/user-attachments/assets/61e1e2b6-8d14-45d2-a5eb-447dab731c0d)
