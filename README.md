echo "# Kubernetes Task 5" >> README.md
echo "This project contains Kubernetes manifests for deployment, service, PV, PVC, and pod-based tasks." >> README.md

git add README.md
git commit -m "Added README"
git push


PROJECT TITILE-"KUBERNETES-TASK.5-DEPLOYMENT+SERVICE"
PROJECT DESRIPTION-This project demonstrates how to deploy a sample application on a Kubernetes cluster using K3s.  
It includes creating a Deployment and exposing it using a NodePort Service.
TECHNOLOGIES USED - - Kubernetes (K3s)
- YAML Manifests
- EC2 Ubuntu Instance
- GitHub

HOW TO APPLY THE DEPLOYMENT-
 kubectl apply -f deployment.yaml
 kubectl apply -f service.yaml

 VERIFYING RESOURCES
   kubectl get pods 
   kubectl get deployment 
   kubectl get svc

   TESTING THE DEPLOYMENT-SERVICE ON LOCAL MACHINE
   (from terminal ubuntu)-CURL http://localhost:30080
   http://44.200.107.201:30080/

     interview questions
     1. What is Kubernetes?

Kubernetes is an open-source container orchestration platform that automates deployment, scaling, and management of containerized applications.

2. What is the role of kubelet?

The kubelet is an agent that runs on every worker node.
Its job is to:

Communicate with the control plane

Make sure containers in a pod are running

Start/stop containers as required

3. Explain pods, deployments, and services.
Pod

Smallest unit in Kubernetes

Contains one or more containers

Temporary (ephemeral)

Deployment

Manages multiple pods

Ensures desired replica count

Supports rolling updates & rollback

Service

Provides stable networking for pods

Exposes pods internally or externally

4. How do you scale in Kubernetes?

Using the kubectl scale command:

kubectl scale deployment myapp --replicas=5


Or using Horizontal Pod Autoscaler (HPA).

5. What is a namespace?

A namespace is a way to divide cluster resources logically.
Used for:

Isolation

Organizing projects/teams

Avoiding naming conflicts

6. Difference between ClusterIP, NodePort, LoadBalancer.
Type	Description	Access
ClusterIP	Default, internal service	Inside cluster only
NodePort	Opens a port on every node	NodeIP:NodePort
LoadBalancer	Uses cloud provider LB	Public internet
7. What are ConfigMaps?

ConfigMaps store non-secret configuration data (key-value pairs) that can be injected into pods as:

Environment variables

Command-line args

Config files

8. How do you perform rolling updates?

You can update a deployment without downtime:

kubectl set image deployment/myapp myapp=nginx:1.19


Check status:

kubectl rollout status deployment/myapp
   
