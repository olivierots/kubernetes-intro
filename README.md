# kubernetes-intro
```
Docker & kubernetes goes hand in hand
Docker is used as the container runtime and kubernestes as the platform to deploy the images
Kubernetes is a wrapper for Docker, from Docker side of things, docker images are used which then become containers

Inside a pod there is one or more containers
A pod get wrapped inside something called a replica set which allow us to control the number of pods available

A replica set get wrapped inside a deployment & act as a load balancer in case of high load and allows us to rollback
& roll forward with updates.

conclusion: everything get wrapped up
            containers get wrapped up in pods
            pods get wrapped in replica set which controls the amount of pods
            replica sets get wrapped in a deployment (yaml file)
```            

```
### useful comands ###
kubectl create -f <>
kubectl get pods 
kubectl exec -it <pod-name> -- /bin/bash ==> exec into a container
kubectl log <pod-name>  
kubectl describe pod <pod-name>  

# creating a YAML file - useful for debugging 
kubectl get service
kubectl get service "service-name" -o yaml > "service-name".yaml 

# how to edit any kube objects on the fly 
e.g  kubectl get deployments 
     kubectl edit deployment <deployment-name>
  
```
