# React App Kubernetes Configuration

This repository contains the Kubernetes configuration files for deploying the simple React application.

## React Application Repository

The source code for the React application, which was dockerized by me, can be found in the following repository:
[React App Repository](https://github.com/makram89/PAI/tree/master/zadanie_10_react)

## Deployment Instructions

```sh
kubectl apply -f ./config
kubectl apply -f ./services
kubectl apply -f ./deployments
```


Ensure that your Kubernetes cluster is up and running before executing these commands. \
Example minikube cluster: [minikube cluster](../cluster/create-cluster.sh).

To access Wordpress site you might need to run 'tunnel':
```
minikube tunnel 
```
