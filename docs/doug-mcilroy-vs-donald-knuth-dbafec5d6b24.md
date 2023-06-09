# 道格·麦克洛伊 vs 唐纳德·克努特

> 原文：<https://medium.com/codex/doug-mcilroy-vs-donald-knuth-dbafec5d6b24?source=collection_archive---------4----------------------->

![](img/99699a836d8e337e164571730cf2b621.png)

托马斯·科勒

我无意中发现[道格·麦克洛伊展示他的“Unix 老手”](http://www.leancrew.com/all-this/2011/12/more-shell-less-egg/)(你可能需要刷新几次才能加载)，我很敬畏。继续这个故事。

这是一个关于[唐纳德·克努特](https://www-cs-faculty.stanford.edu/~knuth/)的故事，他是“斯坦福”的名誉教授(声音是虚构的)，你可能知道他是一位计算机科学家，他让凯塞尔在 12 秒差距内运行。在这个故事中，Knuth 用 Pascal 写了一个美丽而简单的程序。这个程序的源代码绝对令人叹为观止。说真的:这就像读糟糕的莎士比亚(这对于帕斯卡来说是相当不错的)。无论如何，道格·麦克洛伊被要求审查 Knuth 的代码，在给出一些好的评论后，他卸载了 Knuth，并提出了一个六行 Unix shell 脚本来取代 Knuth 的所有 10 多页(类似于)Pascal。太棒了。

这篇文章以极好的风格结尾:

> 我忍不住再加一段摘录。这是[麦克洛伊的]评论的最后一段:
> 
> Knuth 在这里向我们展示了如何智能地编程，但不是明智地编程。我相信纪律。我不相信这个结果。“他创造了一种工业级的法贝热彩蛋——错综复杂，做工精美，精致到超乎寻常，从一开始就是一件博物馆藏品。”
> 
> 请记住，他说的是关于唐纳德·克努特的。
> 
> 麦克洛伊没有法贝热彩蛋。只是黄铜球。

我们需要停下来欣赏美好——不！ ***伟大的*** 写作。让我想起了[某个人](https://thegoldenmule.medium.com/)。

现在，在现实中，我意识到麦克洛伊和克努特在这里说着两种不同的语言。克努特在展示 [*有文化的编程*](http://en.wikipedia.org/wiki/Literate_programming) ，一种从未真正流行起来的意识形态，而麦克洛伊在引用 [Unix 宣言](http://en.wikipedia.org/wiki/Unix_philosophy):一种像野火一样流行起来的意识形态*。我不认为这两种理念必然是不一致的——麦克洛伊的评论清楚地表明了这一点 Knuth 很可能已经编写了一个坚持这两种理念的程序。麦克洛伊谈论的是编程的一个方面，这个方面有点难以确定:*明智的工作*。*

*这个讨论非常类似于[越差越好](http://dreamsongs.com/RiseOfWorseIsBetter.html)哲学，我们可以用格言“简单胜于正确”来概括。*

*来自麦克洛伊:*

> *上面给出的 ***简单*** 管道将足以立即得到答案，而不是下周或下个月。完成这项工作可能就足够了。但是，即使对于一个制作项目，比如说对于国会图书馆来说，这也将是一笔可观的首付， ***对于测试答案*** 的价值以及引出后续问题都很有用。*

*简单？是的。正确吗？嗯，他的代码确实被证明是正确的，但是看起来麦克洛伊甚至不在乎 T21。“正确”这个词通常伴随着一系列偷偷摸摸的假设，但实际上它是一个极具弹性的术语。在时纠正*？纠正*出于什么目的*？正确的**现在**可能意味着一个随机数函数，它总是返回数字 5。为了一个未知的目的，从现在起十年后的修正将需要通过向你的键盘投掷飞镖来编写代码。**

*麦克洛伊的最后一句话是我们实用主义哲学家判断正确性的剃刀:它对检验答案的价值有用吗？*

*这就是麦克洛伊的哲学与标准的 Unix 哲学或更差更好或其他许多其他东西的区别。这是麦克洛伊明智的一课:**答案的价值比实现的价值更重要**。*

*在解决问题方面，我经常失败！比起答案的实际价值，我通常对一个解决方案的阴谋更感兴趣。我刚刚送的*有用吗*？游戏内编程:这个功能*好玩吗*？它看起来真的恶心吗？是的，我看到你的解决方案是完全模块化的，你做了一个非常快速和有趣的数据结构，我无法相信这一切都在 GPU 上(出于某种原因)——但结果的价值是什么？*

*谢谢你。麦克洛伊，为了有帮助的提醒，那个 ***实现的辉煌是乘以答案*** 的值。*