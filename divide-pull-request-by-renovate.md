# How to Divide Pull Request Created by Renovate

## configure PackageRules in renovate.json

You can divide pull requests created by Renovate through `PackageRules.additionalBranchPrefix` in `renovate.json`. Some variables can be used as prefix that divides pull request. See [renovate.json](/renovate.json) that `baseDir` having a `helmfile.yaml` is used as prefix. You can refer to [Configuration Options - Renovate Docs | Renovate Docs](https://docs.renovatebot.com/configuration-options/#additionalbranchprefix) for more details.

```json
  "packageRules": [
    {
      "managers": ["helmfile"],
      "additionalBranchPrefix": "{{baseDir}}-",
      "commitMessageSuffix": ": {{baseDir}}"
    }
  ]
```