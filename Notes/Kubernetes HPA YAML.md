Kubernetes HPA YAML – Explained Simply.

HPA automatically scales the number of Pods based on resource usage.
Let’s break down a simple HPA YAML 👇

🧩 YAML Explained in Simple Terms

1) apiVersion: autoscaling/v2: Uses the latest HPA API with advanced metrics support.

2) scaleTargetRef: Tells HPA what to scale (usually a Deployment).

3) minReplicas: Minimum number of Pods (even when traffic is low).

4) maxReplicas: Maximum Pods allowed (protects cluster resources).

5) metrics: Defines when to scale.
6) averageUtilization: 70
        If average CPU usage across Pods goes above 70%, HPA adds more Pods. If it goes below, HPA removes Pods.

🧠 How HPA Works (Flow):

Traffic ↑ → CPU ↑ → HPA scales 

Pods up  
  
Traffic ↓ → CPU ↓ → HPA scales Pods down

💡 Production Notes

✅ Requires metrics-server

✅ Works best with stateless apps

✅ Commonly used with Ingress + Service

![Image](https://github.com/user-attachments/assets/4276f2f3-bc19-4524-bacb-34bddd5af6a2)

