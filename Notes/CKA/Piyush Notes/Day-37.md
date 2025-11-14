#Day-37

Today I worked on Application Troubleshooting in Kubernetes — deep-diving into how microservices communicate, how services expose workloads, and how to resolve real-world connectivity issues inside a cluster! 

Key Learnings & Fixes:

1️⃣ Deployed the Example Voting App, which consists of 5 microservices — frontend, Redis, .NET worker, PostgreSQL, and results UI.

2️⃣ Verified pod placement using kubectl get po -o wide and traced traffic flow across worker nodes to identify NodePort accessibility issues.

3️⃣ Identified missing service endpoints caused by label mismatches — fixed by aligning pod labels with service selectors.

4️⃣ Debugged Result Service connectivity — the pod listened on port 80 but the service was targeting 8080, so I patched the service using kubectl edit svc result.

5️⃣ Diagnosed vote-submission failures originating from NetworkPolicy restrictions — the policy allowed only app=frontend, while our voting pods used labels like app=vote.

6️⃣ Updated the NetworkPolicy to include the correct labels, restoring connectivity between the voting app and Redis.

7️⃣ Validated everything end-to-end: NodePort access ✔️, service endpoints ✔️, Redis communication ✔️, vote submission ✔️, result page ✔️

Pro Tips Learned Today:

1️⃣ Always validate labels and selectors — most service issues come from mismatches.

2️⃣ If a service shows no endpoints, check pod labels first before diving deeper.

3️⃣ For NodePort issues, confirm node public IP + correct worker placement.

4️⃣ NetworkPolicies can silently block communication — always verify your ingress rules.

5️⃣ Debugging in Kubernetes isn’t guessing — it’s following the network path step-by-step.


![Image](https://github.com/user-attachments/assets/78176035-6939-4d0c-b3cb-6da493b93df5)
