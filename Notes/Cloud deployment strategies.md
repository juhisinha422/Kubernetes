Cloud Deployment Strategies 👇

1. 𝗥𝗼𝗹𝗹𝗶𝗻𝗴 𝗗𝗲𝗽𝗹𝗼𝘆𝗺𝗲𝗻𝘁 gradually updates application instances in small batches. While some are upgraded to the new version, others still serve the current version.

This continues until all instances are running the latest version.

2. 𝗖𝗮𝗻𝗮𝗿𝘆 𝗗𝗲𝗽𝗹𝗼𝘆𝗺𝗲𝗻𝘁 starts by routing a small % of traffic to the new version.

Most users still interact with the old version, reducing risk during early rollout. Based on feedback and stability, traffic is slowly increased.

3. 𝗕𝗹𝘂𝗲 𝗚𝗿𝗲𝗲𝗻 𝗗𝗲𝗽𝗹𝗼𝘆𝗺𝗲𝗻𝘁 runs two environments side by side, one with the current version and one with the new.

Blue → current version
Green → new version

Once the new version is validated, traffic is shifted over gradually. Tools like load balancers or DNS routing handle the switchover.

![Image](https://github.com/user-attachments/assets/c08df9e9-f767-405f-a2e4-bea4cef32415)
