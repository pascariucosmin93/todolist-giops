# todolist-giops

GitOps repository for the Todo application Kubernetes manifests.
Image tags are updated automatically by the CI pipeline in the main `todolist` repo.

ArgoCD should target:

- repo: `git@github.com:pascariucosmin93/todolist-giops.git`
- path: `k8s/chart`

Authentik can be deployed as a separate ArgoCD application using:

- Helm repo: `https://charts.goauthentik.io`
- values file from this repo: `authentik/values.yaml`

Required Kubernetes secrets:

- `todolist-postgres`
  Keys: `POSTGRES_DB`, `POSTGRES_USER`, `POSTGRES_PASSWORD`
- `todolist-keycloak-admin`
  Keys: `KEYCLOAK_ADMIN`, `KEYCLOAK_ADMIN_PASSWORD`
