#Day-38 

Today I deep-dived into Kubernetes Control Plane Troubleshooting — fixing broken API servers, unhealthy schedulers, kubeconfig failures, and controller crash loops!

1️⃣ “Connection Refused?” → Check kube-apiserver first.
 One tiny YAML typo inside /etc/kubernetes/manifests/ can bring your entire control plane down.
 Debugging = details.

2️⃣ Using containerd? → crictl ps is the truth.
 docker ps won’t show control-plane pods anymore in v1.34 clusters.
 Know your runtime = faster troubleshooting.

3️⃣ Kubeconfig mistakes = instant failure.
 Fix it quickly by copying:
 /etc/kubernetes/admin.conf → ~/.kube/config

4️⃣ Pod stuck in Pending? → Look at kube-scheduler.
 Image pull issues or misconfigured scheduler manifests are usually the culprits.

5️⃣ Deployment not recreating pods? → kube-controller-manager is sick.
 CrashLoopBackOff often points to cert/hostPath misconfigurations.

6️⃣ kubectl cluster-info + cluster-info dump = underrated superpowers.
 Best tools for understanding overall cluster state.


![Image](https://github.com/user-attachments/assets/24edf466-31c6-4994-a5e5-35e672b964ba)
