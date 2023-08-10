<!--
SPDX-FileCopyrightText: 2023 Bundesministerium des Innern und für Heimat, PG ZenDiS "Projektgruppe für Aufbau ZenDiS"

SPDX-License-Identifier: Apache-2.0
-->
# Sovereign Workplace Open-Xchange Bootstrap Helm Chart Repository

This repository contains a Helm Chart for initializing Open-Xchange:

1. waits for the middleware to be available
1. creates a directory for ox-filestore under `/opt/open-xchange/ox-filestore`
1. `initconfigdb`
1. waits for port 8009
1. `registerfilestore`
1. `registerserver`
1. `registerdatabase`
1. restarts the stateful set

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Kubernetes 1.21+
- Helm 3.0.0+
- Optional: PV provisioner support in the underlying infrastructure

## Documentation

The documentation is placed in the README of each helm chart:

- [sovereign-workplace-open-xchange-bootstrap](charts/sovereign-workplace-open-xchange-bootstrap)

## License

This project uses the following license: Apache-2.0

## Copyright

Copyright © 2023 Bundesministerium des Innern und für Heimat, PG ZenDiS "Projektgruppe für Aufbau ZenDiS"
