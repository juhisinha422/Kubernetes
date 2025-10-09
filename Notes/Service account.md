𝐒𝐞𝐫𝐯𝐢𝐜𝐞 𝐀𝐜𝐜𝐨𝐮𝐧𝐭 𝐢𝐧 𝐊𝐮𝐛𝐞𝐫𝐧𝐞𝐭𝐞𝐬

A ServiceAccount (SA) in Kubernetes is a special type of account designed for workloads running inside Pods to communicate securely with the Kubernetes API.

Unlike User Accounts (used by humans, managed outside Kubernetes, e.g., via IAM, LDAP, or certificates), ServiceAccounts are managed within the cluster itself and are intended for applications, controllers, and other system components.

🔑 Key Points about ServiceAccounts
1. Identity for Pods
- Every Pod in Kubernetes runs under a ServiceAccount.
- If not specified, the Pod automatically gets the default ServiceAccount of its namespace.

2. Authentication
- ServiceAccounts use bearer tokens (JWTs) to authenticate with the Kubernetes API server.
- In Kubernetes v1.24+, these tokens are ephemeral (short-lived) and mounted automatically into Pods.

3. Authorization
- Having a ServiceAccount alone doesn’t mean it has access.
- Permissions are granted using RBAC (Role / ClusterRole + RoleBinding / ClusterRoleBinding).

4. Namespace Scoped
- A ServiceAccount exists within a namespace.
- For cluster-wide access, you must bind it with a ClusterRoleBinding.


![Image](https://github.com/user-attachments/assets/9945290b-c055-42a9-b04d-81fd5a23ccbc)

![Image](https://github.com/user-attachments/assets/0a6cad35-1736-45ff-92e0-aedeca74cbc1)


![Image](https://github.com/user-attachments/assets/7b9ecfb6-119b-44e9-b95a-031b5548d00e)

![Image](https://github.com/user-attachments/assets/8bba6821-7c64-4877-b625-dc9b8f44402e)



