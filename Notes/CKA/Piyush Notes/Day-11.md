#Day-11 
Today I explored Multi-Container Pods — focusing on Init Containers & Sidecar Containers 

Key takeaways:
1) Init Containers run before the main app — perfect for setup or dependency checks.
2) Sidecar Containers run alongside the main app — great for logging, monitoring, or syncing tasks.
Both share the same Pod resources (CPU, memory, network).

Learning how these containers work together gave me deeper insight into real-world K8s deployments and service orchestration.


![Image](https://github.com/user-attachments/assets/56f9ee23-2633-40da-b729-78a7cd4f997f)
