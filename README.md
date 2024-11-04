# argo-cd
Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes.

Argo CD is implemented as a Kubernetes controller which continuously monitors running applications and compares the current, live state against the desired target state (as specified in the Git repo). A deployed application whose live state deviates from the target state is considered OutOfSync. Argo CD reports & visualizes the differences, while providing facilities to automatically or manually sync the live state back to the desired target state. Any modifications made to the desired target state in the Git repo can be automatically applied and reflected in the specified target environments.

1. [install minikube](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download)

2. [Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)

3. [argo cd getting started](https://argo-cd.readthedocs.io/en/stable/getting_started/)

## Useful commands to access argocd UI
- kubectl get ns
- kubectl -n argocd get all
- k -n argocd get svc
- k -n argocd edit svc argocd-server #change the ClusterIP to NodePort
- minikube ip # to get the minikube ip then access the argocd server through the browser 
- k get secret -n argocd
- k -n argocd get secrets argocd-initial-admin-secret -o json
- k -n argocd get secrets argocd-initial-admin-secret -o json | jq .data.password -r | base64 -d # decode the password

## Argo cd cli install
- wget https://github.com/argoproj/argo-cd/releases/download/v2.12.6/argocd-linux-amd64
- mv argocd-linux-amd64 argocd
- sudo mv  argocd /usr/local/bin/
- argocd
- argocd login argocd-server-ip:port # input username and password