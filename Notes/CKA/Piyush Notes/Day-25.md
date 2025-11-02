Day-25

Today’s deep dive was all about understanding Service Accounts in Kubernetes 

We often talk about users in Kubernetes — but did you know there are two types?

👤 Human Users – Engineers logging in for troubleshooting or cluster management.

🦾 Service Accounts – Automation identities used by applications, controllers, or CI/CD systems.

Think of Service Accounts as “non-human users” that allow tools like Jenkins, Prometheus, or Datadog to interact securely with the Kubernetes API 🔐

Key Learnings:

1) Service Accounts are namespace-scoped and created automatically for each namespace.

2) Tokens and certificates are mounted as secrets into pods at      /var/run/secrets/https://lnkd.in/dSBGJkQs.

3) With RBAC roles and bindings, we can finely control what each Service Account can do..
4)They enable secure automation — no human credentials involved, just clean, auditable access.

 Best Practice:

Use Service Accounts for automation, follow the least privilege principle, and rotate tokens regularly

![Image](https://github.com/user-attachments/assets/60b2978b-ce8a-4e06-bee4-d31c560ee354)
