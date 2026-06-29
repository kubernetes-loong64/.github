# Kubernetes LoongArch64

<p align="center"><a href="README.md">English</a> | <a href="README-zh.md">中文</a></p>

<p align="center"><img src="https://img.shields.io/badge/Kubernetes%20LoongArch64%20%E9%BE%99%E8%8A%AF%E6%9E%B6%E6%9E%84%E5%8F%91%E8%A1%8C%E7%89%88-blue?logo=kubernetes&logoColor=white" alt="Kubernetes LoongArch64 龙芯架构发行版"></p>

将 Kubernetes 生态带到 **LoongArch64 (loong64)** 架构上。

我们通过自动化 CI/CD 流水线，为 **LoongArch64 (loong64)** 平台提供预编译的二进制文件和 Docker 镜像。我们的目标是让 Kubernetes 及其核心组件在 **LoongArch64 (loong64)** 上像在主流架构上一样易于获取、稳定可靠。

## 项目

| 项目                                                                                                         | 描述                                                                       |
|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| [cli-loong64](https://github.com/kubernetes-loong64/cli-loong64)                                           | Docker CLI 二进制文件                                                         |
| [compose-loong64](https://github.com/kubernetes-loong64/compose-loong64)                                   | Docker Compose 二进制文件                                                     |
| [debian-loong64](https://github.com/kubernetes-loong64/debian-loong64)                                     | 同步 Debian 容器镜像到 Docker Hub 用于 LoongArch64                                |
| [containerd-loong64](https://github.com/kubernetes-loong64/containerd-loong64)                             | containerd 二进制文件和容器镜像                                                    |
| [coredns-loong64](https://github.com/kubernetes-loong64/coredns-loong64)                                   | CoreDNS 二进制文件和容器镜像                                                       |
| [cri-tools-loong64](https://github.com/kubernetes-loong64/cri-tools-loong64)                               | 容器运行时 CLI 工具（crictl、critest）                                             |
| [etcd-loong64](https://github.com/kubernetes-loong64/etcd-loong64)                                         | etcd 二进制文件和容器镜像                                                          |
| [git-loong64](https://github.com/kubernetes-loong64/git-loong64)                                           | Git 版本控制系统容器镜像                                                           |
| [gitlab-runner-loong64](https://github.com/kubernetes-loong64/gitlab-runner-loong64)                       | gitlab-runner-helper 容器镜像 LoongArch64 移植                                 |
| [gradle-loong64](https://github.com/kubernetes-loong64/gradle-loong64)                                     | Gradle LoongArch64 容器镜像                                                  |
| [jdk-loong64](https://github.com/kubernetes-loong64/jdk-loong64)                                           | JDK (Java 开发工具包) LoongArch64 容器镜像                                        |
| [jenkins-loong64](https://github.com/kubernetes-loong64/jenkins-loong64)                                   | Jenkins LoongArch64 容器镜像                                                 |
| [kubernetes-loong64](https://github.com/kubernetes-loong64/kubernetes-loong64)                             | Kubernetes 二进制文件和容器镜像                                                    |
| [maven-loong64](https://github.com/kubernetes-loong64/maven-loong64)                                       | Apache Maven LoongArch64 容器镜像                                            |
| [minio-loong64](https://github.com/kubernetes-loong64/minio-loong64)                                       | MinIO 服务器和 mc (MinIO Client) 二进制文件与 Docker 镜像                            |
| [moby-loong64](https://github.com/kubernetes-loong64/moby-loong64)                                         | Docker (Moby) 二进制文件                                                      |
| [nexus-loong64](https://github.com/kubernetes-loong64/nexus-loong64)                                       | Nexus Repository Manager LoongArch64 容器镜像                                |
| [nginx-loong64](https://github.com/kubernetes-loong64/nginx-loong64)                                       | Nginx LoongArch64 容器镜像                                                   |
| [ossutil-loong64](https://github.com/kubernetes-loong64/ossutil-loong64)                                   | ossutil（阿里云 OSS 命令行工具）二进制文件                                              |
| [plugins-loong64](https://github.com/kubernetes-loong64/plugins-loong64)                                   | 容器网络 CNI 插件                                                              |
| [redis-loong64](https://github.com/kubernetes-loong64/redis-loong64)                                       | Redis LoongArch64 容器镜像                                                   |
| [release-loong64](https://github.com/kubernetes-loong64/release-loong64)                                   | Kubernetes 发布工具和构建依赖镜像（debian-base、distroless-iptables、go-runner、setcap） |
| [runc-loong64](https://github.com/kubernetes-loong64/runc-loong64)                                         | runc 二进制文件                                                               |
| [runner-tools-base-images-loong64](https://github.com/kubernetes-loong64/runner-tools-base-images-loong64) | gitlab-runner-helper 基础镜像 LoongArch64 移植                                 |
| [submodule-loong64](https://github.com/kubernetes-loong64/submodule-loong64)                               | 通过 git 子模块聚合所有 LoongArch64 组件仓库的 Monorepo                                |
| [tini-loong64](https://github.com/kubernetes-loong64/tini-loong64)                                         | Tini（容器 init）二进制文件                                                       |
| [valkey-loong64](https://github.com/kubernetes-loong64/valkey-loong64)                                     | Valkey LoongArch64 容器镜像                                                  |

## 容器镜像

完整容器镜像列表请参见 [容器镜像](https://github.com/kubernetes-loong64/.github/wiki/images)。

## 工作原理

GitHub Actions 工作流克隆上游源码，应用 **LoongArch64 (loong64)** 适配补丁，在 Debian 13 环境中使用 `gcc-loongarch64-linux-gnu` 或原生 Go 交叉编译。通过推送符合各项目命名规范的分支或标签触发构建与发布。

关于 Debian 13 容器选型的理由，详见 [Discussion #6 — 为什么使用 container: debian:13？](https://github.com/orgs/kubernetes-loong64/discussions/6)。

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

## 文档

- [LoongArch64 (loong64) 龙芯架构：从 GitHub 安装 github.com/kubernetes-loong64 编译的 containerd、docker 二进制](https://xuxiaowei.io/t/754)
- [LoongArch64 (loong64) 龙芯架构：从 GitHub 安装 github.com/kubernetes-loong64 编译的 containerd、docker rpm 包](https://xuxiaowei.io/t/811)
- [LoongArch64 (loong64) 龙芯架构：从 rpm 仓库 安装 github.com/kubernetes-loong64 编译的 containerd、docker rpm 包](https://xuxiaowei.io/t/812)
- [LoongArch64 (loong64) 龙芯架构：安装 Kubernetes](https://xuxiaowei.io/t/858)
- [视频：龙芯 3B6000 安装 Kubernetes 1.30.1：基于 containerd 2.3.1](https://www.bilibili.com/video/BV1VK7H68EtF/)

## 许可证

所有项目均基于 [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) 许可。
