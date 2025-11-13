Day-36

Today I explored Kubernetes Logging and Monitoring — diving deep into how clusters observe, measure, and troubleshoot themselves! 

Key Learnings:

 1️⃣ Installed and configured the Metrics Server, a CNCF project that powers resource metrics like CPU and memory utilization.

2️⃣ Understood how Kubelet and cAdvisor work together — cAdvisor collects container metrics, and Kubelet forwards them to the Metrics Server.

3️⃣ The Metrics API then exposes this data to the API Server — enabling commands like kubectl top nodes and kubectl top pods.
 
4️⃣ Fixed TLS certificate issues in Metrics Server by adding --kubelet-insecure-tls (for testing environments).
 
5️⃣ Explored cluster logging — Kubernetes offers basic logging, but for real observability we integrate tools like ELK, Splunk, or Grafana.
 
6️⃣ Learned about crictl, the new go-to CLI after Docker was deprecated in Kubernetes 1.24 — perfect for node-level debugging when kubectl isn’t working.
 
7️⃣ Practiced troubleshooting cluster issues using crictl ps, crictl logs, and crictl pull when the API server is down.

Pro Tips:

1️⃣ Use crictl for runtime-level debugging — it’s your lifeline when the control plane goes silent.

2️⃣ Centralize logs and metrics to external observability stacks (ELK, Prometheus, Grafana) for proactive alerts and insights.

3️⃣ Always monitor resource utilization to prevent performance bottlenecks before they hit production.

4️⃣ Monitoring isn’t just about seeing — it’s about understanding your system’s pulse and acting before it skips a beat! 

![Image](https://github.com/user-attachments/assets/d7078b2b-26aa-48ca-8584-7786a336237d)
