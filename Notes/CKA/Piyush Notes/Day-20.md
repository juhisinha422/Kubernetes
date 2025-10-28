#Day-20 

Understanding how data is secured over the internet is non-negotiable for any tech professional. Today was a deep dive into SSL/TLS, the protocol that puts the "S" in HTTPS.

Key Takeaways: 

1️⃣ HTTP vs. HTTPS: HTTP sends all data (even passwords!) in plain text, making it easy for hackers to "sniff." sniffing. HTTPS fixes this by using TLS (Transport Layer Security) to create an encrypted, secure channel between your browser and the server.

2️⃣ Hybrid Encryption: TLS cleverly uses both types of encryption. It starts with slower Asymmetric Encryption (a Public/Private key pair RSA) to only verify the server's identity (via a Certificate) and securely exchange a new, temporary Symmetric Key.

3️⃣ The Handshake: This initial process is the "TLS Handshake." Once complete, the rest of the session uses that super-fast Symmetric Key ⚡ to encrypt all the actual data (your logins, form data, etc.).

4️⃣ Simple Analogy: A server's Public Key is like an open padlock 🔓 it gives to everyone (inside its Certificate). You put your secret session key in a box, lock it with their padlock, and send it. Only the server has the matching Private Key 🔑 to open the box.

5️⃣ Why this matters: This is the foundation of internet trust. It prevents Man-in-the-Middle (MITM) attacks, protects user credentials 🛡️, and ensures data integrity. In DevOps, we are responsible for managing and automating these certificates for our services (e.g., in Kubernetes Ingress or Load Balancers) to keep our applications secure.


<img width="800" height="450" alt="Image" src="https://github.com/user-attachments/assets/87f58b24-b3f6-4076-b1a7-79347acd09bc" />
