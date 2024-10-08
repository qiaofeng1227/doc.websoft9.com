---
sidebar_position: 1.0
slug: /design-infrastructure
---

# 规划整体基础设施

使用 Websoft9 托管现代化的企业级云原生应用，需要一套完整、可靠且高效的基础设施作为支撑。  

以下是建立这样一个基础设施时需要考虑的关键组件。

## 云类型

Websoft9 支持在公有云、私有云或混合云上部署，但选择哪种云，应考虑组织的业务、合规和成本需求：

- **公有云**：由专业的第三方服务商提供的云资源，适合需要快速部署和动态伸缩资源的应用。
  - **成本效益**：通常采用按需付费模式，可以根据实际使用来优化成本。
  - **全球部署**：能够在全球范围内部署服务，接近用户以减少延迟。
  - **创新服务**：常有最新的云服务和技术可用。

- **私有云**：组织自建的数据中心或电信托管，满足特定的安全性、合规性或性能需求：
  - **控制**：完全控制你的基础设施，包括硬件和软件。
  - **按需定制**：可以根据具体需求定制环境，包括性能优化和安全性增强。
  - **隐私保护**：数据保留在组织的控制范围内，有助于满足特定的隐私要求。

- **混合云**：结合公有云和私有云的优势，允许数据和应用程序在两者之间流动：
  - **灵活性**：根据需求将工作负载安排到最适合的环境。
  - **成本优化**：对不同的工作负载选择最成本效益的云环境。
  - **业务连续性**：通过在不同云环境之间分配资源，增强灾难恢复能力。

## 云服务器

云服务器是应用托管的直接运行基础，你需要考虑以下因素：

- 性能规格：根据应用的性能需求，选择适当的 [CPU 和内存规格](./install/requirements#server)，预算有限时优先保障内存
- 地域选择：理论上服务器区域尽量在物理位置上与客户地域相近
- 可伸缩性：确保服务器可以根据应用负载自动或手动地伸缩。
- 操作系统：选择支持你的应用程序的操作系统，如 Linux。
- 兼容性：确保服务器支持容器化技术，如 Docker，以及容器编排工具，如 Docker Compose, k8s
- 可用性：选择支持高可用性的云服务，以减少停机时间。
- CPU 架构：确保应用支持常用的 CPU 架构，如 x86-64, ARM 32/64, x86/i686 等
- 私有云虚拟化技术：私有云架构中，选择 KVM, VMware, VirtualBox, OpenStack 等主流虚拟化架构


## 快照备份

定期的快照备份可以防止数据丢失，并允许快速恢复到一个已知的良好状态。

- 自动化备份：设置自动备份策略，以定期创建系统和数据的快照。
- 备份策略：根据业务需求制定备份频率和保留策略。
- 恢复测试：定期进行恢复测试，确保备份是有效的。

## 网络

网络是云原生应用的核心，需确保网络的安全性、可靠性和性能。

- 组网：设计一个适合应用架构的网络拓扑，包括子网划分和网络隔离。
- 安全组：配置安全组以限制不必要的入口和出口流量，增强安全性。
- CDN：使用内容分发网络（CDN）来缩短用户和服务之间的距离，提升访问速度和用户体验。
- 负载均衡：部署负载均衡器以分散流量，确保服务的高可用性和可伸缩性。
- 带宽：[选择足够的带宽](brandwith-infra)可以大幅度提升托管的成绩

## 磁盘与存储

根据所托管的应用对的存储需求，选择适合的磁盘和存储解决方案：

- 持久存储：对于需要持久化的数据，选择支持持久卷的存储服务。
- 性能：根据需要选择不同的存储类型，如 SSD 用于高 IOPS 需求。
- [扩容优化](./storage)：提前规划磁盘容量和存储方式可能的变化。

## API

自动化可以提高应用托管的效率，而自动化的基础是通过 API 管理基础设施

## 域名

域名是用户访问云原生应用的入口：

- [准备可用的域名](./domains)：选择一个易于记忆且相关的域名，并进行注册、认证和备案
- [设置应用的域名](./domain-set#wildcard)：域名解析并绑定到 Websoft9 控制台


## 安全与合规性

在所有这些基础设施组件上，安全性是不可或缺的。

- **身份和访问管理**（IAM）：确保只有授权用户才能访问资源。
- **加密**：在传输和静态数据上实施加密，保护敏感信息。
- **监控和日志**：实施监控系统来跟踪性能和安全事件，并保留日志以供审计。
- **合规性**：遵守行业标准和法规要求，如GDPR、HIPAA等。

通过仔细规划和实施上述基础设施组件，你可以为你的 Websoft9 云原生应用打下一个坚实的基础。   

这不仅有助于确保应用的平稳运行，还可以提升用户体验，最终推动业务成功。