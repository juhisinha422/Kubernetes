Day-12 

Today I explored three powerful Kubernetes workload controllers that form the foundation of real-world DevOps automation 

1️⃣ DaemonSet — ensures one pod per node. Ideal for monitoring, logging, and networking agents like Calico or kube-proxy.
 2️⃣ Job — executes once and completes successfully; great for setup or one-time automation tasks.
 3️⃣ CronJob — schedules recurring workloads using the familiar Linux cron syntax:
# ┌───────────── minute (0 - 59)
# │ ┌───────────── hour (0 - 23)
# │ │ ┌───────────── day of month (1 - 31)
# │ │ │ ┌───────────── month (1 - 12)
# │ │ │ │ ┌───────────── day of week (0 - 6)
# │ │ │ │ │
# * * * * *

 These controllers keep clusters consistent, self-healing, and always on schedule — essential for scalable DevOps operations.


![Image](https://github.com/user-attachments/assets/761c3d32-5602-4a85-9308-31ff898a336b)
