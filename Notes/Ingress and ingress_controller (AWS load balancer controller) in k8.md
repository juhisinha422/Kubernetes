Ingress and ingress_controller (AWS load balancer controller) in k8
====================
whatingress in k8?
---------------------
ingress is a k8 resource  where we define rules ,it is used to  manage  the "external" #https traffic from the user(client) and route the traffic(request) to backend services which is inside the k8 cluster  based on hostname or path (URL).

ingress_controller(AWS load balancer ingress controller)
----------------------------------------------
it is a controller and which always watches the  "watches Ingress resources"  ,Based on the annotations defined in the Ingress, it automatically provisions and manages an Application Load Balancer (ALB) in AWS.

It implements whatever is defined in the Ingress resource

<img width="800" height="487" alt="Image" src="https://github.com/user-attachments/assets/2ae1202b-af24-47cb-bdf0-c890b1a1aca4" />
