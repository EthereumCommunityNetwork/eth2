---
description: 针对Eth2 验证者的一些常见问题解答
---

# 验证者 FAQ

## 验证者常见问题

####  **1.  什么是 “验证者” \(validator\)？**

验证者是参与以太坊 2.0协议共识的实体。用大白话来说，即运行特定计算机程序的人。该程序会提议并证明新的区块，使之能添加到区块链上。

换言之，你可以将验证者看作新区块的投票者。一个区块获得的票数越多，被添加到区块链上的可能性就越大。重要的是，验证者的投票权重由其质押余额决定。

何为验证者节点：每个客户端都包含两个软件。第一个是节点软件，它负责处理网络共识，它与外部世界连接，并发送和接受区块。第二个是验证者客户端，它与你的节点连接，并负责证明与提议区块。每个验证者客户端上都可以有非常多个质押了32个ETH的验证者。如果你想质押64个ETH，你不需要运行2个节点或2个验证者客户端。

####  **2. 什么是存款合约 \(deposit contract\)？**

你可以将存款合约理解为以太坊账户与ETH 2.0验证者之间的资金转移。存款合约的状态注明了谁为质押者、谁为验证者、质押金额、以及谁有权限提款。

####  **3. 为什么验证者需要质押存款？**

验证者需要质押存款，这样才能对他们的不当行为进行惩罚。换言之，为了保证这些验证者都遵守协议，他们的不当行为需要承担一定经济后果。

#### **4. 验证者需要质押多少ETH?**

验证者在开始维护网络之前，需要质押32个ETH。这32个ETH就是验证者的初始余额。

#### **5. 质押多于32个ETH会有什么好处吗？**

没有，单个验证者存入超过 32 ETH 不会获得任何优势。将质押的最大ETH数额限制到32个有助于提高去中心化程度，因为它防止任何一个验证者有过大的投票权重。请记住，验证者的投票权重取决于其质押余额。

#### **6. 我可以暂停运行 \(而非退出网络\) 我的验证者节点几天，然后再重新开始吗？**

可以的，但正常情况下你会损失一定数额的ETH，大概相当于你在那段时期赚取的ETH数量。换言之，如果你赚取了大约0.01个ETH，那么你将损失大约0.01个ETH。

#### **7. 我应该什么时候补充我的验证者余额？**

这个问题的答案很大程度取决于你余额还有多少ETH。如果你的余额接近16个ETH的话，你当然应该再存入：这是为了确保你不会被验证者集踢出 \(如果你的余额低于16个ETH的话，你会被自动踢出\)。如果你的余额接近31个ETH，你大概不需要再存入ETH以达到32个

#### **8. 我什么时候可以提款，退出与提款有什么区别？**

你可以用你的验证者节点签名一条自愿退出信息以示意你想要停止验证。

但是请记住，在阶段0里，一旦你退出了就回不去了。

你不能再激活你的验证者节点了，在阶段1.5之前你也不能转移或提取你的资金

\(这意味着在阶段1.5之前你都无法访问你的资金\)。

#### **9. 我是否总是需要运行一个Eth1节点来运行一个Eth2验证者节点？**

在eth1-&gt;eth2合并之前，你都需要运行一个Eth1节点，合并后，Eth1节点就会被抛弃，而Eth2节点就是以太坊节点。

#### **10. 在ETH 2上质押需要运行一个ETH 1全节点吗？轻客户端可以吗？如果你的ETH 1节点掉线了会怎么样？**

是的，你需要一个ETH 1节点，轻客户端也可以，但是同步轻客户端有时候会容易出问题。如果你没有一个ETH 1节点，你可以继续证明，但你不可以提议区块。

#### **11. 有没有开箱即可用的节点工具箱可买吗？**

有的，Dappnode和Avado提供了一些不同的选择。

#### **12. 怎样追踪我质押了的 ETH 以及我的奖励？**

已经有一些很好的浏览器如 beaconcha.in 和 beaconscan.com 来追踪验证者节点的工作情况。你也可以在本地上安装 Prometheus 和 Grafana 来创建一个dashboard 来追踪你的验证者节点的工作状况，或者在验证者客户端的输出设备上查看。

#### **13. Staking 的年化率 \(APY\) 如何？**

你所获得的总年化率根据网络上质押的 ETH 总额而变化。可以访问该网址：

https://beaconcha.in/calculator 来计算质押的 ETH 总额会如何影响你的收益率。

