We will leverage `oc` command to interact with the OpenShift cluster.
Let's download the `oc` tarball from the running cluster.
The command below will initialise the cluster with a known token to simplify the following steps.
`minikube start --wait=false`{{execute}}
`kubectl get nodes`{{execute}}
`kubeadm init --token=102952.1a7dd4cc8d1f4cc5 --kubernetes-version $(kubeadm version -o short)`{{execute}}


`sudo cp /etc/kubernetes/admin.conf $HOME/
sudo chown $(id -u):$(id -g) $HOME/admin.conf
export KUBECONFIG=$HOME/admin.conf`{{execute}}

`cat /opt/weave-kube.yaml`{{execute}}
`kubectl apply -f /opt/weave-kube.yaml`{{execute}}
`kubectl get pod -n kube-system`{{execute}}
`kubeadm token list`{{execute}}


`wget https://downloads-openshift-console.apps.test-ocp-ce4a.161.156.153.93.xip.io/amd64/linux/oc.tar --no-check-certificate`{{execute}}

Unpacking the tarball

`tar -xf oc.tar`{{execute}}

Updating the `PATH` variable

`export PATH=$PATH:$PWD`{{execute}}
