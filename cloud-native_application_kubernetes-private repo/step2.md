Let's now deploy the sample application.

Cloning the repository

`git clone https://github.com/jasmineuchil/h2o_on_ocp`{{execute}}

This repository contains the service and deployment configuration files that can be used as-is on the  Kubernetes platform.


Before starting, Please get a license key for accessing H2O platform. Sign up https://www.h2o.ai/try-driverless-ai/ now.
Check your mail for license key and now replace the license key.
`vi $PWD/h2o_on_ocp/docker/experiment/license.sig`{{execute}}


Change Directory

`cd $PWD/h2o_on_ocp/docker/`{{execute}}

Run a docker build:
 `docker build -t h2ojas:latest .`{{execute}}

Change Directory
`cd ../`{{execute}}

Create a new Project
`kubectl create namespace jas`{{execute}}

Deploy the application
 `kubectl create -f h2o-service.yaml --validate=false --namespace=jas
 kubectl create -f h2o-deployment.yaml --validate=false --namespace=jas`{{execute HOST1}}


Check status of Pods
`kubectl get po -n=jas`{{execute}}
