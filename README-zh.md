## LoongArch GitLab Runner

<p align="center"><a href="README.md">English</a> | <a href="README-zh.md">中文</a></p>

## 概述

本项目为 **loong64**（龙芯架构）构建 **gitlab-runner-helper** Docker 镜像。它是 [kubernetes-loong64](https://github.com/kubernetes-loong64) 项目的子模块。

上游 GitLab Runner 项目（[gitlab-org/gitlab-runner](https://gitlab.com/gitlab-org/gitlab-runner)）提供面向 `linux/amd64` 的 `gitlab-runner-helper` 镜像。本仓库通过补丁将上游适配为 `linux/loong64` 的 **gitlab-runner-helper** Docker 镜像，使用 **Debian 14**（来自 `lcr.loongnix.cn`）作为基础镜像。

> **注意：** 本项目**不**构建 GitLab Runner 二进制文件、RPM 包或 DEB 包。它仅专注于 `gitlab-runner-helper` Docker 镜像，该镜像供 GitLab Runner **Docker 执行器**和 **Kubernetes 执行器**在 LoongArch 上运行 CI/CD 作业时使用。

[![kubernetesloong64/gitlab-runner-helper](https://img.shields.io/docker/v/kubernetesloong64/gitlab-runner-helper?logo=docker&label=kubernetesloong64%2Fgitlab-runner-helper)](https://hub.docker.com/r/kubernetesloong64/gitlab-runner-helper/tags)

## 分支

| 分支                | 描述                                        |
|-------------------|-------------------------------------------|
| `main`            | 项目文档、许可证和公共配置                             |
| `loong64-v19.1.0` | 基于上游 GitLab Runner v19.1.0 的 loong64 适配构建 |

新的 loong64 发布分支遵循命名约定 `loong64-<上游版本号>`。

## 验证发布

- 发布文件使用 GPG 签名。
- 从 [keys.openpgp.org](https://keys.openpgp.org) 下载公钥。
- 指纹：[FCF8724722CCBF9F51B1FBE376532BE7E3013105](https://keys.openpgp.org/debug?q=FCF8724722CCBF9F51B1FBE376532BE7E3013105)
- [手动下载](https://keys.openpgp.org/vks/v1/by-fingerprint/FCF8724722CCBF9F51B1FBE376532BE7E3013105)

```shell
gpg --keyserver keys.openpgp.org --recv-keys FCF8724722CCBF9F51B1FBE376532BE7E3013105
echo "FCF8724722CCBF9F51B1FBE376532BE7E3013105:6:" | gpg --import-ownertrust
```

或者，手动下载公钥文件后导入：

```shell
gpg --import /tmp/xxx
```

## 许可证

[Apache License 2.0](LICENSE)
