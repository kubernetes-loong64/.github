# Kubernetes LoongArch64

<p align="center"><a href="README.md">English</a> | <a href="README-zh.md">中文</a></p>

<p align="center"><img src="https://img.shields.io/badge/Kubernetes%20LoongArch64%20%E9%BE%99%E8%8A%AF%E6%9E%B6%E6%9E%84%E5%8F%91%E8%A1%8C%E7%89%88-blue?logo=kubernetes&logoColor=white" alt="Kubernetes LoongArch64 龙芯架构发行版"></p>

Bringing the Kubernetes ecosystem to the **LoongArch64 (loong64)** architecture.

We provide pre-built binaries and Docker images for LoongArch64, built via automated CI/CD pipelines. Our goal is to make Kubernetes and its core components on **LoongArch64 (loong64)** as accessible and reliable as they are on mainstream architectures.

## Projects

| Project                                                                                                    | Description                                                                                                  |
|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| [cli-loong64](https://github.com/kubernetes-loong64/cli-loong64)                                           | Docker CLI binaries for LoongArch64                                                                          |
| [compose-loong64](https://github.com/kubernetes-loong64/compose-loong64)                                   | Docker Compose binary for LoongArch64                                                                        |
| [containerd-loong64](https://github.com/kubernetes-loong64/containerd-loong64)                             | containerd binaries and container images for LoongArch64                                                     |
| [coredns-loong64](https://github.com/kubernetes-loong64/coredns-loong64)                                   | CoreDNS binaries and container images for LoongArch64                                                        |
| [cri-tools-loong64](https://github.com/kubernetes-loong64/cri-tools-loong64)                               | CLI tools (crictl, critest) for container runtimes on LoongArch64                                            |
| [etcd-loong64](https://github.com/kubernetes-loong64/etcd-loong64)                                         | etcd binaries and container images for LoongArch64                                                           |
| [gitlab-runner-loong64](https://github.com/kubernetes-loong64/gitlab-runner-loong64)                       | gitlab-runner-helper container image porting to LoongArch64                                                  |
| [gradle-loong64](https://github.com/kubernetes-loong64/gradle-loong64)                                     | Gradle container images for LoongArch64                                                                      |
| [jdk-loong64](https://github.com/kubernetes-loong64/jdk-loong64)                                           | JDK (Java Development Kit) container images for LoongArch64                                                  |
| [jenkins-loong64](https://github.com/kubernetes-loong64/jenkins-loong64)                                   | Jenkins container images for LoongArch64                                                                     |
| [kubernetes-loong64](https://github.com/kubernetes-loong64/kubernetes-loong64)                             | Kubernetes binaries and container images for LoongArch64                                                     |
| [maven-loong64](https://github.com/kubernetes-loong64/maven-loong64)                                       | Apache Maven container images for LoongArch64                                                                |
| [minio-loong64](https://github.com/kubernetes-loong64/minio-loong64)                                       | MinIO server and mc (MinIO Client) binaries and Docker images for LoongArch64                                |
| [moby-loong64](https://github.com/kubernetes-loong64/moby-loong64)                                         | Docker (Moby) binaries for LoongArch64                                                                       |
| [nexus-loong64](https://github.com/kubernetes-loong64/nexus-loong64)                                       | Nexus Repository Manager container images for LoongArch64                                                    |
| [ossutil-loong64](https://github.com/kubernetes-loong64/ossutil-loong64)                                   | ossutil (Alibaba Cloud OSS CLI) binary for LoongArch64                                                       |
| [plugins-loong64](https://github.com/kubernetes-loong64/plugins-loong64)                                   | CNI plugins for container networking on LoongArch64                                                          |
| [redis-loong64](https://github.com/kubernetes-loong64/redis-loong64)                                       | Redis container images for LoongArch64                                                                       |
| [release-loong64](https://github.com/kubernetes-loong64/release-loong64)                                   | Kubernetes release tooling and build dependency images (debian-base, distroless-iptables, go-runner, setcap) |
| [runc-loong64](https://github.com/kubernetes-loong64/runc-loong64)                                         | runc binaries for LoongArch64                                                                                |
| [runner-tools-base-images-loong64](https://github.com/kubernetes-loong64/runner-tools-base-images-loong64) | gitlab-runner-helper base images for LoongArch64                                                             |
| [submodule-loong64](https://github.com/kubernetes-loong64/submodule-loong64)                               | Monorepo aggregating all LoongArch64 component repositories as git submodules                                |
| [tini-loong64](https://github.com/kubernetes-loong64/tini-loong64)                                         | Tini (init for containers) binaries for LoongArch64                                                          |
| [valkey-loong64](https://github.com/kubernetes-loong64/valkey-loong64)                                     | Valkey container images for LoongArch64                                                                      |

## Container images

See [Container Images](https://github.com/kubernetes-loong64/.github/wiki/images) for the full list of available container images.

## How it works

GitHub Actions workflows clone upstream sources, apply **LoongArch64 (loong64)** compatibility patches, and cross-compile using `gcc-loongarch64-linux-gnu` or native Go cross-compilation in a Debian 13 environment. Releases are triggered by pushing branches or tags following project-specific naming conventions.

See [Discussion #6 — Why Use container: debian:13?](https://github.com/orgs/kubernetes-loong64/discussions/6) for the rationale behind the Debian 13 container choice.

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

All projects are licensed under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
