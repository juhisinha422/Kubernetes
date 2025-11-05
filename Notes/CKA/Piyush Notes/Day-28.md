Day-28

Before diving deep into storage concepts in Kubernetes, I decided to revisit Docker storage — and it turned out to be a great refresher!

Key Learnings:

 1️⃣ Discovered how Docker images are built in multiple read-only layers, forming the base of immutable infrastructure.

2️⃣ Understood how containers create a writable layer on top of image layers for runtime changes.

3️⃣ Learned that data inside a container is temporary — it’s deleted when the container stops — and how volumes help make data persistent.

4️⃣ Explored storage drivers (like overlay2) that manage how layers and container data are stored and merged.

5️⃣ Created and attached Docker volumes using:
docker volume create data_volume  
docker run -v data_volume:/app -dp 3000:3000 day27
and confirmed data persistence even after container removal.

6️⃣ Differentiated between volumes and bind mounts, understanding when to use each.


![Image](https://github.com/user-attachments/assets/ad8d34b7-e07f-4a05-9145-9e624c03232e)
