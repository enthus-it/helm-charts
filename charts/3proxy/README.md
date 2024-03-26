# 3proxy-helm

The unofficial Helm Chart for 3proxy. See more about 3proxy at <https://github.com/z3APA3A/3proxy>.

The goal of this project is to provide a Helm chart for running 3proxy in Kubernetes.

This chart creates a kubernetes *service* for the ports forwarded by [this 3proxy docker image](https://github.com/tarampampam/3proxy-docker).

## Get Repository Info

```console
helm repo add enthus-it https://enthus-it.github.io/helm-charts
helm repo update
```

See [`helm repo`](https://helm.sh/docs/helm/helm_repo/) for command documentation.

## Installing

```console
helm install --namespace=3proxy --values values.yaml 3proxy enthus-it/3proxy
```

## Uninstalling

```console
helm delete --namespace=3proxy 3proxy
# OR
helm delete MY-RELEASE
```

## Parameters

### 3proxy configuration

| Parameter               | Description                                     | Default |
| ----------------------- | ----------------------------------------------- | ------- |
| `config.proxyLogin`     | Authorization login  | empty |
| `config.proxyPassword`  | Authorization password | empty |
| `config.dns.primary`    | Primary nameserver  | `1.0.0.1` |
| `config.dns.secondary`  | Secondary nameserver  | `8.8.4.4` |
| `config.maxConnections` | Maximal connections count | `1024` |
| `config.extraConfig`    | Additional 3proxy configuration (see example) | empty |

### Service configuration

| Parameter                | Description                                     | Default |
| ------------------------ | ----------------------------------------------- | ------- |
| `service.type`           | See `kubectl explain service.spec.type` | `ClusterIP` |
| `service.http.enabled`   | Enable service HTTP proxy port | `true` |
| `service.http.port`      | HTTP proxy port | `3128` |
| `service.socks.enabled`  | Enable service SOCKS proxy port | `true` |
| `service.socks.port`     | SOCKS proxy port | `1080`|
