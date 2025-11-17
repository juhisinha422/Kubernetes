Day-40 

 Today I explored JSON, YAML, JSONPath & advanced kubectl output formatting — the hidden superpowers behind Kubernetes command-line mastery!
Most people stop at kubectl get pods.

 But real cluster debugging starts when you understand how kubectl talks to the API server, how responses are structured, and how to extract exactly the data you need.

Key Learnings

1️⃣ kubectl → API Server → JSON Response
 Every kubectl command sends an HTTP request and the API server always responds in JSON, even if you see a human-readable table.

2️⃣ See raw data anytime:
kubectl get nodes -o json
kubectl get nodes -o yaml

3️⃣ JSONPath = laser-focused queries
 Extract only what you need:
kubectl get nodes -o=jsonpath='{.items[*].metadata.name}'
kubectl get pods  -o=jsonpath='{.items[0].spec.containers[0].image}'

4️⃣ Custom Columns = clean tables
kubectl get nodes -o=custom-columns=Node:{.metadata.name},IP:{.status.addresses[*].address}

5️⃣ Sorting for better debugging
kubectl get pods --sort-by=.metadata.creationTimestamp
These tools turn kubectl from a simple CLI into a full cluster-query engine. 

 Pro Tip:

Mastering JSONPath and custom columns makes you dramatically faster at troubleshooting issues in real production clusters.
This is one of those “small skills → big impact” areas in Kubernetes.


![Image](https://github.com/user-attachments/assets/4e6001f5-ce78-4395-9140-bcb136e098ea)
