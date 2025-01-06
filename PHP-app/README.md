

## Kubernetes Configuration

This directory contains the Kubernetes configuration files for the simple PHP application. These files are used to deploy the application to a Kubernetes cluster.

### PHP Application Repository

The PHP application, that was dockerized, can be found in the following repository: [PHP Application Repository](https://github.com/makram89/PAI/tree/master/zadanie_5_PHP1)

### Files

- `php-1-deployment`: Defines the deployment for the PHP application.
- `php-1-service`: Defines the service to expose the PHP application.
- `ns.yml`: Defines the namespace for the PHP application.


### Deployment 

To deploy the PHP application to your Kubernetes cluster, use the following commands:

```sh
kubectl apply -f ./config
kubectl apply -f ./services
kubectl apply -f ./deployments
```


Ensure that your Kubernetes cluster is up and running before executing these commands. \
Example minikube cluster: [minikube cluster](../cluster/create-cluster.sh).

To access app site you might need to run 'tunnel':
```
minikube tunnel 
```


For more information, refer to the [main README](../README.md).