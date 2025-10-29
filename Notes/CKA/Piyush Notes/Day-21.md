Day-21

Today was all about securing communication inside Kubernetes using TLS certificates 🔐 

 Hands-on Demo:

 1️⃣ Generated private key & CSR

openssl genrsa -out <username>.key 2048  

openssl req -new -key <username>.key -out <username>.csr -subj "/CN=<username>"

2️⃣ Created csr.yaml and applied it
kubectl apply -f csr.yaml  
kubectl certificate approve <name>

3️⃣ Extracted & decoded the approved certificate with the help of simple command : echo "<certificate>" | base64 -d 
 
Key Learning:

Every K8s component communicates securely using TLS — understanding this flow helps DevOps engineers automate and troubleshoot authentication like pros

![Image](https://github.com/user-attachments/assets/47e51123-b8a2-4efe-bac7-5d1be02afeef)
