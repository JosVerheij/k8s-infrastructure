# GitOps


## File Structure

```
appsets/
└── infrastructure.yaml

apps/
├── cilium/
│   ├── app.yaml                 # Not used by this layout
│   ├── values.yaml              # Helm base values
│   ├── clusters/
│   │   └── <argocd-cluster-name>/
│   │       └── values.yaml      # Optional cluster override
│   └── envs/
│       └── homelab/
│           ├── app.yaml         # Discovery metadata
│           └── values.yaml     # Optional environment override
│
├── metrics-server/
│   ├── base/
│   │   ├── kustomization.yaml
│   │   └── deployment.yaml
│   ├── clusters/
│   │   └── <argocd-cluster-name>/
│   │       ├── kustomization.yaml  # Kustomize Component
│   │       └── patch.yaml
│   └── envs/
│       └── homelab/
│           ├── app.yaml
│           └── kustomization.yaml # Kustomize Component
│
└── node-labeler/
    └── envs/
        └── homelab/
            ├── app.yaml
            └── manifests/
                ├── service-account.yaml
                └── job.yaml
```
