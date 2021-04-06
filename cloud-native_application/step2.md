

Access OpenShift Container Platform ( setup on IBM PowerVS - IBM Cloud ) WebConsole URL - authenticate with your Public GitHub ID

Click on https://console-openshift-console.apps.test-ocp-ce4a.161.156.153.93.xip.io to access OpenShift Container Platform WebConsole URL.

Click on authentication mechanism as github --> Allow your GitHub handle to authenticate ( grant permissions ) to this OpenShift Cluster.

Copy Login Command --> Display Token --> Copy the token

NOTE - Port is 6443. So it will look like this -

oc login --token=<UPDATE> --server=https://api.test-ocp-ce4a.161.156.153.93.xip.io:6443 --insecure-skip-tls-verify=true
