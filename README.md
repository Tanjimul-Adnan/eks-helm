# eks-helm

This repository is the GitOps source of truth. Terraform creates the Argo CD root Application targeting `bootstrap/`.

## Layout

- `bootstrap/` — root app-of-apps ApplicationSet-style list of child Applications.
- `apps/workshop-app/` — Helm chart and dev values.
- `platform/` — optional platform application definitions.

## GitOps contract

CI in `eks-app` updates `apps/workshop-app/values-dev.yaml` by opening a PR. Review and merge that PR; Argo CD syncs the desired state automatically. `automated.prune` and `selfHeal` are enabled in the root Application.

Replace `REPLACE_WITH_ORG` in all repository URLs. If your repositories are private, configure repository credentials in Argo CD via a secret manager or a secure bootstrap process. Do not commit access tokens.
