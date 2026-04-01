# ArgoCD Laboriation

1. Skapa ett k8s-kluster.
2. Skapa ett namespace, och installera ArgoCD genom

```bash
kubectl create namespace argocd
kubectl apply --server-side -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

3. Kontrollera installationen genom

```bash
kubectl get pods -n argocd
```

4. Port-forward till ArgoCD-server

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

5. Skapa lösenord (O8-b8qu4scLz0U--) och logga in med 'admin'

```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

