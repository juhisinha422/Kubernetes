𝐊𝐮𝐛𝐞𝐫𝐧𝐞𝐭𝐞𝐬 𝐈𝐧𝐠𝐫𝐞𝐬𝐬 

 What is Ingress?

Ingress is a Kubernetes API object that manages external access to services within a cluster, typically HTTP/HTTPS traffic.

⚡ Why Use Ingress Instead of Just Services?

- Without Ingress:

Each Service (NodePort/LoadBalancer) = separate entry point

More LoadBalancers → more cost
Hard-to-manage URLs (:30001, :30002, etc.)

- With Ingress:

One single entry point for multiple apps

Centralized routing control

Built-in TLS/SSL termination

Path-based & host-based routing

Extra features like auth, redirects, rate limiting, sticky sessions

 𝐑𝐨𝐥𝐞 𝐨𝐟 𝐭𝐡𝐞 𝐈𝐧𝐠𝐫𝐞𝐬𝐬 𝐂𝐨𝐧𝐭𝐫𝐨𝐥𝐥𝐞𝐫

 Ingress itself is just rules. The Ingress Controller is the pod that makes it work:

Reads Ingress resources

Configures itself as a load balancer (HTTP reverse proxy)

Routes traffic to the right Services

 Without an Ingress Controller, your Ingress resources do nothing.

🌐 Common Ingress Controllers

NGINX → most popular, widely adopted

Traefik → dynamic & cloud-native friendly

HAProxy → high-performance load balancer

Takeaway: Use Services to expose Pods internally, and Ingress for smart, centralized, and cost-effective external access.

![Image](https://github.com/user-attachments/assets/1c08ad06-c0b1-4ba1-a100-141afd9f7dfc)
