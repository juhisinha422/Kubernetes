Day 12 of 60: Kubernetes is more than just Deployments!

Today, I shifted my focus from "permanent" services to Specialized Workloads. If you’re only using Deployments, you’re missing out on the full power of the K8s control plane.

Here is what I tackled today:

1️⃣ DaemonSets: The "Everywhere" Controller 

Ever wondered how monitoring or logging agents run on every single node automatically? That’s a DaemonSet.

Unlike a Deployment, you don’t set a replica count.

It scales with your cluster. Add a node? The Pod follows. Remove a node? The Pod is cleaned up.

Real-world use: kube-proxy, Calico/Flannel CNI, and Fluentd.

2️⃣ Jobs: Task-Oriented Pods 

Not every Pod needs to run forever. Some just have a job to do and then they need to quit.

The Goal: Run to completion.

Use Case: Database migrations, batch processing, or one-time data backups.

3️⃣ CronJobs: Scheduling the Future 

I brushed up on my Cron syntax (e.g., */5 * * * *) to automate recurring tasks.

Use Case: Nightly cleanups, weekly report generation, or clearing out old logs.

<img width="752" height="422" alt="Image" src="https://github.com/user-attachments/assets/b0cae181-c607-4fb0-8b03-0a796194e52e" />
