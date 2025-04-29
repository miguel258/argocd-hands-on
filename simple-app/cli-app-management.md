# Gestión de Aplicaciones con la CLI de ArgoCD

## **Obtener Información de las Aplicaciones con la CLI**
```bash
argocd app list
argocd app get demo
argocd app history demo
```

## **Borrar Aplicación con la CLI**
```bash
argocd app delete <<nombre-aplicacion>>
```

## **Crear Aplicación con la CLI**
```bash
argocd app create <<nombre-aplicacion>> \
--project default \
--repo <<ruta-acceso-repo>> \
--path "<<path>>" \
--dest-namespace default \
--dest-server https://kubernetes.default.svc
```
