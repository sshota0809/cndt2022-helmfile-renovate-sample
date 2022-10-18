# How to Use Private Helm Repository through helmfile

## Create your own private helm repository

You can build your own private helm repository. See [The Chart Repository Guid](https://helm.sh/docs/topics/chart_repository/) for detail. It's easy way to build it through private GitHub repository. See [Using a Private GitHub Repository as a Helm Chart Repository](https://dev.to/frosnerd/using-a-private-github-repository-as-a-helm-chart-repository-5fa8) for detail.

## Generate encrypted credential by helm-secrets

At first, you prepare a credential to access to your private helm repository. It may be your personal GitHub access token or other.  Once you prepare it you can encrypt it through `helm-secrets`. See [helmfile document](https://helmfile.readthedocs.io/en/latest/#environment-secrets) for detail.

## Reference secret in helmfile.yaml

