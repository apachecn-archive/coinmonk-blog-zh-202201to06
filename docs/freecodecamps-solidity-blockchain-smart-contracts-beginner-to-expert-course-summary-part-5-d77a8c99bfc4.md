# FreeCodeCamp 的可靠性、区块链、智能合约初级到专家课程总结，第 5 部分

> 原文：<https://medium.com/coinmonks/freecodecamps-solidity-blockchain-smart-contracts-beginner-to-expert-course-summary-part-5-d77a8c99bfc4?source=collection_archive---------6----------------------->

为什么理解区块链中的**随机性如此重要？**

![](img/5c8b1aea7f21d415d1b1ba9c39f4fa7e.png)

[Patrick Collins](/@patrick.collins_58673); the Author of the Course

欢迎来到我总结的第五部分！我很高兴你在这里。我写这些文章来分享我从[这门课](https://www.youtube.com/watch?v=M576WGiDBdQ)中学到的东西。

查看该系列的前几部分:

1.  [第一部分](https://kris-ograbek.medium.com/freecodecamps-solidity-blockchain-smart-contracts-beginner-to-expert-course-summary-part-1-3539606eee0e):区块链介绍【第 0 课】
2.  第二部分:介绍 Solidity，混合 IDE，创建你的第一个智能合同。[第 1、2、3 课]
3.  [第三部分](https://kris-ograbek.medium.com/freecodecamps-solidity-blockchain-smart-contracts-beginner-to-expert-course-summary-part-3-fea146841d9a):web 3 . py 简介。
4.  [第四部分](/coinmonks/freecodecamps-solidity-blockchain-smart-contracts-beginner-to-expert-course-summary-part-4-d9bb72a4a6bf):布朗尼**简介**。

在这一部分，我们将学习区块链中的**随机性**。在我看来，第七课是最难完全理解的一课。但这是至关重要的！

## 区块链上是不可能产生随机数的。

是的，你没看错。当你在智能合约中看到“随机性”时，它要么是伪随机的，要么是链外生成的(区块链之外)。只有后者才能是真正的随机。为什么不可能？[这个来自隐型僵尸的教训](https://cryptozombies.io/en/lesson/19/chapter/7)提供了一个很好的答案:

> 作为**链上机制一部分的一切都是由设计**决定的，包括哈希函数。

确定性意味着对于相同的输入，你总是得到相同的输出。来自维基百科:

> 确定性系统是一个不包含随机性的系统。

区块链是一个确定性的系统。这是达成共识的唯一途径。确定性和随机性是互斥的。

## 你为什么要在乎？

如果您对其中一个主题感兴趣，了解随机性在区块链中的工作方式至关重要:

*   **不可替代令牌**
*   **博彩**
*   **赌博**
*   **分散自治组织**

我说的不仅仅是创建这样的应用程序。如果你是这类平台的用户，你会希望确保**RNG(随机数生成器)**是真正随机的。如果他们没有，*你很可能被耍了*。

记住，除了你自己，没人在乎你的钱。如果你在区块链上赔钱，你就永远失去了它。就算证明是恶意活动，你的钱也没了。请，成为一个受过教育的区块链用户。这将在多方面带来回报。

## 更糟的是。

开发人员可能会无意识地以错误的方式实现 RNG。有一种方法可以产生看似随机但实际并非如此的数字。他们是**伪随机**。它为黑客或恶意用户操纵结果打开了大门。帕特里克·柯林斯在 [chainlink 论坛](https://forum.openzeppelin.com/t/understanding-the-meebits-exploit/8281/3)上解释了 Meebits 发生的事情。稍后，我将向您展示*如何不与*生成随机数。

区块链中的随机性是一个本质而复杂的话题。在这篇文章中，我试图强调它的重要性。然而，在一篇文章中详细介绍所有内容是不可能的。我强烈建议你多读书。从[这个以太坊 StackExchange 线程](https://ethereum.stackexchange.com/questions/191/how-can-i-securely-generate-a-random-number-in-my-smart-contract)和[这个 egamers.io 文章](https://egamers.io/chainlink-vrf-is-live-on-ethereum-and-embraces-blockchain-gaming/)开始。

这个介绍比通常的要长。我希望你明白为什么这是必要的。现在，回到课程上来！

让我们开始吧！

# 第 7 课:智能合约彩票

**总结**

系好安全带，因为你将学到很多东西！您将创建一个连锁彩票。起初，我对这一课不抱太大期望。我不是赌徒，所以我想这不适合我。说我错了是一种保守的说法。如果要我选择一个我学到最多的教训，那就是智能合同彩票。不仅仅是随机性。在构造函数中调用过**构造函数吗？你听说过**请求和接收周期**吗？你会在这一课！**

**经验教训**

1.  **一个区块链中的随机性**。关于随机性的介绍已经够长了。让我告诉你**如何**和**如何不**产生随机数。

先说后者。

getRandomNumber() returns a pseudorandom number

让我来分解代码。首先，我们从 nonce 和全局可用变量创建一个字符串:

*   **nonce** :发送方交易次数，
*   **msg.sender** :调用函数的地址，
*   **block . difficult**:矿工要找到一个积木必须解决的一个问题的难度。
*   **block.timestamp** :从 epoch 开始的当前块时间戳，以秒为单位。

这个想法是把一堆变量混合在一起。然后，我们将字符串传递给哈希函数。有两个问题:

*   所有的变量要么是可预测的，要么是可操纵的，
*   我们的**哈希函数是确定性的**。相同的输入将总是返回相同的输出。

记住:复杂的计算不会让它们变得随机！

**如何在区块链中生成随机数？**

这就是**链环 VRF(可验证随机函数)**发挥作用的地方。据我所知，链环 VRF 是唯一真正安全的方式来产生随机数。

让我们展示一个使用 VRF 链生成随机数的最小契约例子。

getRandomNumber() returns a truly random number

什么？所有这些就为了得到一个随机数？是的，恐怕是的。但并没有看起来那么可怕。关键要点是:

*   我们使用 Chainlink 的 **VRFConsumerBase** 契约。它将验证我们收到的是一个真正的随机数，
*   这个契约生活在一个区块链上，所以我们需要它的地址( **address _vrfCoordinator** )，
*   我们必须支付调用合同的费用。对于调用使用 oracles 操作的智能契约，我们使用 Link Token 进行支付。所以我们需要它的地址( **address _link** )，
*   我们传递链接令牌的金额( **uint256 fee** )来调用 requestRandomness()函数，
*   我们需要一个生成随机性的公钥( **uint256 keyhash** )。

这是我们为确定性系统的随机性付出的代价。不仅实现更复杂，而且我们用链接令牌支付。

2.**调用继承契约的构造函数**。如果您正在阅读上面的代码，您会注意到一个奇怪的语法。在我们的构造函数中，我们调用 VRFConsumerBase 契约的构造函数。

让我为你清除代码:

**新术语**

1.  **链环 VRF** 。这是获得真正随机数的安全方法。它包括链上验证合同，以证明你得到的数字是真正随机的。Chainlink VRF 背后的机制超出了本文的范围。如果你想知道更多，请查看 Chainlink [VRF 文档](https://docs.chain.link/docs/get-a-random-number/)和这个[来自隐型僵尸的教训](https://cryptozombies.io/en/lesson/19/chapter/7)。
2.  **请求和接收周期**。我们使用 VRFConsumerBase 中的两个函数:

*   **request randomnes**(key hash，fee):进行随机性的初始请求。
*   **fulfill randomnes**(bytes 32 _ request id，uint256 _ randomness):接收验证过的随机性。

我们称之为获取数据的**请求和接收周期**。理解这一点至关重要:我们从不直接执行 fulfillnommandates()函数。如果你注意到，这是一个**内部**函数。这意味着只有契约本身(在我们的例子中是 **VRFConsumerBase** )可以调用它。我们可以覆盖函数，使用函数传递的随机数；**uint 256 _ 随机性**。要了解更多信息，请查看 Chainlink 的[基本请求模型](https://docs.chain.link/docs/architecture-request-model/)文档。

**技术**

坚固性，蟒蛇皮，布朗尼，链环。

# 最后的想法

还在吗？我为你骄傲！在这一点上，你比大多数用户更了解区块链中的随机性。它应该让你在使用“随机”平台时更加谨慎和多疑。

这是迄今为止我写的关于区块链最难的一篇文章。随机性和链环 VRF 都是复杂的话题。他们每个人都值得一系列的文章。在这本书里，我只触及了表面。我希望我能唤醒你探索更多的好奇心。

你有什么问题吗？你喜欢这种总结吗？请在评论中告诉我！

**参考文献**

[YouTube 视频](https://www.youtube.com/watch?v=M576WGiDBdQ)

[GitHub 回购](https://github.com/smartcontractkit/full-blockchain-solidity-course-py)

[链环 VRF 文档](https://docs.chain.link/docs/chainlink-vrf/)

[在智能合约堆栈交换线程中保护 RNG](https://ethereum.stackexchange.com/questions/191/how-can-i-securely-generate-a-random-number-in-my-smart-contract)

> 加入 Coinmonks [电报频道](https://t.me/coincodecap)和 [Youtube 频道](https://www.youtube.com/c/coinmonks/videos)了解加密交易和投资

# 另外，阅读

*   [加密复制交易平台](/coinmonks/top-10-crypto-copy-trading-platforms-for-beginners-d0c37c7d698c) | [Coinmama 审核](/coinmonks/coinmama-review-ace5641bde6e)
*   [印度的加密交易所](/coinmonks/bitcoin-exchange-in-india-7f1fe79715c9) | [比特币储蓄账户](/coinmonks/bitcoin-savings-account-e65b13f92451)
*   [OKEx vs KuCoin](https://coincodecap.com/okex-kucoin) | [摄氏替代品](https://coincodecap.com/celsius-alternatives) | [如何购买 VeChain](https://coincodecap.com/buy-vechain)
*   [币安期货交易](https://coincodecap.com/binance-futures-trading)|[3 comas vs Mudrex vs eToro](https://coincodecap.com/mudrex-3commas-etoro)
*   [如何购买 Monero](https://coincodecap.com/buy-monero) | [IDEX 评论](https://coincodecap.com/idex-review) | [BitKan 交易机器人](https://coincodecap.com/bitkan-trading-bot)