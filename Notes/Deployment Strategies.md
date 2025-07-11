𝐊𝐮𝐛𝐞𝐫𝐧𝐞𝐭𝐞𝐬 𝐃𝐞𝐩𝐥𝐨𝐲𝐦𝐞𝐧𝐭 𝐬𝐭𝐫𝐚𝐭𝐞𝐠𝐢𝐞𝐬 - 𝐊𝐧𝐨𝐰𝐢𝐧𝐠 𝐭𝐡𝐞 𝐏𝐫𝐨𝐬/𝐂𝐨𝐧𝐬  🤔 ☸️  

Deployment strategies offer a unique way to perform application updates with minimal downtime within a #Kubernetes cluster. 

𝑳𝒆𝒕'𝒔 𝒃𝒓𝒆𝒂𝒌 𝒕𝒉𝒆𝒎 𝒅𝒐𝒘𝒏 𝒘𝒊𝒕𝒉 𝒑𝒓𝒐𝒔 & 𝒄𝒐𝒏𝒔:

👉 𝗥𝗲𝗰𝗿𝗲𝗮𝘁𝗲 - All existing instances are terminated at once and new instances with the updated version are created

𝑷𝒓𝒐𝒔

✅ Ease of setup.

✅ Totally renewed applicate state is achieved

𝑪𝒐𝒏𝒔

❗ High impact on availability, downtime during shutdown and booting process

👉 𝗥𝗼𝗹𝗹𝗶𝗻𝗴 𝗨𝗽𝗱𝗮𝘁𝗲 - Application instances are updated one by one, ensuring high availability during the process

𝑷𝒓𝒐𝒔

✅ Ease of setup.

✅ Slow release of new version across instances

✅ Ideal for stateful applications which handle rebalancing of the data

𝑪𝒐𝒏𝒔

❗ Support to multiple APIs is tough.

👉 𝗦𝗵𝗮𝗱𝗼𝘄 - A copy of the live traffic is redirected to the new version for testing without affecting production users. This is the most complex deployment strategy and involves establishing mock services to interact with the new version of the deployment

𝑷𝒓𝒐𝒔

✅ Testing application performance in production.

✅ User is not aware of the impact.

✅ No rollout is done until performance and stability of new version is not established or met.

𝑪𝒐𝒏𝒔

❗ Expensive to maintain dual resources

❗ Complex in setup

👉 𝗖𝗮𝗻𝗮𝗿𝘆 - The new version is released to a subset of users or servers for testing before broader deployment. Canary deployment requires two identical ReplicaSets one to roll out new features to a small group of users and another for all active users. Progressively the new version is pushed to the entire infrastructure and until canary version becomes the new version all live traffic is directed to canaries

𝑷𝒓𝒐𝒔

✅ Version is released for a group of users.

✅ Ideal for performance monitoring and load.

✅ Rollback is fast.

𝑪𝒐𝒏𝒔

❗Rollout is slow

👉 𝗕𝗹𝘂𝗲-𝗚𝗿𝗲𝗲𝗻 - 

- Two identical environments are maintained: one with the current version (blue) and the other with the updated version (green)

- Traffic starts with blue, then switches to the prepared green environment for the updated version

𝑷𝒓𝒐𝒔

✅ Instant rollback possible.

✅ Entire application state changes in one go hence avoids versioning issue.

𝑪𝒐𝒏𝒔

❗Expensive as both versions required to be maintained

❗Testing of entire platform is required before production release

❗Stateful applications are hard to handle in this strategy

👉 𝗔/𝗕 𝗧𝗲𝘀𝘁𝗶𝗻𝗴 - Multiple versions are concurrently tested on different users to compare performance or user experience

𝑷𝒓𝒐𝒔

✅ Parallel running of several versions.

✅ Traffic distribution is fully controlled.

𝑪𝒐𝒏𝒔

❗Intelligent load balancer is required.

❗Tough to troubleshoot

![Image](https://github.com/user-attachments/assets/2afa9005-a816-41a6-8cab-82b5e757f43b)
