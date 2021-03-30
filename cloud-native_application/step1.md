

`kubeadm init --token=102952.1a7dd4cc8d1f4cc5 --kubernetes-version $(kubeadm version -o short)`{{execute}}


`sudo cp /etc/kubernetes/admin.conf $HOME/
sudo chown $(id -u):$(id -g) $HOME/admin.conf
export KUBECONFIG=$HOME/admin.conf`{{execute}}
`curl https://docs.projectcalico.org/manifests/calico.yaml -O`{{execute}}
`kubectl apply -f calico.yaml`{{execute}}

`kubectl get pod -n kube-system`{{execute}}
`kubeadm token list`{{execute}}
`kubeadm join --discovery-token-unsafe-skip-ca-verification --token=102952.1a7dd4cc8d1f4cc5 [[HOST_IP]]:6443`{{execute HOST2}}

`kubectl get nodes`{{execute}}
