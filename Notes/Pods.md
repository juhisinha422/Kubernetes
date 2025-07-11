Kubernetes Pods – Deep Dive with Architecture Diagram

A Pod is the most fundamental unit in Kubernetes — it encapsulates one or more containers that share networking, storage, and lifecycle. Let’s explore every component shown in the image:

1. The Pod Itself

A pod wraps around containers.

It is the deployable unit for Kubernetes (not containers directly).

Pods run on Nodes, managed by the kubelet.


2. Containers Inside the Pod

The diagram shows two containers:

web container

sidecar container


> Kubernetes supports multi-container pods, often used for sidecars (e.g., log shippers, proxies).

Each container includes:

An image (e.g., nginx)

Command/args

Volume mounts

Ports exposed


3. Volume Mounts

Both containers mount a shared volume:

web mounts /usr/share/app/html

sidecar mounts /var/log


This allows them to share data — e.g., web app generates logs, sidecar reads them.

volumeMounts:

 - name: shared-volume

 mountPath: /usr/share/app/html


4. Volume (type: emptyDir)

The volume is defined at the pod level.

emptyDir is a temporary volume, deleted when the pod is deleted.

Good for shared storage between containers in the same pod.


volumes:

 - name: shared-volume

 emptyDir: {}

> This pattern is common in logging or caching.


 5. Labels

Labels like app: web and env: prod are used for:

Pod identification

Selection for services, deployments, policies

metadata:

 labels:

 app: web

 env: prod

> Labels are essential for service selectors and monitoring tools.

 
6. Ports

Each container may expose ports to communicate:

Here, the web container exposes port 80.

Kubernetes uses this info for probes, services, etc.


ports:

 - containerPort: 80


7. Hostname

Pods can be assigned DNS hostnames or be accessed via cluster DNS.

The diagram shows web-pod as the pod’s hostname.

Pods can discover each other using DNS internally.

8. Restart Policy

The policy here is Always.

Other options include Never and OnFailure.

Default for Deployments: Always

restartPolicy: Always



9. Summary of Benefits in This Pod Setup:

Component Purpose

Sidecar Container Collect logs, enhance modularity

Shared Volume Enable inter-container data sharing

Labels Organize and select pods

Ports Facilitate networking and health checks

Restart Policy Ensure availability


<img width="720" height="498" alt="Image" src="https://github.com/user-attachments/assets/848a0f33-1ef3-4713-9232-778cb03ac1ad" />
