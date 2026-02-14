Kubernetes Ingress YAML – Explained Simply

Ingress allows you to route external traffic to multiple services using one entry point. Let’s break down a basic Ingress YAML 👇

			🧩 YAML Explained (Simple Terms)
 
			🔹 apiVersion & kind:
					Defines that this is an Ingress object.
 			
🔹 metadata.name:
					Name of the Ingress resource.
 			
🔹 host:
					Domain name for your application (e.g. myapp.example.com)
 		
🔹 path:
					URL path users access:
					
/ui → frontend service
					
/api → backend service
 			
🔹 pathType: 
                    Prefix matches everything starting with the path.
 			
🔹 backend.service.name:
					Service where traffic should go.
 		
🔹 backend.service.port:
					Port exposed by the service.

🧠 How traffic flows:
 
User → LoadBalancer → Ingress Controller → Ingress rules → Service → Pod

💡 Key things to remember

✔ Ingress is just rules

✔ Ingress Controller does the actual routing

✔ One Ingress = many services

✔ Supports HTTPS & TLS

![Image](https://github.com/user-attachments/assets/1e535ab6-02e3-410f-9f3a-08baa457b1b8)
