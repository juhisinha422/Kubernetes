Kubernetes VPA (Vertical Pod Autoscaler)!

Kubernetes Vertical Pod Autoscaler (VPA) is a component you install in your cluster. It increases and decreases container CPU and memory resource configuration to align cluster resource allotment with actual usage.
 
Kubernetes VPA resource configuration types:

With VPA, there are two different types of resource configurations that we can manage on each container of a pod:

- What is a request?

Requests define the minimum amount of resources that containers need. For example, an application can use more than 256MB of memory, but Kubernetes will guarantee a minimum of 256MB to the container if its request is 256MB of memory.

- What are limits?

Limits define the maximum amount of resources that a given container can consume. Your application might require at least 256MB of memory, but you might want to ensure that it doesn’t consume more than 512MB of memory, i.e., to limit its memory consumption to 512MB.

Components of VPA: -

- The VPA Recommender: Monitors resource utilization and computes target values.

- The VPA Updater: Evicts those pods that need the new resource limits.

Implements whatever the Recommender recommends if “updateMode: Auto“ is defined.

- The VPA Admission Controller: Changes the CPU and memory settings (using a webhook) before a new pod starts whenever the VPA Updater evicts and restarts a pod.

How does Kubernetes VPA work?

1. The user configures VPA.

2. VPA Recommender reads the VPA configuration and the resource utilization metrics from the metric server.

3. VPA Recommender provides pod resource recommendations.

4. VPA Updater reads the pod resource recommendations.

5. VPA Updater initiates the pod termination.

6. The deployment realizes the pod was terminated and will recreate the pod to match its replica configuration.

7. When the pod is in the recreation process, the VPA Admission Controller gets the pod resource recommendation. Since Kubernetes does not support dynamically changing the resource limits of a running pod, VPA cannot update existing pods with new limits. It terminates pods that are using outdated limits. When the pod’s controller requests the replacement from the Kubernetes API service, the VPA Admission Controller injects the updated resource request and limit values into the new pod’s specification.

8. Finally, the VPA Admission Controller overwrites the recommendations to the pod. In our example, the VPA admission controller adds a “250m” CPU to the pod.

Know more in the original article : 
https://www.apptio.com/topics/kubernetes/autoscaling/vertical/

![Image](https://github.com/user-attachments/assets/10976f62-d038-49df-9388-1e6d2e655ff7)

