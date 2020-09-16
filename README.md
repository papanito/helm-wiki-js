# Helm Chart for "wiki.js"

A Helm chart for [Wiki Js](https://wiki.js.org/)


## What is Wiki.js?

>  Wiki.js's beautiful and intuitive interface! Released under the AGPL-v3 license. Install anywhere Works on virtually any platform and is compatible with either PostgreSQL, MySQL, MariaDB, MS SQL Server or SQLite! Administration Manage all aspects of your wiki using the extensive and intuitive admin area.

[Wiki Js](https://wiki.js.org/)


## TL;DR

```console
$ helm repo add xxxx https://charts.xxxx.com/xxx
$ helm install my-release xxx/wiki
```

## Introduction

This chart bootstraps a [Wiki.js](https://hub.docker.com/r/requarks/wiki) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.


## Prerequisites

- Kubernetes 1.12+
- Helm 2.12+ or Helm 3.0
- PV provisioner support in the underlying infrastructure


## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm repo add xxxx https://charts.xxxx.com/xxx
$ helm install my-release xxx/wiki
```

These commands deploy Wiki.js on the Kubernetes cluster in the default configuration. The [Parameters](#parameters) section lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `my-release` resources:

```console
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release. Use the option `--purge` to delete all history too.

## Parameters

The following tables lists the configurable parameters of the fluentd chart and their default values.

| Parameter                          | Description                                                                                                    | Default                                                  |
|-------------------------- ---------|----------------------------------------------------------------------------------------------------------------|----------------------------------------------------------|
| `image.registry`                   | Wiki image registry                                                                                            | `docker.io`                                              |
| `image.repository`                 | Wiki image name                                                                                                | `requarks/wiki`                                          |
| `image.tag`                        | Wiki image tag                                                                                                 | `{TAG_NAME}`                                             |
| `image.pullPolicy`                 | Wiki image pull policy                                                                                         | `IfNotPresent`                                           |
| `nameOverride`                     | String to partially override `wikijs.fullname` template with a string (will prepend the release name)          | `nil`                                                    |
| `fullnameOverride`                 | String to fully override `wikijs.fullname` template with a string                                              | `nil`                                                    |
| `resources`                        | Resource limits                                                                                                | `nil`                                                    |
| `persistence.config.storageClass`  | Persistent Volume storage class                                                                                | `nil`                                                    |
| `persistence.config.accessMode`    | Persistent Volume access mode                                                                                  | `ReadWriteOnce`                                          |
| `persistence.config.size`          | Persistent Volume size                                                                                         | `10Gi`                                                   |
| `persistence.config.claimName`     | Persistent Volume claim name                                                                                   | `nil`                                                    |
| `env.wikiAdminEmail`               | Admin email for wiki, set as environment variable                                                              | `admin@example.com`                                      |