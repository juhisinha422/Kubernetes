Day-43

Today I explored Helm the Kubernetes Package Manager that simplifies app deployments and brings true GitOps-style automation to life.

Key Learnings (In-Depth Helm + GitOps Insights): 

1️⃣ Helm : The apt/yum/choco/brew of Kubernetes
Instead of downloading binaries or applying multiple YAMLs manually, Helm bundles everything into a single installable package called a chart. 
 One command -> entire application deployed.

2️⃣ Chart :  A packaged collection of Kubernetes manifests
All YAML resources (Deployment, Service, RBAC, CRDs) are stored together.
 You no longer manage separate files you manage one chart.

3️⃣ Release : Running instance of a chart
Just like a Docker image becomes a running container,
 a Helm chart becomes a release once deployed.
 You can deploy the same chart to Dev, QA, Staging, Prod each becomes its own release.

4️⃣ Values.yaml : The real magic
You never touch templates again.
 Just update the values.yaml file to configure images, replicas, ports, ingress, resources . Helm will auto-render everything.
This is why Helm is perfect for GitOps. Declarative, reusable, environment-friendly.

5️⃣ ArtifactHub :  The central marketplace for Helm charts
Official tools like ArgoCD, Prometheus, Grafana, NGINX publish their charts here:
 🔗 https://artifacthub.io/
 Find -> pull -> install in seconds.

6️⃣ Helm Versions Matter: 
version -> chart version (update when chart/templates change)
appVersion -> actual application versionSemantic, clean, trackable.


![Image](https://github.com/user-attachments/assets/81003de1-a2b4-4b06-b517-853828826b72)
