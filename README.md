# How to use?
- Run `sh helm_installation.sh` to install helm package.
- Check if helm is installed: `helm version`
- Run `helm env` to check helm status.
![image](https://user-images.githubusercontent.com/76727343/209653191-42be1e5c-3aa9-445a-9762-079947d00169.png)

# How Helm connects to Kubernetes cluster?

- Instead of using separate K8s commands for each K8s object, helm encloses K8s objects definition closely into a package called chart.
- Later this chart is passed to Helm and then helm connects to K8s API to create K8s object.
- It connects to the Kubernetes cluster/host via the config file `~/.kube/config`

# Create first Chart
- `helm create knoldusHelm`
- `tree knoldusHelm`
![image](https://user-images.githubusercontent.com/76727343/209653328-4384fd40-c119-498d-b994-6ee7c647c1f5.png)


- Delete everything from templates directory to start afresh: `rm -rf knoldusHelm/templates/`
- create new deployement file `templates/nginx.yml`
- deploy the deployment `kubectl create deployment nginx --image=nginx`
- Expose the deployment `kubectl expose deploy nginx --port 80 --type NodePort --dry-run=client -o yaml >> knoldusHelm/templates/service.yaml`
- Create a file at `templates/NOTES.txt` which keeps metadata about Helm.
- Delete deployment `kubectl delete deploy nginx`

# Deploying first helm chart
- `helm lint knoldusHelm`
- `helm install demochart ./knoldusHelm --dry-run`
- `helm install demochart ./knoldusHelm`
- Verify using `helm list`
- To Uninstall `helm uninstall demochart`
.
.
.
.
.
NOTE: This repo is a work in Progress.
