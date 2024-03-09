---
layout: default
title: 架构概览
nav_order: 3
has_children: true
permalink: docs/architecture-overview
---

# 架构概览
---
## 引言
Story Protocol引入了一种革命性的开放可编程IP层，将IP提升为区块链生态系统中的一等实体。这一系统的核心是IPAsset，一个旨在作为每个IP的核心身份的智能合约。这种以账户为中心的方法使得数据的存储和管理以及多样化功能的执行成为可能。开发者被赋予了创建自定义模块的能力，有效地编程IP的行为和互动能力。这些模块充当了IPAsset的"名词"的功能性"动词"，提供了一种统一和标准化的方法来访问和操作IP数据。

Story Protocol融合了IP身份和功能的概念，为公共的、无需许可的区块链上创新和动态的IP管理铺平了道路。

## 架构
![Story Protocol Architecture](/assets/images/sp_architecture.png)
让我们简要介绍上述图表中提到的层次：

### IPAsset（名词）
IPAssets是Story Protocol上的基础可编程IP元数据。每个IPAsset代表一个链上的NFT（代表一个IP）及其关联的IPAccount，这是一个修改过的ERC-6551（Token Bound Account）实现。IPAsset将新的或现有的NFT（如BAYC）转化为一个多功能的、互动的IP实体。

[了解更多关于IPAssets]

### IPAccount
IPAccounts是代表各自NFT的链上可编程IP，采用Story Protocol对ERC-6551的修改实现。例如，一个Mad Lad NFT将有一个关联的IPAccount，其所有者是那个Mad Lad NFT的所有者。

Story Protocol内的所有互动都围绕IPAccounts进行，协议专注于启用以IPAccount为中心的系统。许可、收入/版税分享、重混和其他关键功能都是因IPAccount的可编程性而成为可能。

IPAccount的一个关键特性是通用的execute()函数，它允许通过编码字节数据调用Story Protocol内的任意模块（因此可扩展至未来的模块）。此外，还有executeWithSig()函数，使用户能够签署交易并让其他人代表他们执行，以实现无缝的用户体验。

[了解更多关于IPAccounts]

### 模块（动词）
模块是自定义程序（智能合约），定义和扩展Story Protocol中IPAccounts的功能。作为"动词"作用于"名词"（IPAccount），模块赋予开发者创建每个IP的函数和互动的能力，使IP真正可编程。

[了解更多关于模块]

### 注册表
"注册表"作为Story Protocol全局状态的主要目录/存储功能。与管理特定IP状态的IPAccounts不同，注册表监督协议更广泛的状态。

[了解更多关于注册表]

### 访问控制器
访问控制器管理Story Protocol中所有与权限相关的状态和权限检查。特别是，它维护权限表和权限引擎，以处理和存储模块之间以及来自IPAccounts的调用的权限。

[了解更多关于访问控制器]

### 应用层（生态系统）
该层包括在Story Protocol之上构建的应用，用于IP业务，如分发、发现和共创。

[了解更多关于生态系统]: https://docs.storyprotocol.xyz/docs/access-controller
[了解更多关于IPAccounts]: https://docs.storyprotocol.xyz/docs/ipaccount
[了解更多关于模块]: https://docs.storyprotocol.xyz/docs/modules-1
[了解更多关于注册表]: https://docs.storyprotocol.xyz/docs/registry
[了解更多关于访问控制器]: https://docs.storyprotocol.xyz/docs/access-controller
