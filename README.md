#pre-commit-hooks
Repository of pre-commit hooks I've created to help guard myself against dumb mistakes in commits.


## the hooks
  - terraform-format -- runs `terraform fmt` on all terraform files in the repo, formatting them and syntax checking them.
  - kustomize-build -- runs `kustomize build .` against a found kustomize manifest and ensures the files can actually create a legit manifest.
  - kustomize-missing -- compares the found yaml manifests vs. the listed yamls in kustomize manifest to detect when there are discrepancies.
    - if you intentionally want to not put a patched yaml in your kustomization.yaml file, add it to the file like `#ignore file.yaml` 