\(译注：Launchpad官网中也有年化率的动态预测[https://launchpad.ethereum.org/](https://launchpad.ethereum.org/)\)

#### **14. 质押有什么风险？**

质押存在很多风险，但通过学习如何有效运行验证者节点和注意小心谨慎，多数风险都是可以规避的。

➤ 罚没——被罚没当然很可怕，但这很容易可以避免。不要故意发起一个可罚没的攻击，以及不要同时在2个验证者客户端上运行一个验证者密钥。

➤ 怠工惩罚——怠工惩罚与离线时间相关。你需要逐步确认你的质押设置是安全的。实现步骤在上文的硬件指南里已详细说明。

➤ 系统问题——这是最难规避的风险。这个风险像是在客户端里的一个严重漏洞，或是ETH2规范里的一个缺陷。我们一直在做的测试网工作以及整个ETH 2的开发过程都在为了消除这种风险努力。

#### **15. slot、epoch和区块是怎么运作的？**

每12秒会产生一个新slot。在每个slot里，某个验证者会被随机选出做区块提议。如果该名验证者在线，就可以做提议，然后生成一个新区块。32个slot组成一个epoch，一个epoch有32个区块。如果一切运行顺利，每个slot会出一个区块，一个epoch里就会有32个区块。如果在一个epoch里至少有66%的验证者进行投票，那么之前的那个epoch就会被敲定。两个连续的epoch被敲定会使得之前那个epoch以及里面的所有交易被敲定。

## 验证者职责篇

#### **1. 验证者保持活跃和诚实会有什么激励吗？**

除了离线会被罚款外，验证者的恶意行为也会遭受惩罚，例如投票给无效或冲突的区块。另一方面，如果验证者提议或证明的区块被打包到链上，他们就会得到奖励。

基本规则如下：帮助网络达成共识的行为会得到奖励妨碍共识达成的无意行为 \(或不作为\) 会招致轻度惩罚；恶意行为会招致严重惩罚 \(也称为罚没\)

换言之，验证者在最大化他们的奖励时就是在为整个网络带来最大的裨益。

#### **2. 奖励/惩罚是如何发放的？**

请记住，每个验证者都有自己的余额——初始余额会在存款合约里显示。以太坊网络规则会基于验证者的履职情况定期更新其余额。换言之，奖励与惩罚会随着时间反应在验证者的余额中。

#### **3. 奖励/惩罚多久更新一次？**

大约每6.5分钟\(即一个epoch\)更新一次。在每个epoch里，网络都会评估每个验证者的表现，并相应给予奖励或惩罚。

#### **4. 奖励/惩罚金额有多大？**

这个问题很难回答，因为在计算时需要考虑很多因素。理论上，影响验证交易所得奖励的最主要因素是在网络的质押总额\(即，验证者总数\)。根据质押总额，验证者的最高年收益率可能在 2% 至 20% 之间。

在验证者总数固定的情况下，奖励/惩罚主要取决于验证者的余额规模 —— 如果提供证明的验证者的余额越高，验证者收到的奖励/惩罚金额就越高；余额越低，奖励/惩罚就越低。

请注意，这种动态机制是以不那么明显的方式运作的。要想了解其具体原理，你先要理解有效余额\(effective balance\) 这个概念。如果你对这个概念还不熟悉，我们建议你阅读这篇文章。

#### **5. 为什么奖励取决于网络中的验证者总数？**

区块奖励是根据质押在网络中的ETH总量按比例动态计算的。简单来说，如果质押的ETH总量很少，奖励（利率）就很高，但是随着质押的ETH增加，每个验证者所获得的奖励（利率）就会降低。

为什么要用这种动态调整？尽管本文不会深入其中的细节，但一个主要原因是网络的良好运转需要一定数量的验证者来维持 \(ETH总质押量也是\)。因此，为了鼓励更多的验证者参与其中，在达到必要的验证者数量前维持高利率显得尤为重要。

此后，我们仍然鼓励更多的验证者参与 \(越多验证者参与意味着网络的去中心化程度越高\)，但这不是必要的 \(因此利率可能会下降\)。

#### **6. 如果离线，验证者会遭到什么惩罚？**

这视情况而定。除了有效余额的影响外，还需要主要以像两种重要情况：

1. 如果绝大多数（2/3）验证者都在线，离线招致的惩罚会较低，因为有足够多的验证者在线，可以实现区块的最终确定性。这是预料之中的情况。
2. 如果有超过 1/3 的验证者同时离线，离线惩罚就会较高，因为网络无法继续实现区块的最终确定性。这种属于不太可能发生的极端情况。

请注意，如果是第二种 \(不太可能的\) 情况，离线验证者在 21 天内损失的ETH可高达 50% \(16 ETH\)。21 天之后，这些验证者就会被逐出验证者池。这样一来，网络就可以恢复正常，开始达成区块的最终确定性。

罚没和怠工惩罚 \(inactivity leaks\) 是两种不同的惩罚。如果你主动地投了不正确的票，你便会受到罚没。而如果你离线了，你便会受到怠工惩罚。怠工惩罚力度非常轻，大概等于你在线时获得的奖励。

#### **7. 诚实验证者需要在线多长时间才能实现盈利？**

总的来说，只要验证者的在线时间超过 50% ，就能实现盈利。这意味着验证者不需要使用后备客户端或多余的网络连接来达到极长的在线时间，因为离线的后果并没有那么严重。

#### **8. 作恶的验证者会遭受什么惩罚？**

同样视情况而定。恶意行为 \(例如，投票给无效或有冲突的区块\) 会让验证者遭到罚没。在早期最低罚没金额是0.25 ETH ，之后会恢复至1 ETH的低限，但是如果其他验证者在同一时间也遭到罚没，这一金额会增加。这样设计的目的是尽可能减少验证者因无心之失而蒙受的损失，但同时有力防止协同攻击。

#### **9. 罚没是什么？**

罚没有两个作用：1\) 大幅提高攻击 ETH 2.0 的成本，使攻击无利可图；2\) 通过检查验证者是否履行其职责来防止他们偷懒。

