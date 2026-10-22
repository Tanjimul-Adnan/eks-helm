# retail-shop-helm

GitOps source of truth. Apply `bootstrap/root-application.yaml` after Argo CD is installed. Argo CD watches this repository and deploys the retail shop Helm chart.

CI updates `apps/retail-shop/values-dev.yaml` by opening a PR. Merge the PR to deploy. Configure private repository credentials through a secure bootstrap/secret-management process.
