How Kubernetes Cluster AutoScaler Works ?


1) Some pods stay Pending when no node has enough CPU or memory.

2) The Autoscaler detects them and scans all node groups for capacity.

3) It selects a matching group and triggers the creation of a new node.

4) The new node joins the cluster, and the pending pods get scheduled on it.

5) Later, nodes with low usage are drained and removed to save cost.

<img width="800" height="500" alt="Image" src="https://github.com/user-attachments/assets/4ca383a2-7c57-4cf7-a756-920570b80d29" />
