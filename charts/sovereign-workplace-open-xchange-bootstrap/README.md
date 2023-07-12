# sovereign-workplace-open-xchange-bootstrap

This helm chart contains a bootstrap job for the setup of Open-Xchange

## Installing the Chart

To install the chart with the release name `my-release`:

```console
helm repo add sovereign-workplace-open-xchange-bootstrap https://gitlab.souvap-univention.de/api/v4/projects/139/packages/helm/stable
helm install my-release sovereign-workplace-open-xchange-bootstrap/sovereign-workplace-open-xchange-bootstrap
```

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | common | 2.6.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| cleanup.deletePodsOnSuccess | bool | `false` | Keep Pods/Job logs after successful run. |
| fullnameOverride | string | `""` |  |
| global.imagePullSecrets | list | `[]` |  |
| global.imageRegistry | string | `"docker.io"` |  |
| image.imagePullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"alpine/k8s"` |  |
| image.tag | string | `"1.25.6"` |  |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| resources.limits.cpu | int | `1` | The max amount of CPUs to consume. |
| resources.limits.memory | string | `"1Gi"` | The max amount of RAM to consume. |
| resources.requests.cpu | string | `"500m"` | The amount of CPUs which has to be available on the scheduled node. |
| resources.requests.memory | string | `"256Mi"` | The amount of RAM which has to be available on the scheduled node. |

## Uninstalling the Chart

To install the release with name `my-release`:

```bash
helm uninstall my-release
```

## Signing

### Chart

Helm charts are signed with helm native signing method. You can verify the charts against this GPG key:

```
-----BEGIN PGP PUBLIC KEY BLOCK-----

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
XD85LYkPgsax8WY=
=cFEh
-----END PGP PUBLIC KEY BLOCK-----
```

### Images

Container images are signed via [cosign](https://github.com/sigstore/cosign) and can be verified with:

```
-----BEGIN PUBLIC KEY-----
MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAETIpFd4qC4ThMC4PmFIPulqFVhfD/
1ujC+TfS7hTH7X06tleO6a2Gl2Vkn0k88A4LDmvFfNFoHRnEhVsjcLDNDw==
-----END PUBLIC KEY-----

```

```
cosign verify --key cosign.pub --insecure-ignore-tlog <image>
```

## License
This project uses the following license: Apache-2.0

## Copyright
Copyright (C) 2023 Bundesministerium des Innern und für Heimat, PG ZenDiS "Projektgruppe für Aufbau ZenDiS"
