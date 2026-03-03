Day 8/60: Kubernetes Services!

I’m officially 13% of the way through my hashtag#60DaysOfK8s challenge, and today was all about Connectivity.

One of the biggest hurdles for beginners in Kubernetes is realizing that Pods are ephemeral—they die and get replaced with new IP addresses. So, how do we keep the traffic flowing? Services.

Today, I deep-dived into the four heavy hitters:

🔹 ClusterIP (The Internal Connector): The default service type. It provides an internal-only IP for communication inside the cluster (e.g., your frontend talking to your backend).

🔹 NodePort (The External Gateway): Opens a specific port (30000-32767) on every Node’s IP to let outside traffic in.

🔹 LoadBalancer (The Cloud Standard): The go-to for production on AWS/Azure/GCP. It provisions a real external Load Balancer to give you a single entry point.

🔹 ExternalName: A clever way to map internal services to external DNS names without using selectors.

Key Takeaway: Understanding the difference between Port, TargetPort, and NodePort is a total game-changer for troubleshooting connectivity issues!

<img width="578" height="530" alt="Image" src="https://github.com/user-attachments/assets/2943bb36-3525-4c67-bbbf-295352edf354" />
