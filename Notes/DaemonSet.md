What is a DaemonSet in Kubernetes – and why should you care?

deployed an nginx DaemonSet and saw it run smoothly across nodes. 

🚀 What’s a DaemonSet?

 A DaemonSet ensures a copy of a Pod runs on every node in your cluster.

 New node added? → Pod auto-deploys there.

 Node removed? → Pod disappears too.

🔧 Use Cases:

 ✅ Monitoring agents (Prometheus Node Exporter)

✅ Log collection (Fluentd, Filebeat)

✅ Network plugins / Security daemons

🛠️ My example:

Deployed NGINX using a DaemonSet:

yaml

hashtag#kind: DaemonSet

containers:

- name: nginx-dmn-pod


image: nginx:latest

🔎 Verified with kubectl get pods -n nginx → Pod was running exactly as expected!

📌 Lesson: DaemonSets are perfect when you want something running on every node without manual scheduling.


<img width="800" height="850" alt="Image" src="https://github.com/user-attachments/assets/23017564-0856-4e23-a665-b8a68fb05881" />
