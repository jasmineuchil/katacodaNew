Kubeadm has been installed on the nodes. The first stage of initialising the cluster is to launch the master node.

The command below will initialise the cluster with a known token to simplify the following steps.
`kubeadm init --token=102952.1a7dd4cc8d1f4cc5 --kubernetes-version $(kubeadm version -o short)`{{execute}}

The command copies the configuration to the users home directory and sets the environment variable for use with the CLI.
`sudo cp /etc/kubernetes/admin.conf $HOME/
sudo chown $(id -u):$(id -g) $HOME/admin.conf
export KUBECONFIG=$HOME/admin.conf`{{execute}}

Run kubectl apply -f [podnetwork].yaml with one of the options listed at https://kubernetes.io/docs/concepts/cluster-administration/addons/

`curl https://docs.projectcalico.org/manifests/calico.yaml -O`{{execute}}
`kubectl apply -f calico.yaml`{{execute}}


On the second node, run the command to join the cluster providing the IP address of the Master node.
`kubeadm join --discovery-token-unsafe-skip-ca-verification --token=102952.1a7dd4cc8d1f4cc5 [[HOST_IP]]:6443`{{execute HOST2}}

The command below will return the two nodes in our cluster.
`kubectl get nodes`{{execute}}
