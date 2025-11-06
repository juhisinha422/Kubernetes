#Day-29

Today’s deep dive was all about Kubernetes Storage — Volumes, PVs & PVCs 

Pods are stateless by default — once deleted, data’s gone.

So, I learned how to make data persist using Persistent Volumes & Claims 🙌

🔹 Explored emptyDir, PV, and PVC

🔹 Understood Access Modes & Reclaim Policies

🔹 Built a Redis + Nginx demo to verify true persistence

Pro Tip: Never use hostPath in production — go with StorageClasses for dynamic provisioning and cloud-native reliability.

<img width="800" height="394" alt="Image" src="https://github.com/user-attachments/assets/b4767c87-9efd-43c5-bf3c-4b4578847f45" />
