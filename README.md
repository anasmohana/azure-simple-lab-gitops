# azure-simple-lab-gitops

Manifests that Flux (installed on the lab AKS cluster by Terraform) syncs. Public on purpose: contains nothing sensitive.

```
infrastructure/ingress-nginx   ingress controller (Helm) with a public load balancer IP
apps/website                   a small static site served by nginx through the ingress
```

Flux applies `infrastructure` first, then `apps` (declared in the Terraform `aks-bootstrap` layer of
[azure-simple-lab](https://github.com/anasmohana/azure-simple-lab)). Change a file here, push, and the cluster follows within ~2 minutes.
