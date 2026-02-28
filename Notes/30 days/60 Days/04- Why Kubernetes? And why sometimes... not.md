Headline: Day 4/40: Why Kubernetes? And why sometimes... not? 

I’m officially 4 days into my Kubernetes journey, and today’s session was a reality check on why this orchestration powerhouse exists—and why it isn't always the "magic button" for every app.

Here are my top 3 takeaways from Day 4:

🚀 1. The "Manual" Breaking Point
Running a few containers on a VM is easy. Managing 1,000+ containers across 24/7 global time zones? That’s a nightmare. Without orchestration, every crash or version update becomes a manual ticket for an exhausted admin. Kubernetes steps in to automate that "self-healing" and deployment lifecycle.

🛠️ 2. It’s About More Than Just "Running" Apps
Kubernetes isn't just a container runner. It’s an entire ecosystem that handles the "hard stuff" out of the box:

Service Discovery (How containers find each other)

Load Balancing (Spreading the traffic)

Auto-scaling (Growing with demand)

⚖️ 3. The Reality Check: Don't Over-Engineer!
The biggest lesson today? Kubernetes is not always the answer. If you have a simple 2-container app, a full K8s cluster (even a managed one like EKS or AKS) can be a waste of money and add unnecessary administrative toil. Sometimes, Docker Compose or a simple VPS is all you need. Due diligence is key!

<img width="800" height="533" alt="Image" src="https://github.com/user-attachments/assets/63167683-40b9-4f6c-9da6-7b2a0477fd06" />
