Day-33

Today’s focus was on Kubernetes Ingress & Ingress Controllers — the real gateway that connects the outside world to your in-cluster applications 

In Kubernetes, Services like NodePort and LoadBalancer can expose applications externally — but they have their own challenges: higher cost, cloud dependency, and limited flexibility.
 That’s where Ingress becomes a game changer

That’s where Ingress shines :
1) Learned how Ingress acts as a smart traffic router using host-based and path-based rules
2) Understood the difference between Ingress Resource, Ingress Controller, and LoadBalancer
3) Explored NGINX Ingress Controller setup (deployment via YAML and Helm)
4) Implemented routing for a “Hello World” app with custom domain mapping
5) Discovered how ingressClassName prevents conflicts in multi-controller clusters

In real-world DevOps setups, we often let the cloud’s managed Load Balancer (e.g., AWS ALB, GCP LB, Azure Front Door) handle the external traffic — and route it internally via the Ingress Controller to cluster services for fine-grained control and cost efficiency.

![Image](https://github.com/user-attachments/assets/b9c50408-95af-440c-8524-6a70ea40a2d7)
