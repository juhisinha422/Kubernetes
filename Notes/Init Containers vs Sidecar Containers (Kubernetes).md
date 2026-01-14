# Init Containers vs Sidecar Containers (Kubernetes)

In **:contentReference[oaicite:0]{index=0}**, Pods can run **multiple containers** that serve different purposes.

Two very common container patterns are:
- **Init Containers**
- **Sidecar Containers**

Understanding the difference is **important for production design and interviews**.

---

## Init Containers

**Init Containers run BEFORE the main application containers start.**

### Key Characteristics
- Run **before** the app
- Run **one by one**, in order
- Run **only once**
- **Block application startup** until successful
- Focused on **setup and preconditions**

### Typical Use Cases
- Waiting for databases or external services
- Running migrations or bootstrap scripts
- Preparing configuration files
- Setting file permissions

---

## Sidecar Containers

**Sidecar Containers run ALONGSIDE the main application containers.**

### Key Characteristics
- Run **with** the app
- Run **continuously**
- Do **not block startup**
- Support the app **during runtime**
- Restart independently of the app container

### Typical Use Cases
- Log forwarding
- Metrics collection
- Service mesh proxies
- Configuration reloaders

---

## Comparison Table


::contentReference[oaicite:1]{index=1}


| Feature | Init Container | Sidecar Container |
|------|----------------|------------------|
| Startup time | Runs before app | Runs alongside app |
| Execution | Runs once | Runs continuously |
| Startup blocking | Blocks app startup | Does not block startup |
| Primary role | Setup & preparation | Runtime support |
| Failure impact | App never starts | App keeps running |

---

## When to Use Which?

### Use Init Containers when:
- Something **must be ready before** the app starts
- Startup order matters
- Setup logic should not live in app code

### Use Sidecars when:
- Continuous support is needed
- The app needs help **while running**
- Observability or networking is required

---

## In Simple Words

> **Init containers prepare the environment.**  
> **Sidecar containers support the application while it runs.**

Both patterns are fundamental to Kubernetes pod design.

---

## Interview Tip 🎯

**Question:** Can a sidecar replace an init container?

**Answer:**  
No. Sidecars do not guarantee startup ordering, while init containers explicitly block application startup until prerequisites are met.

---

## Final Takeaway

> Choose **init containers** for setup.  
> Choose **sidecars** for runtime support.

Knowing this distinction signals **strong Kubernetes fundamentals**.
