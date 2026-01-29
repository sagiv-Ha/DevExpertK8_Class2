# DevExpertK8_Class2

## Part 0 – Prerequisites


**Commands:**
```bash
kubectl cluster-info
kubectl get nodes
```
### Output 
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

## Part 1 – Namespace
**Commands:**
```bash
kubectl get namespaces
```
### Output 
```text
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2\yaml> kubectl apply -f .\namespace.yaml
namespace/dev created
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2\yaml> kubectl get ns
NAME              STATUS   AGE
default           Active   7d1h
dev               Active   4s
kube-node-lease   Active   7d1h
kube-public       Active   7d1h
kube-system       Active   7d1h
```
### Screenshots
![Create Namespace](screenshots/create_namespace.png)

