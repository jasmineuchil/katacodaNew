Let's now deploy the sample application.

Cloning the repository

`git clone https://github.com/jasmineuchil/h2o_on_ocp`{{execute}}

This repository contains the service and deployment configuration files that can be used as-is on the  Kubernetes platform.

Change Directory

`cd $PWD/h2o_on_ocp/docker/`{{execute}}

Run a docker build:
 `docker build -t h2o:latest .`{{execute}}
Tag, Push and pull image:
`docker login`{{execute}}
`docker images | grep h2ojas`{{execute}}
`docker tag $tag_number jasmi111/h2ojas`{{execute}}
`docker push jasmi111/h2ojas`{{execute}}
`docker pull jasmi111/h2ojas`{{execute}}

Change Directory
`cd ../`{{execute}}

Create a new Project
`kubectl create namespace jas`{{execute}}

Deploy the application
 `kubectl create -f h2o-service.yaml --validate=false --namespace=jas
 kubectl create -f h2o-deployment.yaml --validate=false --namespace=jas`{{execute HOST1}}


Check status of Pods
`kubectl get po -n=jas`{{execute}}
