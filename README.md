# KillrVideo All-in-One Simplest Environment

The easiest way to setup & launch KillrVideo.com right at you place! Wnat to check how to work with Apache Cassandra or Datastax Enterprise? That's the right place to start!

## Setting up the Environment

You need to have docker and docker-compose installed in order to launch the application. Experience with docker is recommended but not required

```
> git clone git@github.com:KillrVideo/all-in-one.git killrvideo-all-in-one
> cd killrvideo-all-in-one
> docker-compose up -d
```
It'll take some time to pull the images and launch the application. After that, web interfaces should be available:

* http://localhost:3000 - KillrVideo Web Interface
* http://localhost:9091 - DataStax Studio 

If you use docker on mac/windows, docker-machine or similar setup, you may need to change localhost with the IP address of your docker machine.   
