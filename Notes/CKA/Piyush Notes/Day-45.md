Day-45

Today I worked hands-on with Kubernetes StatefulSets — understanding how they differ from Deployments and why stateful workloads like MongoDB rely on predictable pod identity, ordered startup, and persistent storage that survives restarts.

Key Takeaways

1️⃣ Deployments = Stateless apps
 Random pod names, no identity, no guaranteed storage. Great for APIs & frontends.

2️⃣ StatefulSets = Stateful apps
 Predictable pod identity (pod-0, pod-1), stable network DNS, and dedicated PVs that survive restarts.

3️⃣ Headless Service = the backbone
 Gives each pod its own DNS record → critical for databases like MongoDB.

4️⃣ Persistence tested
 Deleted mongodb-0 — Kubernetes recreated it with the same name and same data. Exactly how StatefulSets should behave.

Why This Matters

If your workload needs stable identity + consistent storage → StatefulSet is mandatory. Deployments simply can't guarantee that.

![Image](https://github.com/user-attachments/assets/f9fac255-94d5-41cb-bbe9-21de9547b69d)
