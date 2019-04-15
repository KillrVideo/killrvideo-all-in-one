# KillrVideo All-in-One Simplest Environment

The easiest way to setup and launch KillrVideo - using Docker on your own machine! Want to learn how to work with Apache Cassandra or Datastax Enterprise? This is the right place to start!

## Docker-Compose Setup

You need to have Docker and docker-compose installed in order to launch the application. Experience with Docker is recommended but not required.

```
git clone git@github.com:KillrVideo/all-in-one.git killrvideo-all-in-one
cd killrvideo-all-in-one
docker-compose up -d
```
It'll take some time to pull the images and launch the application. After that, these web interfaces should be available:

* http://localhost:3000 - KillrVideo Web Interface
* http://localhost:9091 - DataStax Studio 

If you use Docker on mac/windows, docker-machine or similar setup, you may need to replace 'localhost' with the IP address of your docker machine.

## Kubernetes Setup

The files located in ./k8s folder are resource definitions for Kubernetes. They are **generated automatically** using [Kompose](https://github.com/kubernetes/kompose). If you change the docker-compose.yaml file and want to rebuild the Kubernetes definitions, you can update the files with the following command (you need to have Kompose installed)

```
kompose convert -o ./k8s/
```

Running KillrVideo using Kubernetes is simple as:

```
git clone git@github.com:KillrVideo/all-in-one.git killrvideo-all-in-one
cd killrvideo-all-in-one/k8s
kubectl apply -f .
```
Of course, you need to have a Kubernetes cluster configured and available. For the local development purposes we suggest [Minikube](https://kubernetes.io/docs/setup/minikube/).
