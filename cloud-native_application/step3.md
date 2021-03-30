After pod is successfully running:
 Get pods name
 `kubectl get po -n=jas`{{execute}}

 Then execute it
 `kubectl exec -it $pod-name -n=jas -- /bin/sh`

Then run
`./example.sh`{{execute}}
