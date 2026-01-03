Docker Multi-Stage Builds:

Why Multi-Stage Builds:
 Reduce image size, improve performance, and keep only what’s needed for production.

Creating the Dockerfile:
1. Two stages:
A). Installer Stage (Node.js) → Install dependencies, build app
B). Deployer Stage (NGINX) → Copy only /build directory

2. Building the Docker Image:
 Command: docker build -t multi-stage .
3. Produces a lean, production-ready image without unnecessary files.
Running & Inspecting the Container:

4. Command: docker run -dp 3000:3000 multi-stage
 Check logs & explore:
/usr/share/nginx/html → contains only build artifacts
/var/log/nginx → access & error logs

Key Takeaway:
 Multi-stage builds make Docker images smaller, faster, and secure, following best DevOps practices.



![Image](https://github.com/user-attachments/assets/b047b525-4dd8-49d5-a264-25e4f7ff0637)
