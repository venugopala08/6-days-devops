# Problem with the Container:
containers will not support the auto-screening

- scale up - whenever profit increase, we hav to increase the number of servers
     Vertical scaling - u have to increase the system resources
     - horizontal auto-scaling  - we hav to add additional server to existing infrastructure

- scale down - whenever traffic goes down, we have to  remove the additional servers
             - containers will not support load balancing
             - If the container is down, we are going to get application downtime, so we have to go with containers
             - containers will not support the self-healing process.
 To overcome the problems, we are moving towards a war orchestration tool
What is Kubernetes??

* Kubernetes is a container management tool; it is going to manage all the containers
* Kubernetes performs the automatic deployment of the application

# Kubernetes features:

* orchestration
* auto-scaling
* load balancing
* self healing
* It is platform-independent - it can run on any cloud
* To perform the automation kubernetes, we write a manifested (aml) file
1.Create a jump server or bastion host (create instance using ubuntu) (sameeksha-bastianhost)

2.We have to install EKSCTL, Kubectl, AWS CLI.sh

vi cluster.sh (in putty) and right click (if not enter I and right click ) and enter

* esc and enter :wq

* chmod 777 cluster.sh

* sh cluster.sh

* sudo su

* ls

* sh cluster.sh (long package download) (output: cluster.sh: 42: source: not found)

* now in aws --> search for IAM and select users from the sidebar --> create user --> sinchana-k8s -->next -->3rd block & 2nd option administrativeaccess --> create user --> cliateck on sinchana-k8s -->security credential --> create access key -->user key - keep it blank --> next and download csv file


# in putty:

* eksctl

* clear

eksctl create cluster --name sameeksha-cluster --version 1.31 --region ap-south-1 --nodegroup-name test-linux --node-type t2.micro --nodes 3 --nodes-min 3 --nodes-max 5 --managed (to create cluster)
 
![429426730-a757acfc-6553-4bc3-a028-1eec04b04051](https://github.com/user-attachments/assets/a83d136c-fe4c-4c35-b172-004ea215e051)

# Cluster

Kubernetes will manage the application in a cluster

What is cluster??

It is a group of nodes; it contains a master node and a worker node.

The master node
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

aws eks update-kubeconfig --name sinchana-cluster --region ap-south-1

kubectl get nodes (to get list of nodes)(there should be 3 since we mentioned earlier as 3)

when u create pod file , 4 things are imp:

API version - defines the schema representation of the object
kind - defines what kind of object u are creating
Meta-data - defines name of the object (if u want to assign labels we need to define meta data)
spec - defines behaviour of the object
1 cpu = 100 milliqoates 1gb = 1024 megabytes

in vscode :

create a folder called sinchana-k8s-maifests
create pod.yaml and write code
open terminal and enter " git add . ; git commit -m "my first yaml file" " and publish as public
in putty:

ls
cd sinchana-k8s-manifests
kubectl apply -f pod.yaml
kubectl get pods
kubectl get pods -o wide
kubectl describe pod sample-pod
new class:
in putty:

sudo su
kubectl get nodes

# namespace:
Dividing cluster into an isolated environment, when we have multiple teams and projects, we use the concept of namespace default - it is created automatically in k8s, to create a resource with default namespace kube-node-lease - to check the health of the node, kubernetes master node use this objects kube-public - anyone can access resources in this namespace

the time of cluster creation by default all the resources such metric server, core DNS .. all the resources are created in this ( kube-system )

note : when u deploing application production server, we ll never deploy any application with default namespace

in vscode:

image

now in putty:

ls

cd sinchana-k8s-manifests

git pull

kubectl apply -f rs.yaml

MONITORING:

to understand whats going inside the application, we r implementing monitoring dashboard, whith the help of these we can recognise if something goes wrong in the application and also we are able to identify how much CPU, memory consuming podes, nodes, cluster heads -- can be identified

monitoring tools like promethus , graphana

promethus is a metrix server where it is going to collect times series od data tstb , it sends data to graphana dashboards

grafana , with help of this, we can setup monitoring dashboards, where we can see ur data in the form of pycharts or graphs

ansebl is a configuration management tool,

