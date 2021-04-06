After pod is successfully running:
 Get $pod-name from below command
 `kubectl get po -n=jas`{{execute}}

The `kubectl exec` command allows you to remotely run commands inside an existing container of a pod.
 `kubectl exec -it $pod-name -n=jas -- /bin/sh`

After login to the container run sample example
`./run_example.sh`{{execute}}
