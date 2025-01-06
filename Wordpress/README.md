## WordPress
For more information, refer to the [main README](../README.md).

This folder contains the configuration and deployment files for the basic Wordpress project. It can use Wordpress official or custom docker  images.  \
Ex. from this repo: [My Wordpress docker and compose project](https://github.com/makram89/Wordpress_demo)
 <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" alt="docker" width="20" height="20"/> </a> <a href="https://flutter.dev" target="_blank" rel="noreferrer"> 


### Directory Structure

- `config/`: Contains the ConfigMap for WordPress configuration.
  - [`configmapa.yml`](config/configmapa.yml): Defines environment variables for WordPress and MySQL.
- `deployments/`: Contains the deployment configurations for WordPress and MySQL.
  - [`wordpress-deployment.yaml`](deployments/wordpress-deployment.yaml): Deployment configuration for WordPress.
  - [`mysql-deployment.yaml`](deployments/mysql-deployment.yaml): Deployment configuration for MySQL.
- `ns/`: Contains the namespace configuration.
  - [`ns.yml`](ns/ns.yml): Defines the `wordpress` namespace.
- `secret/`: Contains the secret configuration.
  - [`secret.yml`](secret/secret.yml): Defines the MySQL password secret.
- `services/`: Contains the service configurations for WordPress and MySQL.
  - [`wordpress-service.yml`](services/wordpress-service.yml): Service configuration for WordPress.
  - [`mssql-service.yml`](services/mssql-service.yml): Service configuration for MySQL.
- `storage/`: Contains the storage configurations for WordPress and MySQL.
  - [`wp-storage.yaml`](storage/wp-storage.yaml): PersistentVolume and PersistentVolumeClaim for WordPress.
  - [`mssq-storage.yaml`](storage/mssq-storage.yaml): PersistentVolume and PersistentVolumeClaim for MySQL.

### Deployment Instructions

Ensure that your Kubernetes cluster is up and running before executing these commands. \
Example minikube cluster: [minikube cluster](../cluster/create-cluster.sh).

To access Wordpress site you might need to run 'tunnel':
```
minikube tunnel 
```

To deploy WordPress, use the following commands:

```sh
kubectl apply -f ./ns
kubectl apply -f ./storage
kubectl apply -f ./secret
kubectl apply -f ./config
kubectl apply -f ./services
kubectl apply -f ./deployments
```


