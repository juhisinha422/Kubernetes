Dockerizing a Simple Application:

1. Setup / Prerequisites:
Docker Desktop (local) or Play with Docker (cloud-based)
Prepared environment to build and run containers

2. Cloning the Application Repository:
Fetched the sample application code from GitHub:
 git clone https://lnkd.in/diHWv-f2

3. Understanding the Dockerfile:
Layers: Base Image → Working Directory → Copy Files → Install Dependencies → Expose Port → CMD Run
Each instruction builds a layered image, improving efficiency and portability

4. Building the Docker Image:
Command: docker build -t getting-started-app .
Creates a portable image containing the application and all dependencies

5. Pushing the Image to Docker Hub:
Tagged and pushed the image to Docker Hub for sharing and reuse
Enables “build once, run anywhere” approach

6. Running and Troubleshooting the Container:
Run: docker run -p 3000:3000 YOUR_USERNAME/getting-started-app
Inspect and debug using: docker exec -it <container-id> sh
Ensures the application runs consistently in any environment

Key Takeaway:
Docker makes containerization simple, allowing developers to package, ship, and run applications efficiently while ensuring environment consistency.



![Image](https://github.com/user-attachments/assets/ae6ac344-c379-4373-9316-67136823cd9e)
