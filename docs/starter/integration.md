---
sidebar_position: 1.3
slug: /apps-integration
---

# 连接并集成多个应用

在现代 IT 架构中，孤立的应用会限制企业共享业务数据和实现流程协作，从而降低组织效率。

Websoft9 多应用托管平台旨在通过统一技术约定来部署与管理企业应用，充分考虑了应用之间的连接和集成需求。

## 规划集成的目标

在实现应用集成之前，架构师需要明确集成目标，即确定需要建立哪种类型的应用集成。

Websoft9 关注的应用连接与集成场景包括：

- **流程集成**：从应用系统流程变化的角度进行集成。例如，A 应用某个动作触发 B 应用执行特定操作，协同完成一项业务。
- **数据集成**：为了确保数据的一致性和可用性，从而引起的应用之间的数据的同步。
- **UI 集成**：需要将多个应用的界面全部或部分，集成为一个统一的界面中，提升用户体验
- **依赖集成**：应用之间具有天然的依赖关系导致的集成需求，例如：网站访问统计软件依赖于 CMS 系统

明确所需的集成场景后，接下来就需要为集成创建应用之间可用的连接。  

## 建立应用间的连接

从底层逻辑来看，主要有两种连接方式：

- **内网连接**：通过专用的虚拟局域网络（VLAN）进行连接，确保安全性和高效性。
- **公网连接**：通过互联网进行公开访问，适用于需要广泛访问的应用场景。

### 内网

Websoft9 所有应用的容器共享同一个内部网络，并以 **容器名（container_name）** 作为唯一的网络标识。  

- 容器之间通过 **容器名** 直接连接。
  
  获取容器名的方式：**Websoft9 控制台 > 我的应用 > 应用管理 > 容器**

- 容器与服务器（宿主机）需要通过 docker0 网桥地址（通常是：172.17.0.1）进行连接

  获取 docker0 的方式：：**Websoft9 控制台 > 容器 > 网络** 会列出所有网络，其中 **bridge** 即所需的值。  
 

### 公网

应用之间的公网连接更具有普遍性，毕竟企业的应用不仅仅限于自托管，更多的 SaaS 或其他云服务的使用是必不可少的。

Websoft9 托管的应用可以很方便的发布到公网。

具体参考：

- [访问应用与网络联网](./app-network)
- [配置应用的域名与安全访问](./gateway)


## 实施自动化集成

在现代企业环境中，应用的数量不断增加，手动集成这些应用显然必定耗时耗力、容易出错。

而自动化集优势明显，并发展成为标准化的集成平台即服务（[iPaaS](https://www.ibm.com/cn-zh/topics/ipaas)）。典型的工具包括：

- 开源

    * [n8n](./n8n)：开源流程自动化工具

    * [Huginn](./huginn)：开源流程自动化工具

    * [Activepieces](https://www.activepieces.com/)：开源流程自动化工具

- SaaS

    * [Zapier](https://zapier.com/) ：预制 3000+ 应用集成，是最流行的 SaaS 集成平台之一

    * [Unito ](https://unito.io/) ：预制 30 + 应用集成，最独特的优点是支持双向数据同步

    * [Automate.io](https://automate.io/)：预制 200 + 应用集成，价格经济实惠

    * [Tray Platform](https://tray.io/)：预制 600+ 应用集成，主打自动化和事件驱动的集成引擎

    * [IFTTT](https://ifttt.com/)：企业和家庭自动化

