#Day-16

fundamental concept in Kubernetes — Resource Requests and Limits 

Key Takeaways:

1️⃣ Resource Requests — define the minimum amount of CPU and memory a container needs to run. The scheduler uses these values to decide which node can host your pod.

2️⃣ Resource Limits — define the maximum amount of CPU or memory a container can use.

If a container exceeds its memory limit, it gets OOMKilled (Out of Memory).
If it exceeds its CPU limit, it gets throttled (slowed down, not killed).

3️⃣ Units Matter!

CPU: measured in cores (1 = 1 CPU, 500m = 0.5 CPU).
Memory: measured in Mi/Gi (Mi = Mebibyte = 1024² bytes).

4️⃣ Hands-on Experiments:

 ✅ Pod within limits → runs fine.

 ⚠️ Pod exceeding memory limit → crashes with OOMKilled.

 🚫 Pod exceeding node capacity → stays in Pending state.

5️⃣ Metrics Server — helps monitor real-time CPU and memory usage across nodes and pods with commands like kubectl top nodes and kubectl top pods.

6️⃣ This exercise helped me understand how Kubernetes maintains resource isolation, efficiency, and fairness across the cluster using cgroups under the hood.

<img width="800" height="544" alt="Image" src="https://github.com/user-attachments/assets/3f9bd466-ce10-4950-9de4-f501cfcdea6e" />

