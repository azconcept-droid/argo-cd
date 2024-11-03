# argo-cd

1. [install minikube](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download)

2. [Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)

Useful commands
kubectl get ns
kubectl -n argocd get all
k -n argocd get svc
k -n argocd edit svc argocd-server #change the ClusterIP to NodePort
minikube ip # to get the minikube ip then access the argocd server through the browser 
k get secret -n argocd
k -n argocd get secrets argocd-initial-admin-secret -o json
k -n argocd get secrets argocd-initial-admin-secret -o json | jq .data.password -r | base64 -d # decode the password