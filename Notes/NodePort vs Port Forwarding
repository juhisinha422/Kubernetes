𝐍𝐨𝐝𝐞𝐏𝐨𝐫𝐭 𝐯𝐬 𝐏𝐨𝐫𝐭 𝐅𝐨𝐫𝐰𝐚𝐫𝐝𝐢𝐧𝐠 𝐢𝐧 𝐊𝐮𝐛𝐞𝐫𝐧𝐞𝐭𝐞𝐬.

NodePort and port forwarding both expose services running inside a Kubernetes cluster, but they serve different purposes and operate at different layers.

🎯 𝐍𝐨𝐝𝐞𝐏𝐨𝐫𝐭

• Exposes a Service on a static port (30000–32767) on every node's IP.

• Accessible externally using <NodeIP>:<NodePort>.

• Mostly used for testing, small-scale deployments, or with external load balancers.

• Requires a Service object in Kubernetes (type: NodePort).

• Persistent and works cluster-wide.

🧠 Example use case: You want external users to access your app via a public IP and a specific port.

🚪 𝐏𝐨𝐫𝐭 𝐅𝐨𝐫𝐰𝐚𝐫𝐝𝐢𝐧𝐠

• Temporarily forwards a local machine port to a pod's port inside the cluster.

• Done using:

   kubectl port-forward pod/my-pod 8080:80

• Only works from your local system and lasts only as long as the command runs.

• Ideal for debugging, development, or accessing internal services.

🧠 Example use case: You want to test or debug an internal microservice running in a pod from your local machine.

![Image](https://github.com/user-attachments/assets/d097c45e-0589-49bb-a121-47f96d32b978)
