# prometheus-openziti-exporter

Prometheus exporter for collecting [OpenZiti Management Edge API](https://openziti.io/docs/reference/developer/api/) information,
written in Go with pluggable metric collectors.

This chart bootstraps a [OpenZiti exporter](https://github.com/enthus-it/openziti_exporter) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

## Prerequisites

- Kubernetes 1.10+ with Beta APIs enabled
- Helm 3+

## Get Repository Info

```console
helm repo add enthus-it https://enthus-it.github.io/helm-charts
helm repo update
```

_See [`helm repo`](https://helm.sh/docs/helm/helm_repo/) for command documentation._

## Install Chart

```console
helm install [RELEASE_NAME] enthus-it/prometheus-openziti-exporter
```

_See [configuring](#configuring) below._

_See [helm install](https://helm.sh/docs/helm/helm_install/) for command documentation._

## Uninstall Chart

```console
helm uninstall [RELEASE_NAME]
```

This removes all the Kubernetes components associated with the chart and deletes the release.

_See [helm uninstall](https://helm.sh/docs/helm/helm_uninstall/) for command documentation._

## Upgrading Chart

```console
helm upgrade [RELEASE_NAME] [CHART] --install
```

_See [helm upgrade](https://helm.sh/docs/helm/helm_upgrade/) for command documentation._

## Configuring

See [Customizing the Chart Before Installing](https://helm.sh/docs/intro/using_helm/#customizing-the-chart-before-installing). To see all configurable options with detailed comments, visit the chart's [values.yaml](./values.yaml), or run these configuration commands:

```console
helm show values enthus-it/prometheus-openziti-exporter
```

For more information please refer to the [openziti_exporter](https://github.com/enthus-it/openziti_exporter) documentation.

## Test functionality

Access the exporter via port-forward and look the the scraped metrics:

```console
kubectl port-forward -n _NAMESPACE_ _PODNAME_ 10004:10004
```
