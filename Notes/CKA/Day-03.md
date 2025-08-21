Day 3 (Journey to CKA)

Today’s Topic: Kube-Scheduler

A common misconception 👉 The scheduler doesn’t actually run or place the pod on the node.
It only decides the best node for a pod to run on.

The actual placement & execution is handled by the Kubelet on that node. ✅

🔹 How does the Scheduler decide?
The scheduler looks at each pending pod and tries to find the “best fit” node for it, based on:

Resource requirements (CPU, Memory, GPU etc.)

Node selectors (explicit matching rules)

Taints & Tolerations (to restrict or allow workloads on certain nodes)
Node affinity / anti-affinity (keep pods together or spread across nodes)

Pod affinity / anti-affinity (influence pod placement based on other pods)

Topology spread constraints (to evenly spread pods across zones/nodes)

🔹 The Process in 2 Steps:

1️⃣ Filtering (Predicates): First, the scheduler filters out nodes that cannot run the pod. (Example: node doesn’t have enough CPU).

2️⃣ Scoring (Priorities): Then, it ranks the remaining nodes and picks the highest-scoring node.

📌 Example:

If you request a pod with 2 CPU and 2 GB memory, the scheduler will:
Filter out nodes that don’t have that much free space

Among the remaining, pick the one with the best score based on affinity, spreading rules, etc.

👉 In short, the Kube-Scheduler = The “matchmaker” between pods and nodes 


![Image](https://github.com/user-attachments/assets/82a3fe2b-8678-477d-956c-4704791b8c1d)
