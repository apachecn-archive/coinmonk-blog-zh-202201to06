# 比特币的工作原理

> 原文：<https://medium.com/coinmonks/how-bitcoin-works-a259c2abf13b?source=collection_archive---------15----------------------->

## 比特币投资

## **20 世纪 90 年代的两项发明是驱动比特币网络的秘方和比特币核心代码**

![](img/303fcd347fa61504011b0a3c9c7593a3.png)

[https://www.bobbyong.com/blog/wp-content/uploads/2014/07/Bitcoin-Network.jpg](https://www.bobbyong.com/blog/wp-content/uploads/2014/07/Bitcoin-Network.jpg)

*这是关于比特币投资的三篇文章之一，它为主要文章“* [*”提供了背景，比特币是不可改变的和安全的，还是脆弱的和有风险的？*](/@IneffableValue/is-bitcoin-immutable-and-safe-or-fragile-and-risky-d5dc412ced2)

著名的基金经理杰里米·格兰瑟姆最近写道，加密货币“在技术上非常复杂……普通人根本无法理解它们，必须相信它们的价值。”我希望，通过一点努力，即使是我们这些非技术“正常人”也能对比特币网络的工作原理有足够的了解，从而理解为什么狂热分子认为比特币是安全、不可摧毁和值得信赖的。

爱好者对比特币的信任来自于 Satoshi 实现比特币的区块链和工作证明(PoW)加密算法的方式。区块链和 PoW 算法都是在 20 世纪 90 年代发明的，并在 Satoshi 与比特币网络一起上线之前完善了近 20 年。让我们来看看 Satoshi 的发明是如何工作的。

## **比特币网络**

比特币是一种去中心化的电子货币，可以通过比特币网络以“无信任”的方式直接从一个数字钱包发送到另一个数字钱包，而不需要银行或托管公司等第三方的参与来解决纠纷或修复故障——因为不存在任何第三方。比特币网络中的每一笔比特币交易都被永久记录在一个名为区块链的公共分散账本中。由于比特币网络的核心是基于共识的 PoW 算法，这个账本在世界各地传播到成千上万个无法篡改的网络节点。

比特币网络是有史以来推出的第一个点对点价值转移系统。比特币是在 2008 年由一个不知名的人或团体用中本聪的名字发明的，他是著名的[比特币白皮书](https://bitcoin.org/bitcoin.pdf)的笔名作者。2009 年，Satoshi 发布了比特币核心，这是一款管理比特币网络运行的开源软件。Satoshi [开采了最初的 genesis 块](https://en.wikipedia.org/wiki/History_of_bitcoin#:~:text=On%203%20January%202009%2C%20the,a%20reward%20of%2050%20bitcoins.)，并获得了有史以来第一批 50 个比特币，这在当时是一文不值的。有史以来的第一笔交易发生在几天后，当时 Satoshi [向一位同事](https://www.investopedia.com/tech/bitcoins-best-use-isnt-currency-its-overseas-remittances/)和另一位加密先驱 Hal Finney 发送了一些比特币，Hal Finney 是继 Satoshi 之后第二个在当时只有两台计算机的网络中运行比特币核心的人。

两种实体组成了比特币网络，并合作维护其安全性和完整性，[节点和矿工](https://www.globalxetfs.com/bitcoin-the-basics/)。在下面的描述中，您将了解到*验证*、*验证*和*确认*——Satoshi 发明的 PoW 协议的三大支柱。

**节点**监管网络，执行对网络安全至关重要的规则，并与其他节点共享关于每个新交易的信息。当一个节点收到一个新的交易时，它*验证*该交易符合比特币网络的规则(例如，发送者的钱包有足够的硬币)。节点可以做到这一点，因为它们维护整个数字总账或区块链的最新副本。这意味着他们知道每一枚硬币和硬币的一小部分从交易到交易，从钱包到钱包的路径，一直追溯到 Satoshi 在 genesis block 收到 50 个比特币的那一天。

在确认一个新的事务后，节点将它保存在它的未决事务的“内存池”中，等待它们被添加到区块链和*确认*的机会。它还将这个经过验证的事务传播到[另外八个](https://nakamoto.com/bitcoins-p2p-network/)随机选择的节点，由它们独立验证。如果一个节点接收到一个[无效的事务](https://learn.saylor.org/mod/page/view.php?id=30778)，它将不会被传播并且会死亡。如果一个行为不当的节点继续发送无效的事务，其他节点将简单地阻止它。

矿工负责将比特币交易合法化，他们将比特币聚合成块，最终由网络确认，并在区块链连接在一起。这需要巨大的计算能力，矿商可以通过出售新铸造的比特币获利。这就是新比特币进入流通的方式。

矿工通过首先从附近节点的内存池中收集[兆字节](https://bitcoinmagazine.com/guides/what-is-the-bitcoin-block-size-limit)的有效交易来寻求奖励，每个矿工独立选择他们的交易。然后，他们相互竞争，竞相将他们选择的事务“密封”到一个与前一个事务相链接的新块中。这需要矿工们利用他们的计算能力来解决一个复杂的密码难题，其数字答案基于他们选择的特定交易，以及前一个块的密封(一种称为“哈希”的密码过程)。生成这个哈希值证明了挖掘器确实执行了 PoW 协议所要求的工作。这个哈希值是密封新块的东西。

第一个完成区块的采矿者将获得区块奖励以及其中单个交易的费用(交易费用越高，采矿者选择和执行交易的速度越快)。然后，该块被传播到整个网络中的节点。每个节点检查该块是否被正确密封——这是一个重要的步骤，称为*验证*。一旦足够数量的节点验证了该块，块内的交易就被确认，并且发送和接收钱包被警告这一点。已核实交易的时间顺序现在已经确定。就像事务一样，未经验证的数据块不会在网络中传播。

为了额外的安全，一些钱包需要在有问题的区块上再确认多达五个区块，才能完成内部的交易。重要的是，一个区块在区块链“越深”，它就越安全，因为在它上面增加区块已经反复证实了这一点。这是因为每一个新的区块都与前一个区块相关联，如果没有这种关联，新的谜题就无法解决。由于挖掘一个新块需要巨大的哈希能力，逆转先前验证的块和其中的交易实际上是不可能的(我们在关于比特币威胁的[主文章](/@IneffableValue/is-bitcoin-immutable-and-safe-or-fragile-and-risky-d5dc412ced2)中讨论了这一点)。这就是为什么比特币钱包经常被编程为在接受比特币交易之前等待多次确认的原因。

以下是我们刚刚讨论过的比特币交易生命周期的图示。

![](img/401a70fb949d4cca22a11d7ab62bd6ca.png)

一开始，可以使用现成的计算机进行挖掘。今天，采矿业是一个大行业。随着比特币价格的上涨，这促使矿工部署更强大的采矿设备来提高他们的哈希能力。如今，大型矿商运营着位于水电站等低成本能源附近的巨型数据中心，许多矿业实体都是上市公司。

在比特币网络建立和运行的 13 年间，矿工们已经赚了近 1900 万比特币，创建了近 72.5 万个区块，全都塞满了交易。[大约 14000 个](https://bitnodes.io/)重要节点执行规则并维护整个区块链的副本。

(有趣的事实:与挖矿不同，任何拥有强大计算机和快速互联网连接的人都可以将比特币核心作为独立节点运行。个人和实体运行节点，因为他们在加强比特币网络方面有着共同的利益)。

比特币网络从未失败或被愚弄过(尽管，正如你将在[的主要文章](/@IneffableValue/is-bitcoin-immutable-and-safe-or-fragile-and-risky-d5dc412ced2)中读到的，几年前，当它更小、更脆弱时，它逃过了几次千钧一发的危机)。支持者指出，网络现在如此庞大，其哈希能力如此强大，以至于比特币区块链是这个星球上最安全的电子数据库。他们说，这使得它不可改变，这意味着几乎不可能伪造比特币。这是支持者将比特币描述为数字黄金的一个原因(关于这一点的更多信息，请参见配套文章“[比特币是健全的货币吗，你为什么要关注它？](/@IneffableValue/is-bitcoin-sound-money-and-why-should-you-care-b3b2be92abd5)》。

当然，随着比特币价格的攀升，更多的矿工加入了这个网络，他们需要越来越多的计算能力来竞争区块奖励。这是战俘区块链的一个特征，而不是一个错误，因为它加强了网络抵御攻击的能力。目前，比特币采矿消耗的电力大约相当于泰国的[国家](https://digiconomist.net/bitcoin-energy-consumption)的电力。一些矿工正试图利用 T2 绿色能源的经济来源，并使用闲置的能源供应，但这是一个缓慢的过程。尽管如此，比特币爱好者指出，采矿实际上可以通过创造需求来帮助平衡和稳定电网，只要电网紧张，需求就会减少。一些人甚至认为比特币类似于“[数字能源](/@jpthor/bitcoin-as-a-store-of-energy-6d850f893bdb)”，因为采矿可以在一个地方吸收能量，并将其传输到另一个地区，通过出售比特币来购买其他地方的能源存储和发电基础设施。

## **比特币核心代码**

比特币的代码是完全开源和去中心化的。任何人都可以使用它，任何软件工程师都可以验证它到底是如何工作的。根据比特币开发者的非正式信息中心 bitcoin.org 的说法，由于这种透明性，“对比特币的大部分信任来自于它根本不需要信任。”

像任何开源软件项目一样，没有人拥有比特币核心。没有一个人或中央权威来规定代码应该如何发展。任何人都可以自由地提议、开发、审查、测试和记录对比特币核心的更改，但只有少数人有“提交权限”将更改上传到托管正式版本的公共存储库。这些[维护者](https://bitcoincore.org/en/about/)通过逐步提升，积累大量的“提交”，或者可接受的代码变更来获得他们的特权。当然，所有提议的代码更改都要经过一个费力的审查和测试过程。

比特币核心新版本的最终质量检查来自节点本身，因为节点可以自由选择是否运行它。大多数新版本都向后兼容以前的版本，尽管有时开发团队发布的版本对协议做了很大的改动。像这样的大型新版本被称为“硬分叉”，因为它们将区块链分成两个具有不同规则的链。[硬分叉](https://freemanlaw.com/hard-and-soft-forks-a-detailed-and-simplified-explanation-of-how-blockchains-evolve/)迫使节点选择是坚持旧协议还是拥抱新协议。

比特币在其短暂的存在期间经历了少量有计划和有争议的硬分叉，每一次都催生了具有不同特征、协议和令牌的[新区块链](https://www.investopedia.com/tech/history-bitcoin-hard-forks/)。最成功的硬分叉创造了[比特币现金](https://www.investopedia.com/terms/b/bitcoin-cash.asp)，这是一种基于分叉区块链的新令牌，它增加了每个区块的大小以加快交易速度。但是最初的比特币区块链仍然是最强大的，最初的比特币代币也是最受欢迎的。

********************

这并不太复杂难以理解，是吗？现在，你对比特币网络的工作原理有了足够的了解，明白了为什么狂热分子认为比特币是安全的、不可摧毁的和值得信赖的，你准备好返回到主要文章，[比特币是不可改变的和安全的，还是脆弱的和有风险的？](/@IneffableValue/is-bitcoin-immutable-and-safe-or-fragile-and-risky-d5dc412ced2)

> 加入 Coinmonks [电报频道](https://t.me/coincodecap)和 [Youtube 频道](https://www.youtube.com/c/coinmonks/videos)了解加密交易和投资

## 也阅读

[](/coinmonks/leveraged-token-3f5257808b22) [## 杠杆代币[多头代币]终极指南

### 杠杆化令牌是具有杠杆化风险敞口的 ERC20 令牌，不考虑保证金、要求、管理…

medium.com](/coinmonks/leveraged-token-3f5257808b22) [](https://coincodecap.com/crypto-exchange) [## 最佳加密交易所| 2022 年十大加密货币交易所| CoinCodeCap

### 哪一个是最好的加密交换？在本文中，我们将根据多种加密货币列出 10 大加密货币交易所

coincodecap.com](https://coincodecap.com/crypto-exchange) [](https://coincodecap.com/best-swap-platforms) [## 2022 年最佳加密交换平台| CoinCodeCap

### 随着时间的推移，我们大多数人将转向 dex 以获得更好的安全性和隐私。因此。在这里，我们将讨论…

coincodecap.com](https://coincodecap.com/best-swap-platforms) [](https://coincodecap.com/best-online-casinos) [## 2022 年最佳加密和比特币赌场(美国批准，存款奖励)

### 接收、支付和赚取加密货币| |有各种各样的最佳在线赌场可供选择，有可能…

coincodecap.com](https://coincodecap.com/best-online-casinos) [](/coinmonks/top-5-crypto-lending-platforms-in-2020-that-you-need-to-know-a1b675cec3fa) [## 2021 年最佳加密借贷平台| 6 大比特币借贷平台

### 获得比特币和其他加密货币的最佳贷款利率

medium.com](/coinmonks/top-5-crypto-lending-platforms-in-2020-that-you-need-to-know-a1b675cec3fa) [](/coinmonks/the-best-cryptocurrency-hardware-wallets-of-2020-e28b1c124069) [## 2021 年 6 大最佳硬件钱包|顶级加密硬件钱包[更新]

### 最好的加密货币硬件钱包是绝对必要的。我们将在 NGRAVE、Ledger Nano X 和…

medium.com](/coinmonks/the-best-cryptocurrency-hardware-wallets-of-2020-e28b1c124069) [](/coinmonks/crypto-trading-bot-c2ffce8acb2a) [## 加密交易机器人——19 款最佳免费加密交易机器人

### 2022 年币安、比特币基地、库币和其他密码交易所的最佳密码交易机器人。四进制，位间隙…

medium.com](/coinmonks/crypto-trading-bot-c2ffce8acb2a) [](/coinmonks/best-crypto-signals-telegram-5785cdbc4b2b) [## 最佳 4 个加密交易信号电报通道

### 这是乏味的找到正确的加密交易信号提供商。因此，在本文中，我们将讨论最好的…

medium.com](/coinmonks/best-crypto-signals-telegram-5785cdbc4b2b)