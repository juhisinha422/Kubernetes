Day 9

 StorageClass & Dynamic Provisioning-

 The backbone of persistent storage in kubernetes.

🔹 Why?

Pods are ephemeral, meaning data is lost if a Pod restarts. To persist data, Kubernetes uses Persistent Volumes (PVs) & Persistent Volume Claims (PVCs). But creating PVs manually isn’t scalable.

👉 StorageClass + Dynamic Provisioning = Automation

StorageClass → Defines types of storage (e.g., SSD, HDD, NFS).

Dynamic Provisioning → Automatically creates PVs when PVCs request them.


✅ Benefits:

No manual PV management.
Flexible & cloud-native.
Scales storage easily.

 #Example

1. User creates a PVC with a storageClassName.

2. Kubernetes provisions a PV dynamically using the defined StorageClass.

3. Pod consumes the storage seamlessly.


*Key Point-

-Reclaim Policy → What happens when PVC is deleted (Retain, Delete).

-Provisioner → Driver that connects to backend storage (AWS EBS, GCP PD, NFS, CSI).

-VolumeBindingMode → When PV is bound (Immediate or WaitForFirstConsumer).

-StorageClass & Dynamic Provisioning make Kubernetes storage powerful, automated, and production-ready.


![Image](https://github.com/user-attachments/assets/cc406288-905c-470f-8c76-fca2078322cc)
