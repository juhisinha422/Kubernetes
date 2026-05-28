### Summary: Kubernetes Cluster Upgrades (Enterprise-Grade, Zero Downtime)

https://youtu.be/Cfznp8jRh7I?si=CCQSkm8LF0A0dZUb
This video by Abishek provides a comprehensive guide on how to perform **production-level Kubernetes cluster upgrades** with zero downtime, focusing primarily on AWS EKS but applicable to other managed Kubernetes services like AKS and GKE. The content emphasizes the importance of prerequisites, the upgrade process, and best practices to ensure smooth and safe upgrades in enterprise environments.

---

### Key Insights and Core Concepts

- **Frequency & Importance:** Kubernetes releases a new version approximately every three months. Kubernetes supports only the latest three versions at a time (e.g., 1.32, 1.31, 1.30). Upgrading regularly is crucial for security, stability, and feature compatibility.

- **Zero Downtime Upgrades:** Achieving zero downtime involves careful planning, including node cordoning and rolling updates, to ensure services remain available during the upgrade.

- **Diverse Cluster Environments:** Organizations typically maintain multiple Kubernetes clusters (dev, staging, pre-production, production). Upgrades must be tested progressively across these environments before production rollout.

---

### Prerequisites for Kubernetes Cluster Upgrade

- **Node Cordoning:** Make nodes unschedulable during the upgrade to prevent new pod deployments and minimize risk. This is recommended but optional if you have prior upgrade experience.

- **Release Notes Review:** Thoroughly read Kubernetes release notes, focusing on API changes, deprecations, and feature behavior changes (e.g., Ingress API moving from `extensions/v1beta1` to `networking.k8s.io/v1`). Ignoring this can cause resource failures post-upgrade.

- **Irreversibility:** Kubernetes cluster upgrades, especially on EKS, are irreversible. Downgrades are not supported; a fresh cluster installation is required if rollback is needed.

- **Testing in Lower Environments:** Upgrade clusters stepwise from development → staging → pre-production → production, allowing 1-2 weeks buffer to validate stability.

- **Version Synchronization:** Ensure Kubernetes control plane and nodes run the **same Kubernetes version** before upgrading to the next version (e.g., nodes and control plane both must be at $1.30$ before upgrading to $1.31$).

- **Compatibility of Cluster Autoscaler:** If using Kubernetes cluster autoscaler, ensure the autoscaler version matches the control plane version to avoid prolonged issues.

- **Available IP Addresses:** Ensure at least five free IP addresses in the subnet allocated to your cluster for upgrade operations.

- **Component Version Sync:** The kubelet version on nodes must match the control plane version.

- **Know Your Cluster:** Understand all installed controllers, add-ons, and networking setups to anticipate impacts from release note changes.

---

### Kubernetes Cluster Upgrade Process (AWS EKS Focus)

| Step                     | Description                                                                                          | Notes                                    |
|--------------------------|------------------------------------------------------------------------------------------------------|------------------------------------------|
| **1. Control Plane Upgrade**  | Initiate upgrade via AWS UI, `eksctl`, or AWS CLI. AWS manages high availability and disaster recovery of control plane. | Takes ~25 minutes; manual trigger required despite managed control plane. |
| **2. Node Group/Data Plane Upgrade** | Upgrade nodes via rolling updates or by creating new node groups and draining old ones. Methods include managed node groups, self-managed nodes, or hybrid setups. | Rolling update recommended for zero downtime; time-consuming with many nodes. |
| **3. Add-Ons Upgrade**         | Upgrade cluster add-ons like CoreDNS, VPC CNI, kube-proxy to compatible versions.                   | Usually straightforward; done post node upgrades. |

- **Managed Control Plane:** AWS manages control plane HA, scaling, and disaster recovery but **does not automatically upgrade the control plane**.

- **Node Upgrade Approaches:**
  - **Rolling Update:** Upgrade nodes one by one; preferred for large clusters.
  - **Forceful Update:** Used with Pod Disruption Budgets; riskier but faster.
  - **New Node Group Creation:** Spin up new nodes with updated versions and retire old nodes; suitable for small clusters.

- **AMI Considerations:** Nodes run on Amazon-provided or custom AMIs. If using custom AMIs or launch templates, manual updates are required. AWS-provided AMIs can be updated via the AWS console or CLI.

---

### Additional Considerations

- **Helm, Argo CD, Prometheus, Flux:** These Kubernetes controllers generally do not require stopping during upgrades. However, thorough functional or end-to-end testing post-upgrade is essential.

- **Testing Upgrade Success:** Run functional or regression tests (e.g., end-to-end test suites) to validate cluster and workloads after upgrade rather than checking individual components manually.

- **EKS Upgrade Insights Feature:** AWS provides upgrade insights in the EKS console highlighting compatibility issues, such as outdated add-ons.

- **Terraform Integration:** For infrastructure as code users, upgrading Kubernetes cluster versions can be as simple as updating version variables and applying changes.

- **EKS Auto:** AWS recently introduced EKS Auto to simplify node upgrades further, but understanding manual upgrade processes remains critical.

---

### Summary Table of Prerequisites and Upgrade Steps

| **Prerequisite**                              | **Details**                                                                                      |
|-----------------------------------------------|------------------------------------------------------------------------------------------------|
| Node cordoning                                | Optional, recommended for production safety                                                    |
| Release notes review                          | Mandatory; understand API changes/deprecations                                                 |
| Version alignment                            | Control plane and nodes must be on the same Kubernetes version                                 |
| Cluster autoscaler compatibility             | Must match control plane version                                                                |
| Available IP addresses                        | Minimum 5 free IPs in cluster subnet                                                           |
| Kubelet version sync                          | Matches control plane version                                                                   |
| Testing in lower environments                 | Upgrade dev → staging → pre-prod with buffer time (1-2 weeks)                                  |
| Cluster knowledge                             | Understand controllers, add-ons, networking                                                    |

| **Upgrade Step**                             | **Tool/Method**                     | **Duration/Notes**                                  |
|---------------------------------------------|-----------------------------------|----------------------------------------------------|
| Control plane upgrade                        | AWS UI, `eksctl`, AWS CLI         | ~25 minutes; manual trigger required               |
| Node group/data plane upgrade                | Rolling update or new node group  | Time varies; rolling update preferred for zero downtime |
| Add-ons upgrade                             | AWS UI or CLI                     | Usually quick and straightforward                   |

---

### Final Recommendations and Conclusion

- Always **test upgrades thoroughly in lower environments** before production rollout to achieve near 100% confidence in upgrade success.

- Follow a **three-step upgrade process**: control plane → node group → add-ons.

- Use **rolling updates** for node upgrades to ensure zero downtime.

- Maintain **version consistency** across control plane, nodes, kubelet, and autoscaler.

- Understand your cluster’s architecture and components deeply to anticipate upgrade impacts.

- Leverage AWS documentation and tools like `eksctl` for streamlined upgrade workflows.

- Stay updated with new features like **EKS Auto** but master manual upgrades first.

---

**This video serves as a practical and interview-relevant guide for DevOps and Cloud engineers responsible for managing Kubernetes upgrades in production environments, especially on AWS EKS.**
