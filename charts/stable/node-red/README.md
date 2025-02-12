# node-red

![Version: 10.0.0](https://img.shields.io/badge/Version-10.0.0-informational?style=flat-square) ![AppVersion: 2.1.4](https://img.shields.io/badge/AppVersion-2.1.4-informational?style=flat-square)

Node-RED is low-code programming for event-driven applications

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/node-red/node-red-docker>
* <https://github.com/k8s-at-home/charts/tree/master/charts/node-red>

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
helm install node-red k8s-at-home/node-red
```

## Installing the Chart

To install the chart with the release name `node-red`

```console
helm install node-red k8s-at-home/node-red
```

## Uninstalling the Chart

To uninstall the `node-red` deployment

```console
helm uninstall node-red
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install node-red \
  --set env.TZ="America/New York" \
    k8s-at-home/node-red
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install node-red k8s-at-home/node-red -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See [image docs](https://nodered.org/docs/getting-started/docker) for more details. |
| env.FLOWS | string | `"flows.json"` | Location of the flows configuration file. If you set `FLOWS: ""` then the flow file can be set via the `flowFile` property in the `settings.js` file. |
| env.NODE_OPTIONS | string | `nil` | Node.js runtime arguments |
| env.NODE_RED_ENABLE_PROJECTS | string | `nil` | Setting to `true` starts Node-RED with the projects feature enabled |
| env.NODE_RED_ENABLE_SAFE_MODE | string | `nil` | Setting to `true` starts Node-RED in safe (not running) mode |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"nodered/node-red"` | image repository |
| image.tag | string | `"2.1.4"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

All notable changes to this application Helm chart will be documented in this file but does not include changes from our common library. To read those click [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common#changelog).

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

### [10.0.0]

#### Changed

- Upgrade to Node Red 2.x (2.1.4) upstream image.
- Upgrade common dep to 4.3.0.

### [9.0.0]

#### Changed

- Upgraded the common library dependency to version 4.0.0. This introduced (potentially) breaking changes to `initContainers` and `additionalContainers`. Be sure to check out the [library chart](https://github.com/k8s-at-home/library-charts/blob/common-4.0.0/charts/stable/common/) for the up-to-date values.

### [8.0.0]

#### Changed

- **BREAKING**: Upgraded the common library dependency to version 3.2.0. This introduces several breaking changes (`service`, `ingress` and `persistence` keys have been refactored).
  Be sure to check out the [library chart](https://github.com/k8s-at-home/library-charts/blob/common-3.2.0/charts/stable/common/) for the up-to-date values.
- Changed image tag to `1.3.5`.

### [1.0.0]

#### Added

- Initial version

[9.0.0]: #900
[8.0.0]: #800
[1.0.0]: #100

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
