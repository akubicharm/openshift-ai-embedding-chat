manually

```bash
oc apply -f ./bootstrap/applicationset/argocd.yaml
oc rollout status deploy/argocd-server
oc apply -f ./bootstrap/applicationset/applicationset-bootstrap.yaml

```