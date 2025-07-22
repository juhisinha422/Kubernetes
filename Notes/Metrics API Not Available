 Just Fixed a "Metrics API Not Available" Issue in Kubernetes!

Today while working with kubectl top pod to monitor resource usage, I ran into this error:

❌ error: Metrics API not available

Turns out, the Kubernetes Metrics Server wasn’t properly configured. After a bit of debugging and some YAML diving, I solved it by:

✅ Deploying the Metrics Server

 ✅ Adding --kubelet-insecure-tls in the deployment arguments

 ✅ Verifying the APIService status

 ✅ Testing with kubectl top nodes and kubectl top pods — and it worked! 

🔧 Tools used:


kubectl

YAML editing'

kubectl logs, kubectl get apiservice, and a lot of patience 😄

This was a great reminder that observability tools like the Metrics Server are essential for real-time visibility into cluster performance.

If you're running Kubernetes and see this error, now you know what to check ✅

<img width="747" height="542" alt="Image" src="https://github.com/user-attachments/assets/0ca27f32-0af7-4c85-b67c-d38955169638" />
