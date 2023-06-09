# 如何在你的 NFT 合同中实现懒惰铸币

> 原文：<https://medium.com/codex/how-to-implement-lazy-minting-in-your-nft-contract-f20082dda21c?source=collection_archive---------1----------------------->

## *铸造每一件物品。一次一笔交易。而且你不用付油费。*

![](img/b378106a3ae76f5485c71620661a7342.png)

照片由[画板上的](https://unsplash.com/@drawkit?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)插图[和](https://unsplash.com/s/photos/ethereum?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)组成

偷工减料是一种在 NFT 合同中越来越常用的技巧。这是一个单一问题的解决方案:以太坊高得离谱的燃气费。

简单的解释就是将`mint`功能从`onlyOwner`改为`payable`。如果你想得到额外的报酬。否则，你只需要改变`mint`功能，并记住一些其他细节。

![](img/bb5bcda067b5decc7ac3484038f65cf6.png)

NFT 第四大城市——归我所有

# 代码

在我们的例子中，我们将使用一个简单的 OpenZeppelin 向导契约。默认情况下，只有所有者可以铸造新令牌。如果您对可用令牌的数量没有限制，这将非常有用。但是由于大多数 NFT 收藏有一个限制，我们需要检查是否没有达到限制。

一个常规的`safeMint`函数应该是这样的:

只有合同的所有者(你)可以调用它。这将花费你汽油费。你还需要知道把它铸造给谁作为`to`参数。你也不能接受为你独特而美丽的代币付款。

我们需要更改参数，就像我们将项目铸造给调用者一样，或者在函数本身内部更改`msg.sender`。

如果我们希望用户能够铸造多个令牌，我们只需要`uint256 _amount`作为参数，否则，我们不需要任何参数。我们还需要创建一个简单的`for`循环来创建在`_amount`参数中选择的令牌数。

如果我们想接受付款，我们需要使它成为一个`payable`函数，并且我们需要移除`onlyOwner`修饰符，因为我们希望我们的用户铸造他们自己的令牌。

这将给我们一个类似于下面的`safeMint`函数:

# 陷阱

到目前为止，`safeMint`函数看起来不错，但是它有一些缺陷，我们真的需要修复。我将解释为什么以及如何做到这一点。

如果用户愿意，他或她可以在一次交易中铸造*所有*可用的代币。特别是在 Polygon 这样的网络上，这可能是一个问题，因为汽油费不是很高，用户不会这样做。为此，我们需要添加一个`require`语句，该语句只让用户在单次交易中赚取一定的金额。

另一个陷阱，也可以说是更重要的一个，我们没有定价。这将需要一段与上面类似的代码。我们需要核对`msg.value`和我们的价格。

它现在看起来越来越好，但我们可能有另一个问题。大多数 NFT 收藏或 dApps 对可以有多少代币有限制。该声明将类似于每次销售的代币数量，但我们需要用总供应量来检查它。

我们现在已经解决了最常见的问题，并且如果实施得当，消除了它们的影响。整个`safeMint`函数现在看起来像这样(我还实现了一个变量来切换销售):

# 结论

智能合约是使用区块链的一种很好的方式，但由于费用很高，我们希望在某些情况下将它放在我们的用户身上。多边形等链使其成为次要问题。

我们还需要在安全性方面下功夫，努力保护我们的 dApp 免受用户可能尝试的任何恶意攻击，例如铸造所有可用的令牌。

非常感谢您的阅读，祝您度过美好的一天。

*在*[*Twitter*](https://twitter.com/MVissers4)*上查看我的第一张* [*NFT 作品集*](https://www.cryptoconcoctions.com/) *在多边形网上查看。*