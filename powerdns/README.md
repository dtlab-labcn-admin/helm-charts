# powerdns

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![AppVersion: v4.3.1](https://img.shields.io/badge/AppVersion-v4.3.1-informational?style=flat-square)

PowerDNS is a DNS server, written in C++ and licensed under the GPL. It runs on most Unix derivatives. PowerDNS features a large number of different backends ranging from simple BIND style zonefiles to relational databases and load balancing/failover algorithms. A DNS recursor is provided as a separate program.

## Notice

This is a modified version of the k8s@home chart: https://github.com/k8s-at-home/charts/tree/master/charts/stable/powerdns

Modifications were made to:
- Strip mariadb and sqlite support
- Allow external PSQL host
- Allow different service types

## Source Code

* <http://www.github.com/PowerDNS/>

## Requirements

## TL;DR

```console
helm repo add idlab https://tbd
helm repo update
helm install powerdns idlab/powerdns
```

## Installing the Chart

To install the chart with the release name `powerdns`

```console
helm install powerdns idlab/powerdns
```

## Uninstalling the Chart

To uninstall the `powerdns` deployment

```console
helm uninstall powerdns
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install powerdns \
  --set env.TZ="America/New York" \
    idlab/powerdns
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install powerdns idlab/powerdns -f values.yaml
```

## Values


| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"Always"` |  |
| image.repository | string | `"naps/powerdns"` |  |
| image.tag | string | `"4.3.1"` |  |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| powerdns.config | object | `{}` |  |
| powerdns.dnssec | bool | `true` |  |
| powerdns.domain | string | `"mydomain.local"` |  |
| powerdns.mysql.database | string | `"pdns"` |  |
| powerdns.mysql.password | string | `"pdnspass"` |  |
| powerdns.mysql.username | string | `"pdns"` |  |
| powerdns.postgres.database | string | `"pdns"` |  |
| powerdns.postgres.password | string | `"pdnspass"` |  |
| powerdns.postgres.username | string | `"pdns"` |  |
| powerdns.postgres.host | string | `"postgresql"` |  |
| probes.liveness.enabled | bool | `true` |  |
| probes.liveness.failureThreshold | int | `5` |  |
| probes.liveness.initialDelaySeconds | int | `30` |  |
| probes.liveness.timeoutSeconds | int | `10` |  |
| probes.readiness.enabled | bool | `true` |  |
| probes.readiness.failureThreshold | int | `5` |  |
| probes.readiness.initialDelaySeconds | int | `30` |  |
| probes.readiness.timeoutSeconds | int | `10` |  |
| probes.startup.enabled | bool | `false` |  |
| probes.startup.failureThreshold | int | `30` |  |
| probes.startup.periodSeconds | int | `10` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` |  |
| service.externalTrafficPolicy | string | `""` |  |
| service.port | int | `53` |  |
| service.type | string | `"LoadBalancer"` |  |
| service.loadBalancerIP | string | `"127.0.0.1"` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `nil` |  |
| strategyType | string | `"Recreate"` |  |
| tolerations | list | `[]` |  |
