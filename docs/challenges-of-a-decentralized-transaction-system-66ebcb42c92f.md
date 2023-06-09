# 分散交易系统的挑战

> 原文：<https://medium.com/coinmonks/challenges-of-a-decentralized-transaction-system-66ebcb42c92f?source=collection_archive---------38----------------------->

![](img/a21cb6f85c8d2cb74ddf905118cd5cba.png)

在之前的文章中，我们看到了区块链背后的动机。在本文中，我们来看看分散式数字金融交易系统面临的挑战。

正如我们在上一篇文章中看到的，在传统的数字交易系统中，存在一个中央分类账，其可信任程度部分类似于银行。该分类帐通常是一个包含用户及其交易信息的数据库。当交易发生时，货币被添加到属于交易中所涉及的用户的账户中或者从属于交易中所涉及的用户的账户中扣除。交易系统还验证用户的账户中是否有足够的资金进行交易。

如果我们想要分散数字交易，那么我们将不再拥有集中账本的奢侈，它充当了单一的真相来源。因此，我们无法知道用户是否是他们所声称的人，以及他们的帐户中是否有足够的钱发送给另一方。这些是分散式数字交易系统应该应对的挑战。

为了深入了解这些挑战，让我们来看看如何分散数字交易。

# 分散系统中的裂脑问题

分散交易的一种方法是给每个用户一份交易分类帐的副本，并让每个用户在将交易添加到他们的分类帐之前验证每笔交易的有效性，这样任何一方都不能控制整个系统。但这将导致真理的多重来源。如果分类账之间存在差异，我们如何判断哪个是真的，哪个不是？

比如说，我想把钱打到一个账户上。我指定收款人的身份和金额，并向每个用户广播交易。理想情况下，所有用户都应该收到广播交易，并相应地更新他们的分类帐。但是假设由于网络问题，一半的用户没有接收到事务广播。现在，有两个不同的用户群，有两个不同版本的分类账。这被称为[一个裂脑问题](https://en.wikipedia.org/wiki/Split-brain_(computing))。那么，我们如何决定哪个是正确的，哪个不是呢？我们如何让所有用户对分类账达成一致，或者用更专业的术语来说，我们如何建立共识？

# 双重支出

这种大脑分裂的问题导致了重复支出的问题。当使用实物货币时，人们可以确保花掉的钱不能再花掉。也就是说，如果我用 10 张 100 卢比的钞票支付 1000 卢比来买书，我就没有办法再花这 10 张 100 卢比的钞票了。这个被称为重复消费的问题在实物货币中并不存在。当然，我可以印刷钞票，但伪造货币不是一件容易的事情，也是一种应受惩罚的罪行。

不过，在大脑分裂的问题中，我可以把同样的钱寄到两个不同的账户。让我们看看它是如何发生的。假设我花 1000 卢比在网上买书。现在，这个事务将被广播给所有用户。现在，和我们之前的例子一样，只有一半的用户接收到这个广播。假设我们的接收者是接收广播的用户之一。因此，我的付款将被确认，这本书将被发送。

确认后，我可以立即更改我自己的分类帐(因为它是我的)来删除上述交易，并使用相同的 1000 卢比进行另一次在线购买。假设这个接收者没有接收到我之前的广播，但是接收到了最新的广播。由于收件人不知道我之前的交易，我的付款将再次确认，产品将被发送。现在，我会用同样的钱买两种产品，或者换句话说，我会重复消费。

# 交易的顺序

上面的例子也说明了交易顺序的重要性。假设我在两次不同的交易中同时向两个不同的账户，即账户 A 和账户 B 发送相同的 1000 卢比，账户 A 在接收到账户 B 的交易之前接收到交易，账户 B 在接收到交易之前接收到交易，那么账户 A 和 B 都将接受我的交易。这也让我可以加倍消费。所以，所有的分类账都应该以同样的顺序记录交易。

# 在分散式系统中认证用户

去中心化的另一个关键问题是认证交易。如果我广播一个交易，其他用户怎么知道我是我声称的那个人。另一个用户广播一个自称是我的交易怎么办？当然，在集中式系统中，我们可以让用户提供他们的登录凭证来认证他们。但是，当系统是分散的时，您不能私下存储登录凭证，如用户名和密码，因为分散系统中的一切都是公开的，每个人都可以使用。

总之，在分散的数字交易系统中，在所有用户之间就分类帐的状态达成共识是最重要的挑战之一。所有用户都应该有相同的系统视图。也就是说，他们应该把所有曾经发生过的交易以同样的顺序记录在他们的分类账中。此外，验证用户的真实性也是一大挑战。

在本文中，我们讨论了分散式数字交易系统所面临的挑战。在接下来的文章中，我们将看到区块链如何应对这些挑战。

*原载于 2022 年 3 月 25 日*[*【https://www.thearmchaircritic.org】*](https://www.thearmchaircritic.org/mansplainings/challenges-of-a-decentralized-transaction-system)*。*

> 加入 Coinmonks [电报频道](https://t.me/coincodecap)和 [Youtube 频道](https://www.youtube.com/c/coinmonks/videos)了解加密交易和投资

# 另外，阅读

*   [投资印度的最佳加密软件](https://coincodecap.com/best-crypto-to-invest-in-india-in-2021) | [WazirX P2P](https://coincodecap.com/wazirx-p2p)
*   [7 个最佳零费用加密交易平台](https://coincodecap.com/zero-fee-crypto-exchanges)
*   [最佳网上赌场](https://coincodecap.com/best-online-casinos) | [期货交易机器人](/coinmonks/futures-trading-bots-5a282ccee3f5)
*   [分散交易所](https://coincodecap.com/what-are-decentralized-exchanges) | [比特 FIP](https://coincodecap.com/bitbns-fip) | [宾邦评论](https://coincodecap.com/bingbon-review)
*   [用信用卡购买密码的 10 个最佳地点](https://coincodecap.com/buy-crypto-with-credit-card)
*   [加拿大最佳加密交易机器人](https://coincodecap.com/5-best-crypto-trading-bots-in-canada) | [Bybit vs 币安](https://coincodecap.com/bybit-binance-moonxbt)