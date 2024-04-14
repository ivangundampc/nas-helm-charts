# traefik-forward-auth-openid

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![AppVersion: 1.0.0](https://img.shields.io/badge/AppVersion-1.0.0-informational?style=flat-square)

traefik-forward-auth-openid helm package

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/ivanwongtf/helm-charts/issues/new/choose)**

## Source Code

* <https://github.com/traefik-forward-auth-openid/traefik-forward-auth-openid-docker>

## Requirements

Kubernetes: `>=1.22.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s.github.io/helm-charts/ | common | 2.0.3 |

## TL;DR

```console
helm repo add nas-helm-charts https://ivanwongtf.github.io/nas-helm-charts/
helm repo update

# Need to enable AKAUNTING_SETUP flag for the first boot up
helm install traefik-forward-auth-openid nas-helm-charts/traefik-forward-auth-openid --set AKAUNTING_SETUP="true"
```

## Installing the Chart

To install the chart with the release name `traefik-forward-auth-openid`

```console
# Need to enable AKAUNTING_SETUP flag for the first boot up
helm install traefik-forward-auth-openid nas-helm-charts/traefik-forward-auth-openid --set AKAUNTING_SETUP="true"
```

## Uninstalling the Chart

To uninstall the `traefik-forward-auth-openid` deployment

```console
helm uninstall traefik-forward-auth-openid
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/bjw-s/helm-charts/tree/main/charts/library/common/values.yaml) from the [common library](https://github.com/bjw-s/helm-charts/tree/main/charts/library/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install traefik-forward-auth-openid \
  --set env.TZ="UTC" \
    nas-helm-charts/traefik-forward-auth-openid
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install traefik-forward-auth-openid nas-helm-charts/traefik-forward-auth-openid -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/bjw-s/helm-charts/tree/main/charts/library/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controller.main.containers.main.env | object | See below | environment variables. See more environment variables in the [traefik-forward-auth-openid documentation](https://traefik-forward-auth-openid.org/docs). |
| controller.main.containers.main.env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"traefik-forward-auth-openid/traefik-forward-auth-openid"` | image repository |
| image.tag | string | chart.appVersion | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 1.0.0

#### Added

- Initial version

#### Changed

N/A

#### Fixed

N/A

## Support

- See the [Docs](https://bjw-s.github.io/helm-charts/docs/)
- Open an [issue](https://github.com/ivanwongtf/nas-helm-charts/issues/new/choose)

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)