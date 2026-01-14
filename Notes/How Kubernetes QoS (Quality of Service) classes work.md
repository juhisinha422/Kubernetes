How Kubernetes QoS (Quality of Service) classes work

Kubernetes doesn’t treat all Pods equally.
It assigns a QoS class to every Pod based on resource requests and limits.

There are three QoS classes:

1. Guaranteed

a. CPU and memory requests == limits for all containers.

b. Highest priority.

c. Least likely to be evicted.

d. Best for critical workloads.

2. Burstable

a. Requests are set, but limits are higher.

b. Medium priority.

c. Can burst when resources are available.

d. Most common QoS class in production.

3. BestEffort

a. No requests and no limits.

b. Lowest priority.

c. First to be evicted under resource pressure.

d. Not recommended for production apps.

How Kubernetes uses QoS:

1. During node memory pressure, eviction happens in this order:

a. BestEffort first

b. Burstable next

c. Guaranteed last

2. Scheduler and kubelet rely on QoS to maintain node stability.

Why this matters:

1. Wrong QoS leads to unexpected Pod evictions.

2. Proper requests and limits protect critical workloads.

3. QoS directly impacts reliability and performance.

In simple words:

QoS decides which Pods survive when the node runs out of resources.

<img width="800" height="533" alt="Image" src="https://github.com/user-attachments/assets/44d83c94-6611-4cf1-b8f5-66c9f64fb0f2" />
