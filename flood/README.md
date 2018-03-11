# flood

flood is a Kubernetes deployment that bundles rtorrent together with the Flood web UI.

## Prerequisites

- Kubernetes 1.7+

## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm install --name my-release blakemiller/flood
```

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

The following tables lists the configurable parameters of the flood chart and their default values.

| Parameter | Description | Default |
| --------- | ----------- | ------- |
| `image.flood.repository` | Image repository | `blakemiller/flood` |
| `image.rtorrent.repository` | Image repository | `blakemiller/rtorrent` |
| `image.tag` | Image tag | `latest` |
| `ingress.enabled` | Enable Ingress creation for Flood web UI | `true` |
| `ingress.annotations` | Arbitraty annotations for Ingress  | `kubernetes.io/ingress.class: nginx` |
| `ingress.path` | URI for Flood web UI | `/` |
| `nfs.enabled` | Enable persistence for storing rtorrent data | `false` |
| `nfs.server` | NFS server address | `` |
| `nfs.path` | Path to share on NFS server | `` |
| `nfs.size` | Size of NFS share | `` |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart. For example,

```console
$ helm install --name my-release -f values.yaml .
```
> **Tip**: You can use the default [values.yaml](values.yaml)