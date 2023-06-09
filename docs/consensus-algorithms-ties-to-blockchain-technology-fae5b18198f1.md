# 共识算法与区块链技术的联系

> 原文：<https://medium.com/coinmonks/consensus-algorithms-ties-to-blockchain-technology-fae5b18198f1?source=collection_archive---------54----------------------->

在我的训练营经历的第一阶段接近尾声时，我在“底层哈希课程”中做了一些额外的阅读，这将在第三阶段结束时展开。当我浏览哈希函数和冲突部分时，我开始将我所阅读的内容与我对区块链技术的一点点知识联系起来，并推动我更深入地挖掘这个主题及其与算法的联系。

**区块链讲解**

区块链技术本质上是一种不可变的分布式账本，自创世纪以来一直托管所有交易，其核心功能是复制和验证交易的能力，无需任何中央机构。这项技术的核心是共识算法。

![](img/f963dfe809a4012fbe49ce6d47309fda.png)

*“共识算法使网络参与者能够以分布式和无信任的方式就区块链的内容达成一致。”维基百科*

进一步来说，这是一个协议，它通过决定哪些事务是有效的并且可以被添加到链中来确保所有节点彼此同步。一致性算法确保网络中的每个参与者都使用相同的区块链，并且每个块都正常安全地运行。

**三难困境**

各种类型的一致性算法被用来解决影响区块链系统的三个难题:

1.  分散化——区块链将数据和计算能力分配给网络中每个参与者(即计算机)的能力
2.  可扩展性—区块链支持高交易吞吐量同时保持低交易费用的能力
3.  安全性——区块链按照提议工作而不让黑客操纵数据链的能力。

该系统的工作原理如下。交易完成后，会生成交易的唯一地址，即交易哈希。进行的事务以树格式编译，并连接到一个块中。块存储大小因区块链而异，因为每个人都试图解决上述 3 个难题。只要每个散列都是抗冲突的，则在为新块生成加密散列时，来自前一个块的散列将被包括在元数据中，从而使其不可变。至于在向链中添加块之前如何验证每个事务，这取决于所使用的共识算法。下图描述了迄今为止所有常用的共识算法。

![](img/8cbcdb7513d4b26adcd30c71241bf5d3.png)

正如你所看到的，有各种各样的方法来达成共识，但是有一种方法是最重要的，因为它是目前最广泛使用的:工作证明。工作证明是最广为人知的区块链比特币的共识机制。

**工作证明**

原则上，比特币网络上的每个参与者都可以参与区块生成。你不需要拥有比特币才能参与，这与股权证明正好相反。为了确认交易并向区块链中输入一个块，挖掘节点必须通过找到一个随机数来解决计算难题，随机数是一个随机的不重复的值，可以添加到哈希中。矿工使用 PoW 来验证交易和开采新硬币，但其主要目标是阻止网络中任何潜在的网络攻击或可疑活动。

![](img/b176622de6118ffc82e0e5f6fd2aa165.png)

正如许多人所注意到的，PoW 的衰落是给链条增加一个新的区块所需要的能量消耗，从而导致了其他一致实相方法的诞生。

**结论**

尽管我对这个主题很感兴趣，但要深入研究每个共识机制做什么以及节点如何验证事务，需要一篇非常大的研究论文。出于本文的目的，我专门研究了最广为人知且目前使用的工作证明方法。然而，越来越多的区块链已经开始使用利益相关证明，但这种共识本身存在关于权力下放的问题。目前没有完美的解决方案，但我期待看到这个领域的未来。

> 加入 Coinmonks [电报频道](https://t.me/coincodecap)和 [Youtube 频道](https://www.youtube.com/c/coinmonks/videos)了解加密交易和投资

# 另外，阅读

*   [用于 Huobi 的加密交易信号](https://coincodecap.com/huobi-crypto-trading-signals) | [HitBTC 审查](/coinmonks/hitbtc-review-c5143c5d53c2)
*   [如何在 FTX 交易所交易期货](https://coincodecap.com/ftx-futures-trading) | [OKEx vs 币安](https://coincodecap.com/okex-vs-binance)
*   [OKEx vs KuCoin](https://coincodecap.com/okex-kucoin) | [摄氏替代品](https://coincodecap.com/celsius-alternatives) | [如何购买 VeChain](https://coincodecap.com/buy-vechain)
*   [ProfitFarmers 点评](https://coincodecap.com/profitfarmers-review) | [如何使用 Cornix 交易机器人](https://coincodecap.com/cornix-trading-bot)
*   [如何匿名购买比特币](https://coincodecap.com/buy-bitcoin-anonymously) | [比特币现金钱包](https://coincodecap.com/bitcoin-cash-wallets)