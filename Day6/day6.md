# Cluster
Kubernetes will manage the application in a cluster

What is cluster??

It is a group of nodes; it contains a master node and a worker node.

# The master node
it is the hero of the cluster which is going to take care of the cluster head
is responsible for the overall health of the cluster
we hav 4 components in master node ,
API server - it is a hero of the server , whenever u want to perform load balancing,auto-scaling it plays a crucial role.
ETCD - it is a distributed DB where ur going to store all the details abt the cluster, application info inside the etcd
controlller - n is responsible for monitoring health of the application , it is always checked desired status = actual status
scheduler - it is component which is going to schedule a pod in a node.

**NOTE:** pod - in k8s , it will run the application in a pod, which contains containers, which containers docker image, it is the smallest deployable unit in the kubernetes.
The worker node
it is where u deploy a server running on the cluster

worker node components:

kubelet - this components exists inside worker node, it is responsible for creating pods, which is going to act as agent, if something goes wrong then it communicates to the master node.
Container runtime - it is like a docker, it is responible for pulling the docker image, creating container, starting the container, it is responsible for managing the container lifecycle.
kube-proxy - it is a networking component in the worker node, it is responsible for creating deployments, exposing application over the internet
in a cluster we should atleast 1 master node and worker node.

there are 2 types :

on premises - we hav to manage this cluster by ourselves, if something goess wrong in application downtime , we r responsible for that

cloud manage clusters - this cluster is managed by the cloud providers , if something goess wrong , they are responsible for our application

in aws , if u want to create a cluster , we hav a service called EKS (elastic kubernetes service)

in putty:

snap install kubectl --classic

aws eks update-kubeconfig --name sameeksha-cluster --region ap-south-1

kubectl get nodes (to get list of nodes)(there should be 3 since we mentioned earlier as 3)

when u create pod file , 4 things are imp:

API version - defines the schema representation of the object
kind - defines what kind of object u are creating
Meta-data - defines name of the object (if u want to assign labels we need to define meta data)
spec - defines behaviour of the object
1 cpu = 100 milliqoates 1gb = 1024 megabytes

in vscode :

create a folder called sameeksha-k8s-maifests
create pod.yaml and write code
open terminal and enter " git add . ; git commit -m "my first yaml file" " and publish as public
in putty:

* git clone-https://github.com/Sinchan08/sinchana-k8s-manifests.git
* ls
* cd sinchana-k8s-manifests
* kubectl apply -f pod.yaml
* kubectl get pods
* kubectl get pods -o wide
* kubectl describe pod sample-pod
# new class:
-in putty:

* sudo su
* kubectl get nodes
  ![429854479-e8b86a6e-1d59-4bbc-9088-615fde1f8d1c](https://github.com/user-attachments/assets/bf5c5f89-7cf7-43af-8c4b-b0bee59175dd)

* kubectl get namespace
* kubectl get all -n kube-system
* kubectl create ns sinchana-ns
* kubectl get ns
* kubectl get pods
* kubectl run test-pod --image ngnix --port 80 -n sameeksha-ns (to create pod)
* kubectl get pods (doesnt give ut pod name)
* get pods -n sinchana-ns (so enter this)
kubectl delete pod test-pod -n sinchana-ns (if the pod goes down the n we face 3 problems)
* problem 1: we ll get application down time - to overcome this we hav to attach controllers to the pod
every pod has own IP address , if pod goes down , the ip address will change - to overcome this we hav have to create services in kuberntes (it will create static URL)
if pod goes down, along with the pod, we will loose the data - to overome this, we hav to implement volumes in k8s
Replica set: it is a k8s object, it is going to maintain minimum number of nodes 24 x 7 ( replica set is always desire state == actual state)
  # namespace:

 Dividing cluster into an isolated environment, when we have multiple teams and projects, we use the concept of namespace default - it is created automatically in k8s, to create a resource with default namespace kube-node-lease - to check the health of the node, kubernetes master node use this objects kube-public - anyone can access resources in this namespace

the time of cluster creation by default all the resources such metric server, core DNS .. all the resources are created in this ( kube-system )

note : when u deploing application production server, we ll never deploy any application with default namespace

in vscode:

replica set problmes in real time application ,we dont recommend use of replica set, because we cant able to perform rollout, rollback operations -deployments? -in k8s , we deploy applications using deployment controllers; deployment will manage the replica set. The replica set will manage the pod

if u want to expose application through web browser, k8s will execute 3 services we have:

cluster ip service
2 node pod service
load balancer service
we r going to implement load balancer services

SRE job

MONITORING:

to understand whats going inside the application, we r implementing monitoring dashboard, whith the help of these we can recognise if something goes wrong in the application and also we are able to identify how much CPU, memory consuming podes, nodes, cluster heads -- can be identified

monitoring tools like promethus , graphana

promethus is a metrix server where it is going to collect times series od data tstb , it sends data to graphana dashboards

grafana , with help of this, we can setup monitoring dashboards, where we can see ur data in the form of pycharts or graphs

ansebl is a configuration management tool,
