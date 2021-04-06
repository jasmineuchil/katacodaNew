

Let's now deploy the sample application.

Cloning the repository

`git clone https://github.com/jasmineuchil/h2o_on_ocp`{{execute}}

This repository contains the service and deployment configuration files that can be used as-is on the OCP platform.

Change Directory

`cd $PWD/h2o_on_ocp/docker/`{{execute}}

Run a docker build:
 `docker build -t h2ojas:latest .`{{execute}}

Change Directory
`cd ../`{{execute}}

Deploy the application
`oc create -f h2o-service.yaml; oc create -f h2o-deployment.yaml; oc create -f node-deployment.yaml` {{execute}}

Check status of Pods

`oc get pods`{{execute}}

Assuming pods have successfully started,
The `oc rsh` command allows you to remotely run commands inside an existing container of a pod.
 `oc rsh $pod-name`

After login to the container run sample example
`./run_example.sh`{{execute}}
