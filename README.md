# Kubernetes with WordPress

## Description
This project demonstrates how to deploy a WordPress application using Kubernetes. It includes the setup of MySQL as the database and WordPress running in a containerized environment.

## Technologies Used
- Kubernetes
- WordPress
- MySQL
- Docker
- Minikube (for local Kubernetes development)

## Setup

### Prerequisites
Before running this project, make sure you have the following installed:
- [Kubernetes](https://kubernetes.io/docs/setup/)
- [Minikube](https://minikube.sigs.k8s.io/docs/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- [Docker](https://www.docker.com/get-started)

### Steps to Run Locally

1. **Start Minikube**:
   ```bash
   minikube start

2. **Create a namespace named wordpress**
   ```bash
   kubectl create namespace wordpress


3. **Clone the repository**:
   ```bash
   git clone https://github.com/Kobby-Jones/kubernetes-wordpress.git

   cd kubernetes-wordpress
4. **Run the following command to deploy MySql and Wordpress**
   ```bash
   kubectl apply -f -n wordpress mysql_pvc.yml

   kubectl apply -f -n wordpress mysql_deployment.yml

   kubectl apply -f -n wordpress mysql_service.yml

   kubectl apply -f -n wordpress wordpress_pvc.yml

   kubectl apply -f -n wordpress wordpress_deployment.yml

   kubectl apply -f -n wordpress wordpress_service.yml

5. **Check the status of pods**:
   ```bash
   kubectl get pods -n wordpress

6. **Verify that the status for both mysql and wordpress are running**
    ***You will see something like this***:
    ```bash
    NAME                         READY   STATUS    RESTARTS        AGE
    mysql-5db58bff64-sq8tm       1/1     Running   1 (20s ago)     30s
    wordpress-7c94565459-4nmxt   1/1     Running   0               20s

7. **You can now visit your wordpress page using by running the following command in the terminal
   ```bash
   minikube service wordpress -n wordpress
8. **A new browser tab will be open and will take you to your wordpress page**

