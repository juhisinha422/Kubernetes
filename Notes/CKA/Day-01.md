Kubernetes Learning from Scratch – All the way to CKA

 – Day 1: KubeAPI Server




The KubeAPI Server is the entry point of Kubernetes – everything in the cluster goes through it.

🔑 What it does:

✅ Authenticates users (who is making the request)

✅ Validates requests (are they correct?)

✅ Talks directly to etcd, which stores all cluster data

✅ Acts as a communication hub – the Scheduler and Kubelet interact with it to perform updates

📌 Setup note:

If we create a cluster using kubeadm, the API Server runs as a pod inside the kube-system namespace on the control-plane node.

In short, the KubeAPI Server is like the brain’s nervous system – connecting every action and making sure the cluster state is always updated.

![Image](https://github.com/user-attachments/assets/0ff3d5c2-c0aa-4dda-ab0c-86c3267f1774)