对验证者进行罚没，指的就是如果有验证者被证明作恶，他们的部分或全部权益就会被销毁。遭到罚没的验证者无法继续参与网络的共识机制，会被强制退出。

#### **10. 如果我错误地设置了我的节点，我会有罚没风险吗？**

是的，会有一些风险。用户遭遇罚没的最常见操作是用一个验证者密钥同时运行两个不同的验证者客户端。你需要确保你的设置不会有这种情况发生。

## 密钥篇

#### **1. 如何生成以及保存我的密钥？**

生成密钥的最佳方式就是通过以太坊基金会Launchpad。可以通过离线保存助记词来保护你的提款密钥，可以记在纸上或者保存在一种类似于Eth1密钥的雕刻钢片上。你可以通过确保你的计算机已安全地设置好来保护你的验证者密钥。

#### **2. 签名密钥 \(signing key\) 丢失了会有什么后果？**

如果签名密钥丢失，验证者将无法继续提议或证明区块。慢慢地，验证者的余额将逐渐减少，因为验证者由于无法参与共识流程而受到惩罚。当验证者的余额减少至16 ETH时，系统便会自动将其逐出验证者池。

然而，这并不意味着验证者要失去质押的所有ETH了。假设验证者是通过EIP2334 \(根据默认的引导流程\) 生成其签名密钥，那么验证者总是可以根据提款密钥重新计算其签名密钥。

然后就可以凭借提款密钥提出那16个ETH了，大概要一天后提款才能到账。请注意，如果同一时间退出或被逐出网络的验证者太多了，等待时间将会更长。

#### **3. 提款密钥 \(withdrawal key\) 丢失了会有什么后果？**

如果提款密钥丢失了，验证者将无法访问质押的ETH了。因此，建议验证者使用助记词 \(mnemonics\) 来创建提款密钥，作为备份。如果验证者是通过此Launchpad的引导流程加入的，其提款密钥将默认通过助记词创建。

#### **4. 提款密钥被盗取了会如何？**

如果提款密钥被盗，盗窃者可以转移验证者的余额，但只能在验证者退出之后才能进行此操作。如果盗窃者没有签名密钥，那么其无法强制验证者退出。这时验证者先凭借签名密钥快速退出验证者节点，然后在盗窃者之前凭借提款密钥将资金转走。

#### **5. 为什么要有两个密钥?**

简而言之，就是为了安全。签名密钥必须保证随时可用。因此，签名密钥必须保持在线。由于保存在线上的东西尤其容易受攻击，因此不建议同时用签名密钥进行提款。

#### **6. 我可以把密钥存在硬件钱包里吗？**

对硬件钱包的支持究竟会如何发展到目前为止还是个问号，不过Ledger已经更新了其规范，以支持 Eth2 密钥。在未来，硬件钱包支持 Eth2 几乎是可以肯定的。  


## 参考来源

[r/ethstaker](https://www.reddit.com/r/ethstaker/comments/ju61pf/ethstaker_faq/?utm_source=share&utm_medium=ios_app&utm_name=iossmf)

[Eth2 Launch Pad](https://launchpad.ethereum.org/faq)





