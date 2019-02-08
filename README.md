# KillrVideo All-in-One Simplest Environment

The easiest way to setup & launch KillrVideo.com right at you place! Want to learn how to work with Apache Cassandra or Datastax Enterprise? That's the right place to start!

## Setting up the Environment

You need to have docker and docker-compose installed in order to launch the application. Experience with docker is recommended but not required.

```
git clone git@github.com:KillrVideo/all-in-one.git killrvideo-all-in-one
cd killrvideo-all-in-one
docker-compose up -d
```
It'll take some time to pull the images and launch the application. After that, web interfaces should be available:

* http://localhost:3000 - KillrVideo Web Interface
* http://localhost:9091 - DataStax Studio 

If you use docker on mac/windows, docker-machine or similar setup, you may need to change localhost with the IP address of your docker machine.

## Kubernetes Setup

The files located in ./k8s folder are resource definitions for kubernetes. They are **generated automatically** using [Kompose](https://github.com/kubernetes/kompose) tool. If you applied any changes to docker-compose.yaml file and want to rebuild kubernetes definitions, you can update the files with the following command (you need to have Kompose installed)

```
kompose convert -o ./k8s/
```

Running KillrVideo using kubernetes is simple as that:

```
git clone git@github.com:KillrVideo/all-in-one.git killrvideo-all-in-one
cd killrvideo-all-in-one/k8s
kubectl apply -f .
```
Of course, you need to have a kubernetes cluster configured and available. For the local development purposes we suggest to use [Minikube](https://kubernetes.io/docs/setup/minikube/).
