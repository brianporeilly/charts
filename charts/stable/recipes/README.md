# recipes

![Version: 6.4.0](https://img.shields.io/badge/Version-6.4.0-informational?style=flat-square) ![AppVersion: 1.0.5.2](https://img.shields.io/badge/AppVersion-1.0.5.2-informational?style=flat-square)

Recipes is a Django application to manage, tag and search recipes using either built in models or external storage providers hosting PDF's, Images or other files.

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/vabene1111/recipes>
* <https://hub.docker.com/r/vabene1111/recipes>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 4.3.0 |

## TL;DR

```console
helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install recipes k8s-at-home/recipes
```

## Installing the Chart

To install the chart with the release name `recipes`

```console
helm install recipes k8s-at-home/recipes
```

## Uninstalling the Chart

To uninstall the `recipes` deployment

```console
helm uninstall recipes
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install recipes \
  --set env.TZ="America/New York" \
    k8s-at-home/recipes
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install recipes k8s-at-home/recipes -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See [project docs](https://raw.githubusercontent.com/vabene1111/recipes/master/.env.template) for more details. |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"vabene1111/recipes"` | image repository |
| image.tag | string | `"1.0.5.2"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |
| sidecar.config.client_max_body_size | string | `"128M"` | define the max body size to allow larger files to be uploaded |
| sidecar.config.reverse_proxy_header_username | string | `"x_authentik_username"` | define the name of the variable in the header containing the authenticated user. It is used together with enabling `REVERSE_PROXY_AUTH` |
| sidecar.image.pullPolicy | string | `"IfNotPresent"` | nginx sidecar image pull policy |
| sidecar.image.repository | string | `"nginx"` | nginx sidecar image repository |
| sidecar.image.tag | string | `"1.21.6"` | nginx sidecar image tag |

## Changelog

### Version 6.4.0

#### Added

* Support for reverse proxy authentication.

#### Changed

N/A

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/k8s-at-home/recipes?modal=changelog)

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/k8s-at-home/helm-docs/releases/v0.1.1)
