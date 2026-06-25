## LoongArch GitLab Runner

<p align="center"><a href="README.md">English</a> | <a href="README-zh.md">中文</a></p>

## Overview

This project builds the **gitlab-runner-helper** Docker image for the **loong64** (LoongArch) architecture. It is a submodule of the [kubernetes-loong64](https://github.com/kubernetes-loong64) project.

The upstream GitLab Runner project ([gitlab-org/gitlab-runner](https://gitlab.com/gitlab-org/gitlab-runner)) provides the `gitlab-runner-helper` image for `linux/amd64`. This repository patches the upstream to produce the `linux/loong64` **gitlab-runner-helper** Docker image, using **Debian 14** (from `lcr.loongnix.cn`) as the base.

> **Note:** This project does **not** build GitLab Runner binaries, RPM packages, or DEB packages. It focuses solely on the `gitlab-runner-helper` Docker image, which is used by the GitLab Runner **Docker executor** and **Kubernetes executor** to run CI/CD jobs on LoongArch.

[![kubernetesloong64/gitlab-runner-helper](https://img.shields.io/docker/v/kubernetesloong64/gitlab-runner-helper?logo=docker&label=kubernetesloong64%2Fgitlab-runner-helper)](https://hub.docker.com/r/kubernetesloong64/gitlab-runner-helper/tags)

## Branches

| Branch            | Description                                                              |
|-------------------|--------------------------------------------------------------------------|
| `main`            | Project documentation, license, and shared configuration                 |
| `loong64-v19.1.1` | Patched build for upstream GitLab Runner v19.1.1 with loong64 support    |

New loong64 release branches follow the naming convention `loong64-<upstream-version>`.


## Verifying releases

- Releases are signed with GPG.
- Download the public key from [keys.openpgp.org](https://keys.openpgp.org).
- Fingerprint: [FCF8724722CCBF9F51B1FBE376532BE7E3013105](https://keys.openpgp.org/debug?q=FCF8724722CCBF9F51B1FBE376532BE7E3013105)
- [Manual download](https://keys.openpgp.org/vks/v1/by-fingerprint/FCF8724722CCBF9F51B1FBE376532BE7E3013105)

```shell
gpg --keyserver keys.openpgp.org --recv-keys FCF8724722CCBF9F51B1FBE376532BE7E3013105
echo "FCF8724722CCBF9F51B1FBE376532BE7E3013105:6:" | gpg --import-ownertrust
```

Or download the key file manually and import it:

```shell
gpg --import /tmp/xxx
```

## License

[Apache License 2.0](LICENSE)
