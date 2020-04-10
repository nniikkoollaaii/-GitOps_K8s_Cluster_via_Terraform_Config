# GitOps_K8s_Cluster_via_Terraform_Config

Repository containing K8s Configuration for GitOps

See [GitOps_K8s_Cluster_via_Terraform Repository](https://github.com/nniikkoollaaii/GitOps_K8s_Cluster_via_Terraform) for more information

## Team1

Uses a single namespace

So Flux and HelmOperator HelmReleases are added to "gitops"-NS to be applied to "team1"-NS by Admin-Flux and -Helm-Operator

In addition you have to add a secret in team1 dir (call it "git-auth.secret.yaml")  with your git credentials to access team1 repo for their app deployment

It should have the following format:

```
apiVersion: v1
kind: Secret
metadata:
  name: git-auth
  namespace: team1
type: Opaque
data:
  username: base64(username)
  password: base64(password)
```