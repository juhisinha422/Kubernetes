#Day-14

Today I dove into one of the most powerful scheduling mechanisms in Kubernetes — Taints & Tolerations 

 Key Takeaways:
 1️⃣ Taints — applied on nodes to restrict which pods can run on them.
 2️⃣ Tolerations — added to pods to allow scheduling on tainted nodes.
 3️⃣ Effects — NoSchedule, NoExecute, and PreferNoSchedule define how strictly pods are filtered.
 4️⃣ NodeSelector — lets pods choose nodes by labels, while taints make nodes choose which pods to accept.

![Image](https://github.com/user-attachments/assets/acb4e427-b620-4c85-bb3b-bc780ab947c9)
