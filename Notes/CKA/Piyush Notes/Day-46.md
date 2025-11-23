Day-46 

Today I learned how Kubernetes decides which application should run first when resources (CPU/Memory) are limited.
 Think of it like this:

👉 When a system is full, not everything can run at the same time.
 
👉 So Kubernetes gives each pod (application) a Priority Number.

👉 Higher priority = more important.
 
👉 If needed, Kubernetes will pause/evict a low-priority app to make space for a critical one.
 This process is called Preemption.

Real-world example:

Imagine a server is almost full and:
A low-priority app is running

A high-priority “critical” app needs to start

Kubernetes will automatically remove the low-priority one and allow the critical one to run.
 No human intervention needed!

🔧 Why this matters

✔️ Ensures important business services always have space

✔️ Helps maintain uptime during heavy load

✔️ Keeps clusters running smoothly and intelligently
This feature is super powerful for production workloads, especially in resource-constrained environments.


![Image](https://github.com/user-attachments/assets/18a74c6c-7571-492d-b1fb-de5bca411da9)
