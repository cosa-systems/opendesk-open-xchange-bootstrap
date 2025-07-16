<!--
SPDX-FileCopyrightText: 2023 Bundesministerium des Innern und für Heimat, PG ZenDiS "Projektgruppe für Aufbau ZenDiS"

SPDX-License-Identifier: Apache-2.0
-->
# opendesk-open-xchange-bootstrap

This helm chart contains a bootstrap job for the setup of Open-Xchange

## Installing the Chart

To install the chart with the release name `my-release`:

```console
helm repo add opendesk-open-xchange-bootstrap https://gitlab.opencode.de/api/v4/projects/1379/packages/helm/stable
helm install my-release opendesk-open-xchange-bootstrap/opendesk-open-xchange-bootstrap
```

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | common | ^2.x.x |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| additionalAnnotations | object | `{}` | Additional custom annotations to add to all deployed objects. |
| additionalLabels | object | `{}` | Additional custom labels to add to all deployed objects. |
| cleanup.deletePodsOnSuccess | bool | `true` | Keep Pods/Job logs after successful run. |
| cleanup.deletePodsOnSuccessTimeout | int | `3600` | When deletePodsOnSuccess is enabled, the pod will be deleted after configured seconds. |
| containerSecurityContext.allowPrivilegeEscalation | bool | `false` | Enable container privileged escalation. |
| containerSecurityContext.capabilities | object | `{"drop":["ALL"]}` | Security capabilities for container. |
| containerSecurityContext.readOnlyRootFilesystem | bool | `true` | Mounts the container's root filesystem as read-only. |
| containerSecurityContext.runAsGroup | int | `1000` | Process group id. |
| containerSecurityContext.runAsNonRoot | bool | `true` | Run container as a user. |
| containerSecurityContext.runAsUser | int | `1000` | Process user id. |
| containerSecurityContext.seccompProfile.type | string | `"RuntimeDefault"` | Disallow custom Seccomp profile by setting it to RuntimeDefault. |
| coreMiddleware.adminSelector | string | `"roles.middleware.open-xchange.com/admin=true"` | Selector for provisioning (role admin) |
| coreMiddleware.selector | string | `"app.kubernetes.io/instance=open-xchange,app.kubernetes.io/name=core-mw"` | Selector for all OX core middleware deployments |
| filestore.identifier | string | `"ox-filestore-s3"` | identfier of filestore in filestore-s3.properties |
| filestore.size | int | `100000` | Size in MB |
| fullnameOverride | string | `""` | Provide a name to substitute for the full names of resources. |
| global.imagePullSecrets | list | `[]` | Credentials to fetch images from private registry Ref: https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/  imagePullSecrets:   - "docker-registry"  |
| global.imageRegistry | string | `"docker.io"` | Container registry address. |
| image.digest | string | `""` | use digest instead of image tag, has precedence over tag! |
| image.imagePullPolicy | string | `"IfNotPresent"` | Define an ImagePullPolicy.  Ref.: https://kubernetes.io/docs/concepts/containers/images/#image-pull-policy  "IfNotPresent" => The image is pulled only if it is not already present locally. "Always" => Every time the kubelet launches a container, the kubelet queries the container image registry to             resolve the name to an image digest. If the kubelet has a container image with that exact digest cached             locally, the kubelet uses its cached image; otherwise, the kubelet pulls the image with the resolved             digest, and uses that image to launch the container. "Never" => The kubelet does not try fetching the image. If the image is somehow already present locally, the            kubelet attempts to start the container; otherwise, startup fails  |
| image.registry | string | `"docker.io"` | Container registry address. This setting has higher precedence than global.registry. |
| image.repository | string | `"alpine/k8s"` | Container repository string. |
| image.tag | string | `"1.27.4"` | Overrides the image tag whose default is the chart appVersion. Has no effect if digest is used! |
| imagePullSecrets | list | `[]` | Credentials to fetch images from private registry Ref: https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/  imagePullSecrets:   - "docker-registry"  |
| nameOverride | string | `""` | String to partially override release name. |
| resources.limits.cpu | int | `1` | The max amount of CPUs to consume. |
| resources.limits.memory | string | `"1Gi"` | The max amount of RAM to consume. |
| resources.requests.cpu | string | `"500m"` | The amount of CPUs which has to be available on the scheduled node. |
| resources.requests.memory | string | `"256Mi"` | The amount of RAM which has to be available on the scheduled node. |
| serviceAccount.annotations | object | `{}` | Additional custom annotations for the ServiceAccount. |

## Uninstalling the Chart

To install the release with name `my-release`:

```bash
helm uninstall my-release
```

## Signing

Helm charts are signed with helm native signing method.

You can verify the chart against [the public GPG key](../../files/gpg-pubkeys/opendesk.gpg).

## License

This project uses the following license: Apache-2.0

## Copyright

Copyright (C) 2023 Bundesministerium des Innern und für Heimat, PG ZenDiS "Projektgruppe für Aufbau ZenDiS"
