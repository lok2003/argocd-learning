Create K8s cluster 

Check nodes 
```sh
kubectl get nodes 
kubectl get namespace 
```

Create Namespace for ArgoCD 
```sh
kubectl create namespace argocd
```

Verify
```sh
kubectl get namespace argocd 
```
```
NAME     STATUS   AGE
argocd   Active   31s
```

Install Argo CD
```sh
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

verify the pods 
```sh
kubectl get pods -n argocd 
```
Access the Argo CD UI 
```sh
kubectl port-forward svc/argocd-server -n argocd 8080:443
```
open the terminal and
```sh
https://localhost:8080
```

IN new terminal run this 
```sh
kubectl -n argocd get secret argocd-initial-admin-secret \
  -o jsonpath="{.data.password}" | base64 -d
```
you got password 
for user name `admin`
enter password 
sign in 



```sh
kubeclt get application -n argocd
```


```sh
kubectl describe application nginx-demo-2 -n argocd
```