Day-15

Today I explored another key part of Kubernetes scheduling — Node Affinity & Anti-Affinity ⚙️

These mechanisms go beyond Taints & Tolerations and give us intelligent control over where and how pods are scheduled across nodes.

Key Takeaways:

 1️⃣ Node Affinity — allows you to target specific nodes based on labels (e.g., disk=ssd, zone=us-east-1a).
 
 2️⃣ Required vs Preferred — requiredDuringSchedulingIgnoredDuringExecution enforces strict placement, while preferredDuringSchedulingIgnoredDuringExecution defines flexible preferences.
 
 3️⃣ Node Anti-Affinity — helps you avoid certain nodes (e.g., don’t schedule in zone=us-east-1a).
 
 4️⃣ Pod Anti-Affinity — ensures similar pods (like replicas) don’t run on the same node — improving HA and resilience.
 
 5️⃣ Combine these with Taints & Tolerations for fine-grained, intelligent scheduling policies.


![Image](https://github.com/user-attachments/assets/38bfd41d-8488-4531-9647-8fa72669b371)
