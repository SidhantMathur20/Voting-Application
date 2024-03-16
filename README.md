# Voting Application

This application allows users to vote and view the voting percentage in real-time. It is built using Docker and orchestrated with Kubernetes to ensure scalability and high availability.

## Application Overview

The application is designed to capture votes and display the results in real-time. It is composed of several components, including a voting front-end, a Redis queue, a worker processing the votes, a Postgres database to store results, and a result display front-end.
<kbd>
<img width="1468" alt="Screenshot 2024-03-16 at 1 15 27 PM" src="https://github.com/SidhantMathur20/Voting-Application/assets/88873670/27c12696-ad4c-4b1c-bdcc-b386eb7bdf49">
</kbd>

### Application Architecture

The architecture is designed for scalability and fault tolerance, as illustrated below:
<kbd>
<img width="1442" alt="Screenshot 2024-03-16 at 1 18 22 PM" src="https://github.com/SidhantMathur20/Voting-Application/assets/88873670/389c9f47-6332-4f46-89fa-4fb883721d6b">
</kbd>

## Deployment Instructions

The application is containerized and deployed using Kubernetes. Follow these steps to deploy the application:

### Prerequisites

- Docker
- Kubernetes (Minikube or any Kubernetes cluster you have access to)
- kubectl (configured to interact with your Kubernetes cluster)

### Deployment Steps

1. **Create Deployments and Services**

   Deploy the application components using the following commands:

      ```shell
      kubectl create -f voting-app-deploy.yaml
      kubectl create -f voting-app-service.yaml
      kubectl create -f redis-deploy.yaml
      kubectl create -f redis-service.yaml
      kubectl create -f postgres-deploy.yaml
      kubectl create -f postgres-service.yaml
      kubectl create -f worker-app-deploy.yaml
      kubectl create -f result-app-deploy.yaml
      kubectl create -f result-app-service.yaml

These commands will set up all the necessary deployments and services for the application to function.

## Verify the Deployments

After deploying, check the status of the pods, services, and deployments:

     ```shell
      kubectl get pods,svc,deployment


## Access the Application

Retrieve URLs to access the voting and result services:

      ```shell
      minikube service voting-service --url
      minikube service result-service --url

## Scaling the Application

If needed, scale the voting application deployment to handle more traffic:

      ```shell
      kubectl scale deployment voting-app-deploy --replicas=3

## Clean Up

Once done, you can delete all the deployed components using the `kubectl delete` command, specifying the resources to delete.

## Additional Information

- Make sure to modify the YAML files according to your cluster setup and requirements.
- Ensure your Kubernetes cluster has sufficient resources to deploy all components of the application.
- Monitor the application and Kubernetes resources to ensure smooth operation.

