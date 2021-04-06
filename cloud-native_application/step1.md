

We will leverage oc command to interact with the OpenShift cluster. Let's download the oc tarball from the running cluster.

`wget https://downloads-openshift-console.apps.test-ocp-ce4a.161.156.153.93.xip.io/amd64/linux/oc.tar --no-check-certificate`{{execute}}

Unpacking the tarball

`tar -xf oc.tar`{{execute}}

Updating the PATH variable

`export PATH=$PATH:$PWD`{{execute}}
