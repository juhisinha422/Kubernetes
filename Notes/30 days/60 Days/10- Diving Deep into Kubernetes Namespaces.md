Day 10/60: Diving Deep into Kubernetes Namespaces!

Small steps lead to big clusters! Today marks double digits in my 60 Days of Kubernetes Challenge, and I’ve been digging into how K8s handles resource isolation through Namespaces.

While it might seem like a simple way to "organize" files, there is a lot more happening under the hood—especially regarding networking and security.

Key Takeaways from Today:

Logical Isolation: Namespaces are the secret to running multiple environments (Dev, Test, Prod) or multiple teams on the same physical cluster without stepping on each other's toes.

Default vs. System: Learned why we should stay out of kube-system and how the default namespace acts as the "catch-all" if you aren't specific.

The Networking Twist: This was the "Aha!" moment. While Pod IPs are cluster-wide, Hostnames are Namespace-wide.

To talk to a service in the same namespace: curl my-service

To talk to a service in a different namespace: You need the FQDN (Fully Qualified Domain Name) like my-service.namespace.svc.cluster.local.

Efficiency: Practiced using imperative commands like kubectl create ns for speed, versus declarative YAML for production-grade tracking.

It’s one thing to read about it; it’s another to try and curl a service and realize you forgot the namespace suffix! 😅

<img width="800" height="416" alt="Image" src="https://github.com/user-attachments/assets/a19b324e-dbe6-4ad9-b9aa-20899ae6224e" />
