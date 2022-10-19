# How to Use Private Helm Repository through Renovate

## Create your own private helm repository

You can build your own private helm repository. See [The Chart Repository Guid](https://helm.sh/docs/topics/chart_repository/) for detail. It's easy way to build it through private GitHub repository. See [Using a Private GitHub Repository as a Helm Chart Repository](https://dev.to/frosnerd/using-a-private-github-repository-as-a-helm-chart-repository-5fa8) for detail.

## Generate encrypted credential by Renovate Encrypt

At first, you prepare a credential to access to your private helm repository. It may be your personal GitHub access token or other. Once you prepare it you can encrypt it through [Renovate Encrypt](https://app.renovatebot.com/encrypt). you fill your `Organization`, `Repository` and `Raw Password Value` into box and click `Encrypt` button.

## Reference secret in helmfile.yaml

You can refer to the secret in `renovate.json` that you generated through `Renovate Encrypt`. See [renovate.json](/renovate.json) that refer to your secrets as `username` and `encrypted.password` for private helm repository.

```json
  "hostRules": [
    {
      "hostName": "https://raw.githubusercontent.com/yourname/sample-helm-repository/main/",
      "hostType": "helm",
      "username": "<your username>",
      "encrypted": {
        "password": "<encrypted password through Renovate Encrypt>"
      }
    }
  ],
```