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

<img width="800" height="581" alt="Image" src="https://github.com/user-attachments/assets/6df61d66-3943-4399-a623-0f5829bc8e8d" />

<img width="457" height="327" alt="Image" src="https://github.com/user-attachments/assets/702f550c-b8f3-4886-a7e4-f3676351c6a3" />

<img width="1333" height="352" alt="Image" src="https://github.com/user-attachments/assets/c06ce70e-43f9-443d-8d15-f889562c180f" />

<img width="771" height="199" alt="Image" src="https://github.com/user-attachments/assets/cb6420ed-e12a-4754-b958-9914ab9976d0" />
