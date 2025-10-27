#Day-19

Understanding how to manage configuration is critical for secure and flexible applications.

Key Takeaways: 

1️⃣ ConfigMaps: The "settings file" for Kubernetes. Used to store non-sensitive data (like app URLs, environment names, or feature flags) as key-value pairs, decoupling them from your container image. 

2️⃣ Secrets: The "digital safe" for Kubernetes. Used only for sensitive data (like database passwords, API keys, and TLS certificates). K8s stores this data Base64 encoded and handles it securely.

3️⃣ Simple Analogy: A ConfigMap is a public restaurant menu 📜. A Secret is the PIN code to the restaurant's safe 🔒. You never write the PIN on the menu. 

4️⃣ Hands-on Experiments: 

✅ Created ConfigMaps and Secrets using both imperative (from-literal) and declarative (.yaml) methods. 

✅ Practiced Base64 encoding/decoding for secret data. 

✅ Injected data into Pods as environment variables (envFrom, valueFrom) and as files (volumes).

5️⃣ Why this matters: This is a production-level best practice. It means no more hard-coding passwords in code or images. This makes applications more secure, portable, and easier to manage across different environments (dev, staging, prod).

<img width="590" height="371" alt="Image" src="https://github.com/user-attachments/assets/40d26fca-9564-4789-81dd-8419f00bd45c" />
