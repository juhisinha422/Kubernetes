Why an Ingress Controller in Kubernetes?

The  bare-bones deployment of a service on a Kubernetes (K8s) cluster goes this way - the service pods are deployed on a cluster namespace, and the service makes an endpoint available for clients on the public internet to connect.

But there is an issue with having the service endpoint itself being publicly accessible. If a service instance goes down, clients connected to its endpoint become aware of it. This is true even with redundancy - the affected clients are cut off temporarily, before being re-routed to a different instance that's up.

The solution is to have an intermediate API Gateway or a Load Balancer - to implement high availability gracefully, and automatically reroute requests to an active service instance.

Plus, we need something called an Ingress Controller - which processes ingress rules (which incoming request goes to which microservice pod). 

Finally, we also need for each route - an Ingress Component. Note a route is either a pathname (the domain name plus a suffix), or a distinct sub-domain. Such a pod maps the route to the relevant microservice pod name,  based on its configuration (YAML).

More here: https://lnkd.in/ggVqm7yf

When the Ingress Controller pod receives a request from the Load Balancer, it routes that message based on its ingress rules - to the appropriate Ingress Component. Which then passes it on to the relevant microservice pod, based on its configuration.

This way, not just the service endpoint - all the pods of the service (comprising all microservices) get to have private IP addresses - and the service can remain of type ClusterIP.

To top it off, a DNS service can be used to map the domain name of each Ingress Component of this setup, to its IP address in the cluster. This completes the picture, resulting in simpler traffic routing among the pods of our service.

Of course, the DNS service is also used to map the domain name of the public endpoint that receives client requests (passing them on to the API Gateway / Load Balancer) - to a public IP.

There are many mechanisms to implement such an Ingress Controller, including:

1. Reverse Proxy - a K8s installation always came with a default nginx controller, now deprecated/retired: https://lnkd.in/g3nYaETQ

2. Service Mesh - Istio is a popular vendor, though often considered overkill: https://lnkd.in/gyppM5FS

3. Gateway API - This is the most recent, and highly recommended: https://lnkd.in/gbCYJMHj


![Image](https://github.com/user-attachments/assets/60f66266-ba1b-480d-9320-c9dfb7ac01e7)
