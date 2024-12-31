# Kubernetes Basic Commands and Examples

## Pods
**Commands to manage Pods using declarative YAML files:**

1. View all Pods:
   ```bash
   kubectl get pods
   ```
2. Create a Pod:
   ```bash
   kubectl create -f pod-definition-example.yaml
   ```
   *Creates a Pod named `myapp-pod-nginx` with a container running the `nginx` image.*

3. Describe a Pod:
   ```bash
   kubectl describe pod myapp-pod-nginx
   ```
   *Provides detailed information about the Pod.*

---

## ReplicaSets
**Commands to manage ReplicaSets using declarative YAML files:**

1. View all ReplicaSets:
   ```bash
   kubectl get replicasets
   ```
2. Create a ReplicaSet:
   ```bash
   kubectl create -f replicaset-definition-example.yaml
   ```
   *Creates a ReplicaSet named `new-replica-set` with 4 Pods, each running the `nginx` container.*

3. Describe a ReplicaSet:
   ```bash
   kubectl describe replicaset new-replica-set
   ```
   *Provides detailed information about the ReplicaSet.*

---

## Deployments
**Commands to manage Deployments using declarative YAML files:**

1. View all Deployments:
   ```bash
   kubectl get deployment
   ```
2. Create a Deployment:
   ```bash
   kubectl create -f deployment-definition-example.yaml
   ```
   *Creates a Deployment named `my-deployment` with 3 Pods, each running the `nginx` container.*

3. Describe a Deployment:
   ```bash
   kubectl describe deployment my-deployment
   ```
   *Provides detailed information about the Deployment.*

---

## Services
### ClusterIP Service
**Commands to manage ClusterIP Services:**

1. View all Services:
   ```bash
   kubectl get services
   ```
2. Create a ClusterIP Service:
   ```bash
   kubectl create -f service-definition-clusterip-example.yaml
   ```
   *Creates a ClusterIP Service named `my-service-clusterIp` for label `app:my-redis-service` on port `6379`.*

3. Describe a ClusterIP Service:
   ```bash
   kubectl describe services my-service-clusterIp
   ```
   *Provides detailed information about the Service.*

### NodePort Service
**Commands to manage NodePort Services:**

1. View all Services:
   ```bash
   kubectl get services
   ```
2. Create a NodePort Service:
   ```bash
   kubectl create -f service-definition-nodeport-example.yaml
   ```
   *Creates a NodePort Service named `my-service-nodeport` for label `app:my-redis-service`, exposing port `80` internally and port `30080` externally.*

3. Describe a NodePort Service:
   ```bash
   kubectl describe services my-service-nodeport
   ```
   *Provides detailed information about the Service.*

---

# Running the Voting App on Kubernetes

## Overview
You can deploy the Voting App using either of the following approaches:

### 1. **Using Simple Pods**

1. Navigate to the `using-simple-pods` folder.
2. Create Pods for each YAML file:
   ```bash
   kubectl create -f <yaml-file-name>
   ```
3. Create the Services of the yaml files as described above.

### 2. **Using Deployments**

1. Navigate to the `using-deployment` folder.
2. Create Deployments for each YAML file:
   ```bash
   kubectl create -f <yaml-file-name>
   ```
3. Create the Services of the yaml files as described above.

---

## Access the Voting App

Run the following commands in two separate terminals:

1. For the Voting Page:
   ```bash
   minikube service voting-service --url
   ```
   *Returns a URL to access the voting page.*

2. For the Result Page:
   ```bash
   minikube service result-service --url
   ```
   *Returns a URL to access the result page.*
