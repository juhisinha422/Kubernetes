Kubernetes Journey – Day 7 

 Topic: Namespaces & Resource Isolation

Namespaces in Kubernetes provide a logical way to separate cluster resources for different teams, projects, or environments. They are essential for managing large clusters effectively.


*Why Namespaces?

-Separate environments (dev, staging, prod)

-Enable multi-tenancy in shared clusters

-Apply RBAC & ResourceQuotas for better control

-Keep workloads organized & secure

⚙️ Handy #Commands

kubectl get namespaces

kubectl create namespace dev-team

kubectl run nginx --image=nginx -n dev-team

kubectl config set-context --current --namespace=dev-team

*Always use namespaces to group workloads and apply quotas/limits to prevent resource hogging.

#Quiz Time

🕝 Which default namespace in Kubernetes is used for system components?

A) default

B) kube-public

C) kube-system

D) kube-node-lease

Ans: C - kube-system :: Used for K8s system components like API server, scheduler, controller manager, etc. These are essential for cluster operation.


![Image](https://github.com/user-attachments/assets/4984c977-6634-4ef4-b7af-e66b4854938f)
