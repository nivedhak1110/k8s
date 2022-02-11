Kubernetes core concepts
-------------------------
1. Need of Orchestrator - kubernetes

What happens when the number of users increased ?
Can able to handle the load ? 
Scale up / Scale Down ? 
Deploy a new containers when containers are down ! 
Keep watching on instances, n/w connectivity, health of the instances are tedious process
What about Docker host itself failing? 
How to manage multiple Docker host machines?


2. what is cluster & nodes
3. Master & worker nodes in kubernetes
4. Master components ( v basic)
5. Single node cluster
6. Install minikube -- tool to implement single node cluster
 
curl -LO    https://github.com/kubernetes/minikube/releases/download/v1.25.1/minikube-darwin-arm64 -- binary download 
install minikube-darwin-arm64  /Users/karthikey.dhandapani/bin/minikube  -- install binary in the destined path

echo $PATH -- make minikube accessible everywhere ( like env var)
vi ~/.bash_profile PATH=$PATH:/Users/karthikey.dhandapani/bin 
source ~/.bash_profile -- reflect changes 
minikube start -- create cluster


7. Simple practice on Yaml
   > http://www.yamllint.com/
   
8. What is POD , multi container POD (example - exporters)
9, What is service
9. Run your app as POD in k8s
10. Replicas
11. Deployments
12. Namespace




RINMAC528:minikube ar-nivedha.kuppuraju$ **minikube status**
❗  Executing "docker container inspect minikube --format={{.State.Status}}" took an unusually long time: 2.015163571s
💡  Restarting the docker service may improve performance.
minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured

RINMAC528:minikube ar-nivedha.kuppuraju$ **kubectl get node** 
NAME       STATUS   ROLES                  AGE   VERSION
minikube   Ready    control-plane,master   21h   v1.23.1
RINMAC528:minikube ar-nivedha.kuppuraju$ kubectl get pod
No resources found in default namespace.
RINMAC528:minikube ar-nivedha.kuppuraju$ **kubectl get pod -n kube-system**
NAME                               READY   STATUS    RESTARTS      AGE
coredns-64897985d-pbg6l            1/1     Running   0             21h
etcd-minikube                      1/1     Running   0             21h
kube-apiserver-minikube            1/1     Running   0             21h
kube-controller-manager-minikube   1/1     Running   0             21h
kube-proxy-j8tnt                   1/1     Running   0             21h
kube-scheduler-minikube            1/1     Running   0             21h
storage-provisioner                1/1     Running   3 (98m ago)   21h


