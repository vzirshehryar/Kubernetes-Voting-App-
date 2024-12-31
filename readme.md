Kubernetes Basic Commands to make Pods, Services, ReplicaSets and Deployment declaratively using yaml files.

For running example files
PODS:
Run: kubectl get pods
Run: kubectl create -f pod-defination-example.yaml  
 // it will create pod of name myapp-pod-nginx with a container running nginx image.
Run: kubectl describe pod myapp-pod-nginx
// it will give you info about this pod

REPLICASETS:
Run: kubectl get replicasets
Run: kubectl create -f replicaset-defination-example.yaml
// it will create a replicaset with 4 pods having container running nginx image.
Run: kubectl describe replicaset new-replica-set
// it will give you info about this replicaSet

DEPLOYMENT:
Run: kubectl get deployment
Run: kubectl create -f deployment-defination-example.yaml
// it will create a deployment with 3 pods having container running nginx image.
Run: kubectl describe deployment my-deployment
// it will give you info about this deployment

SERVICES (ClusterIP):
Run: kubectl get services
Run: kubectl create -f service-defination-clusterip-example.yaml
// it will create a ClusterIP service for label "app:my-redis-service" on port 6379.
Run: kubectl describe services my-service-cluserIp
// it will give you info about this services

SERVICES (NodePort):
Run: kubectl get services
Run: kubectl create -f service-defination-nodeport-example.yaml
// it will create a NodePort service for label "app:my-redis-service" on port 80 (internal or container port) and 30080 (exteranl or node port).
Run: kubectl describe services my-service-nodeport
// it will give you info about this services

For Running Voting App in Kubernetes
You have two options for that: Either using deployment (using-deployment) or using pods only (using-simple-pods)

For using-simple-pods:
go to the folder (using-simple-pods) and create the pods using the command as above for each yaml file which is : kubectl create -f <yaml-file-name>
and create the service just like above.

For using-deployment:
go to the folder (using-deployment) and create the deployments using the command as above for each yaml file which is : kubectl create -f <yaml-file-name>
and create the service just like above.

Then run the following commands in the two separate terminal:
Run: minikube service voting-service --url
// it will return a url and this will be your voting page

Run: minikube service result-service --url
// it will return a url and this will be your result page
