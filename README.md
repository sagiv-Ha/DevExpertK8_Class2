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
kubectl create namespace dev
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

### What is a namespace?
A namespace is a logical grouping of resources inside the same Kubernetes cluster.

### Why it is considered logical (not physical) separation
Because all namespaces still share the same nodes and infrastructure.

## Part 2 – Pod
**Commands:**
```bash
kubectl aaply -f ./yaml/create_pod.yaml
kubectl get pod -n dev
kubectl delete pod demo-pod -n dev 
```
### Output 
```text
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2\yaml> kubectl apply -f .\create_pod.yaml
pod/demo-pod created
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2\yaml> kubectl get pod -n dev
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2\yaml> kubectl apply -f .\create_pod.yaml
pod/demo-pod created
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2\yaml> kubectl get pod -n dev
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2\yaml> kubectl get pod -n dev
NAME       READY   STATUS              RESTARTS   AGE
NAME       READY   STATUS              RESTARTS   AGE
demo-pod   0/1     ContainerCreating   0          9s
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2\yaml> watch kubectl get pod -n dev
watch: The term 'watch' is not recognized as a name of a cmdlet, function, script file, or executable program.
Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2\yaml> kubectl get pod -n dev
NAME       READY   STATUS    RESTARTS   AGE
demo-pod   1/1     Running   0          24s
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2\yaml> kubectl delete pod demo-pod -n dev
pod "demo-pod" deleted from dev namespace
PS C:\Users\sagiv\Devops_Course\DevExpertK8_Class2\yaml> kubectl get pod -n dev
No resources found in dev namespace.
```
### Screenshots
![Create and Delete Pod](screenshots/delete_pod.png)

### What happens if you delete this Pod? Who recreates it?
If you delete this Pod, it will not be recreated automatically, because it is not managed by a Deployment or ReplicaSet.

## Part 3 – Deployment 
