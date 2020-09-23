```
=== kubernetes-intro ===

introductory Kubernetes course on Udemy: https://www.udemy.com/course/kubernetes-fast-track/
Below are few things that i've learnrt

Docker & kubernetes goes hand in hand. Kubernetes helps you manage containerized apps in diff envs (physical, cloud & VMs). 
Docker is used as the container runtime and kubernestes as the platform to deploy the images
Kubernetes is a wrapper for Docker, from Docker side of things, docker images are used which then become containers

# Inside a pod there is one or more containers / apps  e.g one pod per app
  each pod has its own IP, when a pod dies, a new pod is created. 
  A pod get wrapped inside something called a replica set which allow us to control the number of pods available

# A replica set get wrapped inside a deployment & act as a load balancer in case of high load and allows us to rollback
  & roll forward with updates.

# conclusion: everything get wrapped up
              containers get wrapped up in pods
              pods get wrapped in replica set which controls the amount of pods
              replica sets get wrapped in a deployment (yaml file)
            
# what problems does kubernetes solve & its features ?
  demand for managing 100s of containers
  high availability (no downtime) & sclability (high peformance) 
  disaster recovery - does not lose any data (backup & restore)

# kubernetes basic architecture
  a master node connected to workers nodes where each node has a kubelet process running on it that makes communications 
  possible.
  each worker nodes has diff docker containers running on them (where the apps are running on)
  The master node has several kubenestes processes essential to run and manage the cluster properly
  e.g API server (UI, CLI, API), controller mnger (keeps tracks of whats happening),s cheduler (repsonsible for scheduling con
  tainers on each nodes based on available resources and the load), etcd (kubernetes backing store & hold current states of all nodes
  & containers) & a virtual network.
  

```

```
=== learning objectives ===

# created multi container pods with an ubuntu image & deployed it
# created a deployment using an httpd image, configured the networking to expose it to the outside world
  & checked all is working on a browser
# created a persistent volume (PV), persistent volume claim (PVC) & mounted it to a pod then deployed it.

```


```
==== useful commands ====

kubectl create -f <file-name>
kubectl get pods 
kubectl exec -it <pod-name> -- /bin/bash ==> exec into a container
kubectl log <pod-name>  
kubectl describe pod <pod-name>  

# creating a YAML file - useful for debugging - get any kubernetes objects & convert it into a yaml file 
kubectl get service
kubectl get service "service-name" -o yaml > "where-you-want-output-redirected".yaml 

# how to edit any kube objects on the fly 
e.g  kubectl get deployments 
     kubectl edit deployment <deployment-name>
     
# see CPU & mem usage
minikube addons enable metrics-server  ==> enable the metrics server
kubectl top pod ==> shows all your pods 
kubectl top pod <pod-name>
watch kubectl top pod ==> refreshes very 2secs 

# accessing the dashbaord
minikube dashboard


```
