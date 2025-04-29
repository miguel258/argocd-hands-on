# Instalación y uso básico de ArgoCD

## **Instalar ArgoCD**
```bash
helm repo add argo https://argoproj.github.io/argo-helm
helm repo update
helm upgrade --install argocd argo/argo-cd --set-string configs.params."server\.disable\.auth"=true --version 7.1.1 --create-namespace -n argocd
```

## **Acceso a la Interfaz Web**
```bash
kubectl apply -f service.yml
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

## **Extraer Password Admin User**
```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```

## **Instalar ArgoCD CLI**
```bash
curl -sSL -o /usr/local/bin/argocd https://github.com/argoproj/argo-cd/releases/download/v2.11.2/argocd-linux-amd64
chmod +x /usr/local/bin/argocd
```

## **Comandos básicos de la CLI**
```bash
argocd help
argocd app list
argocd app get demo
argocd app history demo
argocd app sync demo
argocd app wait demo
```

## **Login con la CLI**
```bash
argocd login localhost:30443 --insecure
```
