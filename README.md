# pre-commit-hooks
Repository of pre-commit hooks I've created to help guard myself against dumb mistakes in commits.

## how to use
This repository is meant to be referenced by the [pre-commit](https://pre-commit.com) helper app.
Add this to your `.pre-commit-config.yaml` file at the root of your repo, specifying the hooks you wish to use for the repository in question:
```
- repo: https://github.com/PeterGrace/pre-commit-hooks
  rev: master
  hooks:
  - id: kustomize-build
  - id: kustomize-missing
  - id: <...>

```


## the hooks
  - terraform-format -- runs `terraform fmt` on all terraform files in the repo, formatting them and syntax checking them.
  - kustomize-build -- runs `kustomize build .` against a found kustomize manifest and ensures the files can actually create a legit manifest.
  - kustomize-missing -- compares the found yaml manifests vs. the listed yamls in kustomize manifest to detect when there are discrepancies.
    - if you intentionally want to not put a patched yaml in your kustomization.yaml file, add it to the file like `#ignore file.yaml` 
