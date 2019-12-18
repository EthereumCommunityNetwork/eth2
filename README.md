---
description: 以太坊正在迈向全新未来——Eth2。我们会在此跟进以太坊2.0的最新研发进展以及开发团队等相关信息。
---

# ETH2.0概览

以太坊下一步的重要网络升级称为 Ethereum 2.0，eth2 或 Serenity，将带来分片 \(Sahrding\)、权益证明共识机制 \(Proof of Stake\)、新虚拟机 \(eWASM\)等重大改变。

首先我们需要明确的是，**eth2升级并非一蹴而就，而是划分成多个阶段逐步进行。**以下内容旨在提供eth2的阶段概况参考，让关注以太坊的爱好者们对升级路线心中有数。

## Eth2的设计原则及目标

#### ⚖ 设计原则

Vitalik Buterin给出的[Ethereum 2.0设计原则](https://notes.ethereum.org/9l707paQQEeI-GPzVK02lA?view#Principles)：

* **Simplicity 简洁性：**特别是由于加密经济 PoS 和二次分片 \(quadratic sharding\) 在本质上很复杂，因此协议应该在其决策中尽可能地追求最大的简洁性。这是非常重要的，因为这将能够：

  * \(i\) 最大限度地减少开发成本，
  * \(ii\) 减少发生意外安全问题的风险，
  * \(iii\) 使得协议设计人员更容易让用户确信参数选择的合法性。

  通过[此链接](https://radicalxchange.org/blog/posts/2018-11-26-4m9b8b/)可以了解相关背景信息。当实现特定级别的功能时，我们无法避免一定的复杂性。复杂性的优先级别是：Layer2 协议的复杂性 &gt; 客户端实现的复杂性 &gt; 协议规范的复杂性。

* **Long-term stability 长期稳定性：**理想情况下，应该构建较低级别的协议，这样就不需要在 10 年或更长时间内更改协议，并且任何需要的创新都可以在更高的级别 \(客户端实现或 Layer2 协议\) 上进行。
* **Sufficiency 丰富性：**在协议之上应能够构建尽可能多的应用程序类别。
* **Defense in depth 深度防御性：**协议应能够在各种可能的安全性假设 \(例如网络延迟、故障数量、用户动机等\) 情况下持续运行。
* **Full light-client verifiability 轻客户端可验证性：**鉴于一些安全性假设 \(例如网络延迟、攻击者预算界限、诚实验证者占少数等\)，验证 O© 数据 \(理想情况是只验证信标链\) 的客户端应该能够获得间接的保障：即使是在受到 51% 攻击的情况下，整个系统的所有数据可用且有效 \(注：这是达到“深度防御性”的其中一个目标\)。

#### 🎯 设计目标

以太坊研者Danny Ryan就Ethereum 2.0给出了五个不同的[设计目标](https://github.com/ethereum/eth2.0-specs#design-goals)：

* **Decentralization 去中心化：** 允许处理能力达 _O\(C\)_ 的消费级笔记本电脑处理/验证 _O\(1\)_ 个分片（可能是系统上任何一层的验证，如信标链）；
* **Resilience 强韧性：**在主网分区之后，即使大部分节点离线，整个系统依旧能够运行；
* **Security** **安全性：**通过密码学技术和设计技术提高验证者的总人数和单位时间内的参与者数量；
* **Simplicity** **简洁性：**最大程度地降低复杂性，哪怕会导致效率有所下降；
* **Longevity** **持久性：**选用的组件要能够抵抗量子计算，或是选用可替换型组件直到可用的抗量子计算组件出现。

## Phase 0

[阶段0](https://github.com/ethereum/eth2.0-specs#phase-0)的主要任务是启动信标链 \(Beacon Chain\)。作为eth2的核心，信标链将为其自身和将来所有的分片链管理Casper权益证明协议，引导着eth2其他所有方面的发展。

正如[Ben Edgington](https://media.consensys.net/state-of-ethereum-protocol-2-the-beacon-chain-c6b6a9a69129)所提到的，该阶段的工作涉及许多方面，包括管理验证者及其押金、选择区块提议者、组织验证者进入委员会、对提议区块进行投票、应用共识规则、验证者的奖惩机制、促进跨分片交易等。

信标链上的主要负载来源将是“证明” \(attestations\)。证明是针对分片区块可用性的见证信息，同时也是信标区块的PoS见证信息。当一个分片区块取得了足够数量的证明，将创建一个“交联” \(crosslink\)，该“交联”可以确认将信标片段（到该分片区块为止）整合到信标链中。

阶段0将使用 Caspe FFG \(the Friendly Finality Gadget/友好的最终确定性小工具\) 来保障最终确定性 \(finality\)。简单来说，最终确定性意味着某项特定操作一旦完成，就将永远铭刻在历史中，并且无法还原。

## Notice:

由于以太坊基金会团队和第三方团队的相关信息更新频繁，因此许多文档都将不定时更新，请留意我们的最新跟踪。

