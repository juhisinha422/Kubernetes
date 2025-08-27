#Kubernetes Journey – Day 8:

 Volumes & Persistent Volumes

In Kubernetes, containers are ephemeral – once a Pod is deleted or restarted, its data is lost. That’s where Volumes & Persistent Volumes (PV) come into play.

🔹 Volume – Provides storage to a Pod, ensuring data is available during container restarts inside the same Pod.

🔹 Persistent Volume (PV) – A cluster-wide storage resource that exists independently of Pods.

🔹 Persistent Volume Claim (PVC) – A request made by a Pod to use storage from a PV.

✅ Key Takeaways:

Volumes solve the ephemeral nature of containers.

PVs abstract the underlying storage (NFS, AWS EBS, GCP PD, Azure Disk, etc.).

PVCs let developers request storage without worrying about backend implementation.

StorageClasses automate dynamic provisioning of volumes.

💡 Real-World Example:

Imagine running a database Pod (MySQL/Postgres) – you cannot afford to lose data every time the Pod restarts. By using PVCs with PVs, you ensure your data persists reliably.

#Interview Question for You:

Q.What is the difference between Volume, PV, and PVC in Kubernetes?

![Image](https://github.com/user-attachments/assets/5c2c6db6-500d-4ed0-a438-4423fd911ae0)
