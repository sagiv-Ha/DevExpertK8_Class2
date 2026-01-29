# DevExpertK8_Class2

## Part 0 – Prerequisites

### Output 
**Commands:**
```bash
kubectl cluster-info
kubectl get nodes
```
```text
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2> kubectl cluster-info
Kubernetes control plane is running at https://127.0.0.1:48997
CoreDNS is running at https://127.0.0.1:48997/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2> kubectl get node
NAME       STATUS   ROLES           AGE    VERSION
minikube   Ready    control-plane   7d1h   v1.34.0
```
### Screenshots

![Cluster Info Nodes](screenshots/cluster-info-nodes.png)

![Create Namespace](screenshots/create_namespace.png)
