# How to use?
- Run `sh helm_installation.sh` to install helm package.
- Check if helm is installed: `helm version`
- Run `helm env` to check helm status.
 # image

# How Helm connects to Kubernetes cluster?
```
Instead of using separate K8s commands for each K8s object, helm encloses K8s objects definition closely into a package called chart.
Later this chart is passed to Helm and then helm connects to K8s API to create K8s object.
```
- It connects to the Kubernetes cluster/host via the config file `~/.kube/config`

# Create first Chart
- helm create knoldusHelm
- tree myhelmchar
# Output Image

-  
