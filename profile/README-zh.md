# Kubernetes LoongArch64

<p align="center"><a href="README.md">English</a> | <a href="README-zh.md">中文</a></p>

<p align="center"><img src="https://img.shields.io/badge/Kubernetes%20LoongArch64%20%E9%BE%99%E8%8A%AF%E6%9E%B6%E6%9E%84%E5%8F%91%E8%A1%8C%E7%89%88-blue?logo=kubernetes&logoColor=white" alt="Kubernetes LoongArch64 龙芯架构发行版"></p>

将 Kubernetes 生态带到 **LoongArch64 (loong64)** 架构上。

我们通过自动化 CI/CD 流水线，为 **LoongArch64 (loong64)** 平台提供预编译的二进制文件和 Docker 镜像。我们的目标是让 Kubernetes 及其核心组件在 **LoongArch64 (loong64)** 上像在主流架构上一样易于获取、稳定可靠。

## 项目

| 项目                                                                             | 描述                                                                       |
|--------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| [kubernetes-loong64](https://github.com/kubernetes-loong64/kubernetes-loong64) | Kubernetes 二进制文件和容器镜像                                                    |
| [release-loong64](https://github.com/kubernetes-loong64/release-loong64)       | Kubernetes 发布工具和构建依赖镜像（debian-base、distroless-iptables、go-runner、setcap） |
| [etcd-loong64](https://github.com/kubernetes-loong64/etcd-loong64)             | etcd 二进制文件和容器镜像                                                          |
| [coredns-loong64](https://github.com/kubernetes-loong64/coredns-loong64)       | CoreDNS 容器镜像                                                             |
| [cri-tools-loong64](https://github.com/kubernetes-loong64/cri-tools-loong64)   | 容器运行时 CLI 工具（crictl、critest）                                             |
| [plugins-loong64](https://github.com/kubernetes-loong64/plugins-loong64)       | 容器网络 CNI 插件                                                              |
| [cli-loong64](https://github.com/kubernetes-loong64/cli-loong64)               | Docker CLI 二进制文件                                                         |
| [containerd-loong64](https://github.com/kubernetes-loong64/containerd-loong64) | containerd 二进制文件和容器镜像                                                    |
| [moby-loong64](https://github.com/kubernetes-loong64/moby-loong64)             | Docker (Moby) 二进制文件                                                      |
| [runc-loong64](https://github.com/kubernetes-loong64/runc-loong64)             | runc 二进制文件                                                               |

## 工作原理

GitHub Actions 工作流克隆上游源码，应用 **LoongArch64 (loong64)** 适配补丁，在 Debian 13 环境中使用 `gcc-loongarch64-linux-gnu` 或原生 Go 交叉编译。通过推送符合各项目命名规范的分支或标签触发构建与发布。

关于 Debian 13 容器选型的理由，详见 [Discussion #6 — 为什么使用 container: debian:13？](https://github.com/orgs/kubernetes-loong64/discussions/6)。

## 验证发布

所有发布均经过 GPG 签名。导入公钥以进行验证：

```
gpg --keyserver keys.openpgp.org --recv-keys FCF8724722CCBF9F51B1FBE376532BE7E3013105
echo "FCF8724722CCBF9F51B1FBE376532BE7E3013105:6:" | gpg --import-ownertrust
```

## 许可证

所有项目均基于 [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) 许可。
