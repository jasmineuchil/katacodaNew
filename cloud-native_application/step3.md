Let's now deploy the sample application.

Cloning the repository

`git clone https://github.com/jasmineuchil/h2o_on_ocp`{{execute}}

This repository contains the service and deployment configuration files that can be used as-is on the  Kubernetes platform.

Change Directory

`cd $PWD/h2o_on_ocp/docker/`{{execute}}

Run a docker build:
 `docker build -t h2o:latest .`{{execute}}

Chane Directory
`cd ../`{{execute}}

Create a new Project
`kubectl create namespace jas
 kubectl create -f h2o-service.yaml --validate=false --namespace=jas
 kubectl create -f h2o-deployment.yaml --validate=false --namespace=jas`{{execute HOST1}}

`oc new-project jasm`{{execute}}
`oc project jasm`{{execute}}

Deploy the application


Check status of Pods


Assuming pods have successfully started, let us now expose the application services outside cluster via
