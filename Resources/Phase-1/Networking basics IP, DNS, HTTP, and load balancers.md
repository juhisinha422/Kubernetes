# Networking Basics for Kubernetes

## Overview

Understanding networking concepts like IP, DNS, HTTP, and load balancers is crucial when working with Kubernetes. This guide covers the fundamental components in a Kubernetes environment, specifically focusing on networking essentials.

## Table of Contents

1. [IP Addressing](#ip-addressing)
2. [DNS (Domain Name System)](#dns)
3. [HTTP (Hypertext Transfer Protocol)](#http)
4. [Load Balancers](#load-balancers)

---

## 1. IP Addressing

### What is an IP Address?

- **IP (Internet Protocol) Address**: A unique identifier for devices on a network.
- In Kubernetes, nodes (machines) and pods (containers) are assigned IP addresses for communication.
  - **Pod IP**: Every pod gets a unique IP within the cluster (assigned by CNI plugin).
  - **Node IP**: Each node (physical or virtual machine) also gets its own IP address.

### Types of IPs in Kubernetes

- **Pod IPs**: Each pod has its own IP address, which allows it to communicate with other pods directly within the same node or across nodes.
- **Service IPs**: Services in Kubernetes have a stable IP that helps route traffic to pods, regardless of their individual IPs.
  
#### Example:

When a pod in Kubernetes tries to talk to another pod, it uses the destination pod's IP address. However, if the pod is restarted or rescheduled, it could get a new IP, which is why services are used for stable communication.

---

## 2. DNS (Domain Name System)

### What is DNS?

- **DNS** is like a phonebook for the internet; it translates human-readable domain names (e.g., `www.example.com`) into IP addresses.
- Kubernetes has its own internal DNS system that helps containers and pods communicate using domain names, rather than hardcoding IP addresses.

### DNS in Kubernetes

- Kubernetes provides an internal DNS service that automatically resolves names of services and pods.
  - **Service DNS Resolution**: When you create a service in Kubernetes, you can access it by the service's name (e.g., `my-service.default.svc.cluster.local`).
  - **Pod DNS Resolution**: Pods can communicate using the DNS of other pods or services, which Kubernetes resolves automatically.

#### Example:

If you have a service named `my-service`, other pods can communicate with it using `my-service.default.svc.cluster.local`.

---

## 3. HTTP (Hypertext Transfer Protocol)

### What is HTTP?

- **HTTP** is a protocol used for transferring data on the web. It's commonly used for communication between clients (e.g., browsers) and servers, and is essential for web-based applications.
  
### HTTP in Kubernetes

- Kubernetes applications often expose HTTP services (via REST APIs, web apps, etc.).
- HTTP requests can be routed to different pods using Kubernetes services and ingress controllers.

#### Ingress Controllers:

- **Ingress**: A Kubernetes resource that manages external access to the services within the cluster, typically over HTTP and HTTPS.
- An **Ingress Controller** is the component that implements the actual routing of HTTP(S) traffic.

#### Example:

A Kubernetes service exposes an HTTP API, which is accessed externally via an Ingress resource. The Ingress controller routes the traffic to the appropriate pod based on URL paths or hostnames.

---

## 4. Load Balancers

### What is a Load Balancer?

- A **Load Balancer** distributes network traffic across multiple servers (pods or nodes) to ensure no single server is overwhelmed.
  
### Load Balancers in Kubernetes

- Kubernetes can integrate with external load balancers to distribute traffic to services.
- **Kubernetes LoadBalancer Type Service**: You can create a service of type `LoadBalancer` which allows you to automatically provision an external load balancer from a cloud provider (e.g., AWS, GCP, Azure).

#### Example:

A `LoadBalancer` type service automatically provisions a cloud load balancer and forwards traffic to the pods behind the service. This is especially useful for exposing applications to the outside world.

### Internal Load Balancing

- For internal services within the cluster, Kubernetes uses **ClusterIP** type services to load balance traffic between pods.

#### Example:

```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-service
spec:
  type: LoadBalancer
  selector:
    app: my-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8080
```

## Summary

**IP Addressing:** Every pod and node in Kubernetes gets an IP address for communication.

**DNS:** Kubernetes provides an internal DNS system to resolve names of services and pods, simplifying communication.

**HTTP:** HTTP is commonly used to expose and interact with services within Kubernetes. Ingress and Ingress controllers are essential for routing external HTTP traffic to the appropriate services.

**Load Balancers:** Kubernetes integrates with external load balancers to distribute traffic to services, helping to scale applications efficiently.
