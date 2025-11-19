#Day-42

Today I deployed a Secure Private Docker Registry on Kubernetes — complete with TLS, authentication, persistent storage, and image pushing/pulling inside the cluster.

Key Learnings

1️⃣ TLS is mandatory for secure registries
Generated self-signed certs, created Kubernetes TLS secrets, and configured Docker to trust the CA across all nodes.

2️⃣ Enabled authentication using htpasswd
Created bcrypt-encrypted credentials and stored them in auth-secret to secure registry access.

3️⃣ Persistence matters
Set up PV + PVC so registry data (images) survives restarts.

4️⃣ Deployment with secrets + storage
Mounted /certs, /auth, and /var/lib/registry inside the registry container.
 Configured HTTPS + authentication using environment variables.

5️⃣ Tested full workflow

✔️ Pushed a custom NGINX image to the registry

✔️ Pulled it inside a Kubernetes pod using an imagePullSecret

Without this secret → pod fails due to unauthorized access.

Takeaway

This project ties together TLS, secrets, storage, Docker trust stores, and Kubernetes deployments — a solid hands-on dive into secure container supply chain practices within Kubernetes.


<img width="800" height="1200" alt="Image" src="https://github.com/user-attachments/assets/b50a3428-a482-446b-883e-1ed977baf893" />
