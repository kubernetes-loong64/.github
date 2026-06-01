# Kubernetes LoongArch64

<p align="center"><a href="README.md">English</a> | <a href="README-zh.md">中文</a></p>

<p align="center"><img src="https://img.shields.io/badge/Kubernetes%20LoongArch64%20%E9%BE%99%E8%8A%AF%E6%9E%B6%E6%9E%84%E5%8F%91%E8%A1%8C%E7%89%88-blue?logo=kubernetes&logoColor=white" alt="Kubernetes LoongArch64 龙芯架构发行版"></p>

Bringing the Kubernetes ecosystem to the **LoongArch64 (loong64)** architecture.

We provide pre-built binaries and Docker images for LoongArch64, built via automated CI/CD pipelines. Our goal is to make Kubernetes and its core components on **LoongArch64 (loong64)** as accessible and reliable as they are on mainstream architectures.

## Projects

| Project                                                                        | Description                                                                                                  |
|--------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| [kubernetes-loong64](https://github.com/kubernetes-loong64/kubernetes-loong64) | Kubernetes binaries and container images for LoongArch64                                                     |
| [release-loong64](https://github.com/kubernetes-loong64/release-loong64)       | Kubernetes release tooling and build dependency images (debian-base, distroless-iptables, go-runner, setcap) |
| [etcd-loong64](https://github.com/kubernetes-loong64/etcd-loong64)             | etcd binaries and container images for LoongArch64                                                           |
| [coredns-loong64](https://github.com/kubernetes-loong64/coredns-loong64)       | CoreDNS container images for LoongArch64                                                                     |

## How it works

GitHub Actions workflows clone upstream sources, apply **LoongArch64 (loong64)** compatibility patches, and cross-compile using `gcc-loongarch64-linux-gnu` or native Go cross-compilation in a Debian 13 environment. Releases are triggered by pushing branches or tags following project-specific naming conventions.

## Verifying releases

All releases are GPG-signed. Import the public key to verify:

```
gpg --keyserver keys.openpgp.org --recv-keys F3693AB74BBA0D84C227AB34F3A4B5061568FC57
```

## License

All projects are licensed under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
