# ui-vmm helm charts

This repository hosts [Helm](https://helm.sh) charts for [ui-vmm](https://ui-vmm.github.io). These charts are used to deploy ui-vmm to Kubernetes.

## Add the ui-vmm Helm Chart repo

In order to be able to use the charts in this repository, add the name and URL to your Helm client:

```console
helm repo add ui-vmm https://ui-vmm.github.io/ui-vmm-helm
helm repo update
```

## Use this charts

For correct deployment of `ui-vmm/ui-vmm`, see examples of [charts/ui-vmm/values-files.yaml](https://raw.githubusercontent.com/ui-vmm/ui-vmm-helm/master/charts/ui-vmm/values-files.yaml)

Render charts:

```console
# ui-vmm backend
helm template ui-vmm/ui-vmm -f charts/ui-vmm/values-files.yaml --set "global.ci_url=hello-world.info"

# ui-vmm frontend
helm template ui-vmm/ui-vmm-panel --set "global.ci_url=hello-world.info"
```

Deploy applications:

```console
# ui-vmm backend
helm upgrade --install -n default ui-vmm ui-vmm/ui-vmm -f charts/ui-vmm/values-files.yaml --set "global.ci_url=hello-world.info"

# ui-vmm frontend
helm upgrade --install -n default ui-vmm-panel ui-vmm/ui-vmm-panel --set "global.ci_url=hello-world.info"
```
