# “数学和编程有什么关系？”

> 原文：<https://medium.com/codex/what-does-mathematics-have-to-do-with-programming-4879fd87cb55?source=collection_archive---------5----------------------->

## 一篇我想写很久的帖子，即使是作为一个不擅长数学的人

![](img/0ce16616e9982ef995940cbac39d99c9.png)

自从在 StackExchange 上发现[这个宝石](https://softwareengineering.stackexchange.com/questions/136987/what-does-mathematics-have-to-do-with-programming/137075)后，我已经拖延了一周又一周的时间来写这篇文章。*为什么我们需要数学*才能成为程序员这个问题是人为的，但是有人以一种有趣的方式回答了它们之间的关系:

> 首先:我是一名数学家——一名专业的数学家(因为我做数学是有报酬的)。我是**不是**程序员。我确实做过一些编程，但绝对是关于 Cargo Cult 的那种(见对 https://tex.stackexchange.com/q/451/86 的第一条评论和我的回应)，没有任何通常会把我带到这个网站的东西(事实上，我在 TeX 聊天室看到一个链接后，在这里注册发布了这个答案)。
> 
> 我回答的总结是:**数学就是编程**。作为一名优秀的程序员，你可以学到所有这些东西[抽象、视角、形式与功能]。如果你已经学会了这些东西，你会发现数学要容易得多，因为你会明白当我们谈论向量空间中的向量时，它只是类`Vector`的一个实例，这意味着我们可以做`Vector`对那个实例做的所有事情:加、减、缩放等等。这就是为什么我喜欢教程序员数学。但是，作为一名数学家，我想说第一个“抽象”在数学中比在编程中更容易学习，因为数学是对抽象的追求

我不想说我是否同意数学字面上就是编程——我认为这主要是一场术语辩论。我也不想从大脑的角度来谈论数学和编程，他们已经在这一集[SciShow](https://www.youtube.com/watch?v=xPecMsFmEm4)中问过编码是与数学更相关还是与语言学更相关。我欣赏这篇文章的积极态度，以及它鼓励程序员追求数学的非居高临下的热情方式。这种能量，我感觉在行业里缺失了很多。现在我有了这个博客，这个博客主要关注面试问题的编码，这似乎特别有意义。与专业编程更实际的日常需求相比，编写面试问题感觉更“数学化”。

比如定心一个

。

他还引用了洛克哈特的《悲叹》一文，全文链接于此，该文认为我们在学校教授数学的方式是错误的，因为它阻碍了探索，抑制了创造力，并使整个学科变得乏味，而它本应像绘画和音乐这样的艺术形式一样鼓舞人心。

# 面试问题

你有一架无人机位于 XY 坐标平面上的某个地方，你接收到一系列你想要拍照的船只的 XY 坐标。你需要给所有的船拍照。您收到了相机的视野，并且需要返回您将要拍摄的照片的相机偏航角度列表。

这是一个为期一天的编码挑战，而且必须是 C++。我不会提供任何代码，或我的答案，因为我强烈怀疑这是错误的答案。我在想[贪婪算法](https://en.wikipedia.org/wiki/Greedy_algorithm)。把你的摄像机对准其中一艘船。拍张照。现在再次移动，直到你到达下一艘在你视野之外的船。

这并不是在所有情况下都是最佳的。

不过，在这个过程中，我发现了一些有趣的事情。我觉得三角学就算不是中学水平也是高中水平，但是你用[反正切](https://stackoverflow.com/questions/15994194/how-to-convert-x-y-coordinates-to-an-angle)把 XY 坐标变成角度。我意识到指令是将 0 度视为北方，顺时针方向，这绝对是一个令人沮丧的挫折。正确的公式其实是这篇帖子最上面的图中的那个，用蜡笔画的。

# 四处打听

将编程视为一种数学形式使这种努力合法化。数学很难——它需要细致、精确，以及专注于那些似乎偏离外部世界、进入自身内部逻辑的问题的能力。数学是如此困难和令人困惑，事实上，我遇到的唯一一个喜欢它的人是住在我大学宿舍对面的女人。出于某种原因，她主修数学。

> 我会说[他们是相似的]。我喜欢解谜和解决问题，这当然是维恩图的中心。抱歉，我不能给你更多的报价。[请给我化名]洛奇。
> —洛基

这就是她的反应。我问过的大多数人对此都不太感冒。顺便说一句，他们中的一个在大学时住在我宿舍的隔壁*。这是相当高的楼层。*

![](img/4be1d91d23fec40c344a38690f05445f.png)

四楼是最好的楼层。美好时光。不仅是普通的巧克力饼，还是无糖的巧克力饼。这个 4 月 1 日的笑话是我做过的第七不道德的事情。

> 我:编码其实只是数学吗？我是说，你在声明变量。你在变异状态。你在定义输入和输出
> 基特里斯:嗯，我想说这是更正式的逻辑。不过话说回来，数学不也是如此吗？也许编码和数学就像是表亲，而不是直系祖先/后代。我不知道，我按下电脑上的按钮，直到应用程序工作，他们给我钱

这是太多的别名，甚至对我的口味。托尼简单地问了我们是否会改变数学中的状态。克里斯要求化名为“脆皮”，他说…

…不，不是真的。

假设你的任务是找到一个目标的最小连续子阵列。你确定了一个解，但是你想达到 O(n)的渐近复杂度。你认识到这是一个滑动窗口技术问题。您遵循向右扩展，然后向左扩展的技术，直到不再满足条件。你被 Meta 录用了，你在 Reddit、LinkedIn 和 OKCupid 上吹嘘你的薪水，你开心了一段时间，直到他们意识到你不知道如何让一个

居中。

这项技术由*和一些*数学组成。所需的精度似乎符合数学的精神。但这仍然不完全等同于解决一个数学问题，科技界的一个大辩论是，计算机科学学生是否真的应该被要求学习三个学期的微积分，一个学期的线性代数，以及像组合学这样的高级课程。

# 智力追求

我记得当我在读《T4:我作为量化分析师的生活》的时候，我记得书中的热情给我留下了深刻的印象。他谈到了自己对物理和数学的着迷，最后谈到了股票市场。我把这件事告诉了 Smack，一个可能比我更好的程序员。我们的谈话大概是这样的:

> 我:让我们从现在开始进行智力对话
> Smack:啊，是的。我们还会享受对方放屁的味道吗？我:……你觉得这是装腔作势？不容置疑地

好吧，听我说完。当我们想到编码采访时，我们会想到什么？大部分是武断的胡说***，我承认我自己在算法问题上用过这个术语。我写道，我们可以称 AR 为一个衡量一次采访包含多少武断的废话的指标，而我们则是它包含多少有用的废话的百分比。系统设计面试和实际让你解决相关行业问题的面试，比如如何使一个

居中，在这方面的评分很高。

也许这是一个很好的心态调整。假设您正在前端编写简单的 JavaScript 来呈现通过服务器发送的事件发送的导航数据。什么都没发生。嗯，在这一点上你可以认为这是一个非常符合逻辑的问题。你有一个更小的程序，它接受变量，用函数修改它们，然后执行一个动作。因为这是一个不受欢迎的动作，所以你要散开。你检查可能是一个因素的其他事情，你解决问题，你学习关于这些变量如何转变的相关事实，它们在典型情况下如何使用，它们在这里做什么。最后，您意识到您应用了错误的函数，当您实际看到绘制在地图上的点时验证了这一点。

这个问题看起来很简单，尤其是对你团队的其他成员来说，但实际上相当复杂。您正在使用一个不是您发明的库来应用一个操作，映射，这是您自己没有做过的事情(至少在这个假设的例子中)。有活动部件。这是一个合理的方式来花费你的时间，你不是一个白痴有这个错误。

很多编程都是由一个持续的声音组成的，这个声音会说:“你在做什么？这太愚蠢了。你就是个傻逼。”但是这种工作，尤其是在行业中，包含许多变量(无论是比喻上还是字面上)。将它与数学进行比较只是另一个视角，它很有激励性，因为它提醒我们，我们占据着一个由逻辑支配的领域。如果一件事出了差错，整个事情都可能崩溃。这并不总是容易的，事实上经常非常困难，这使得它成为一个值得的挑战。

# 结束语

有些人，比如洛奇，很容易就进入了编码领域。是的，有时候很有挑战性。是的，肯定是工作。但她因此变得更好了。这个挑战很有意义。

现在，我有大约九个采访可以写给你。保存在 repl.it 上的 JavaScript 挑战示例代码。保存在 repl.it 上的 Java 挑战示例代码。还有我一直在说的 O(1) insert/delete/getRandom 挑战，这是一个 LeetCode 媒体，还有一个 FAANG 的采访，我会在读完《NDA》后分享(或者不分享，如果 NDA 禁止的话)。还有另一个 2Sum 变体，我必须手工完成，因为我不愿意支付 LeetCode premium。

这是一条漫长的道路。不是每个人都想步行。

我只能梦想拥有 StackExchange 上回答提示的人的成熟。

祝大家好运！