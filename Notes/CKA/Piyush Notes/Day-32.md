Day-32

Today’s deep dive was all about Pod Networking & Linux Network Namespaces in Kubernetes 

We explored what actually happens behind the scenes when a Pod starts — and how containers inside a Pod share the same network namespace using a pause container.

Here’s what we covered:

1) Understood how the pause container manages the Pod’s shared network stack
2) Explored how veth pairs connect Pods to the host network
3) Used commands like ip netns, lsns, and ip link to inspect namespaces
4) Learned how to trace network interfaces between Pods and Nodes
5) Saw how different CNI plugins (like Calico, Flannel, etc.) create and manage virtual networks

Key takeaway:
Every Pod in Kubernetes gets its own isolated network namespace, but all containers inside that Pod share it — enabling communication via localhost. The pause container is the hidden hero that keeps this namespace alive even when app containers restart. 

Pro Tip:
Use kubectl exec and ip netns exec to explore how Pods connect to the host  it’s one of the best ways to truly understand Kubernetes networking in action.

![Image](https://github.com/user-attachments/assets/46770db0-5fce-4642-ab55-fd45ff48418e)
