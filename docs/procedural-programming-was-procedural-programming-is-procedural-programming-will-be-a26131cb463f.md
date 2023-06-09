# 程序化编程过去是，现在是，将来也是。

> 原文：<https://medium.com/codex/procedural-programming-was-procedural-programming-is-procedural-programming-will-be-a26131cb463f?source=collection_archive---------17----------------------->

## [法典](http://medium.com/codex)

尽管我的中级简历中有这个笑话，但我只是对函数式编程有*的热情*——绝对不是一个狂热分子。虽然单子可能很优雅，但在大多数情况下，它们可能不是表达副作用的最实用的方式。我有点狂热的是让世界摆脱在 Java、C++和其他广泛使用和误用的语言中实现的糟糕的设计和被误解的 OOP (mis)的伪装。

FP 很美，但不是*万能*。这里我的意思是“不通用”在一个脚踏实地，实际的工程意义上。当然，它在数学上是“通用的”——lambda 演算等同于图灵机……但在实际的软件工程中，纯粹的 FP 思维模式并不能真正帮助创建简洁、可读和可维护的代码，这种情况至少和它帮助创建简洁、可读和可维护的代码的情况一样多。

OOP 是……老实说，在艾伦·凯的思想之外，OOP 很有可能从来没有以正确的形式存在过。好吧，我是半开玩笑的，但我们可以肯定地同意，Alan 的思想的淡化版本由 C++实现，随后由 Java 实现，并被世界上数百万的程序员滥用，与它所设想的实际 OOP 相差甚远。

C++、Java 和。NET 生态系统，以及所有其他受其设计影响的语言和框架，在创造数万亿美元的价值中发挥了重要作用。这些语言的一些设计非常有意义，而且正是业界所需要的…回顾历史，要理解 Java 做对了什么，做错了什么，人们只需要研究一下 Go 的语言设计。最值得注意的是，Go 已经抛弃了追随 Alan Kay 理想的愚蠢伪装，取而代之的是从 Java 中一点一点地取出大部分有意义的工具，没有一个是没有意义的。

实现泛型花费了数年时间，但它们最终在管道中。

如果有人问 Go 是哪种语言…它肯定不是“OOP”，也肯定不是“函数式的”…它是一种过程语言，而且它并不孤单。在 20 世纪 90 年代和 21 世纪初，“程序性”经常被用作一个粗略的词。这意味着不可读的意大利面条代码，不可辨认的命名不当的全局变量总机，各种隐藏状态，`goto`语句和其他过去的恐怖。它意味着汇编或 BASIC 语言的所有痛苦和挫折。这意味着旧的和尘土飞扬的 C 和 Pascal，而不是新的和华而不实的 C++或 Java。但是当这个名字变成了一个诅咒，许多错误的决定都是为了逃避它……它真的被逃避了吗？

如果你从过去三十年中用这些语言编写的所有软件的语料库中随机选择任何 Java 代码或 C++代码，你几乎肯定会发现*过程化*代码:大型任务被分解成一系列更小的连续任务——这些任务又可能是被分解成更小组件的复杂任务……并且将所有这些放在一起，就是过程和过程调用的概念。我也不关心这个过程是否封装在一个带有 state 的名称空间中，或者高级神职人员是否要求它被称为“方法”——玫瑰是玫瑰的任何其他名称。这仍然是*完全相同的*范式，我小时候学习基础。*“你会如何指导一个机器人去买面包？”*

![](img/95ffec6820e4d28ced37a3966c02c98a.png)

*   去商店
*   买面包
*   把面包带回家

好吧，但是它不知道怎么做这些事情…它怎么去商店呢？

*   去街上
*   步行去商店
*   去商店里面

好吧，但是它怎么去街上？如果我们不解释清楚该怎么做，它可能会穿墙而出…

*   走到门口
*   门户开放
*   出去走走
*   歇业
*   走到人行道上

然后，每一个都可以进一步分解。开门包括移动手、转动把手等。这就是过程化编程的含义:将大型、特定的任务定义为更小、更通用的任务列表。令人震惊的是，这是编程冯诺依曼架构的自然方式(即几乎所有现存的计算机)。所有其他编程范例都必须被编译成过程代码，或者由用过程代码编写的解释器来解释，以便在我们现存的机器上实际运行。

老实说，强加给我们的范式并没有那么糟糕。一开始可能需要一些时间来适应，但是很容易掌握。要真正获得 FP，你需要一个数学头脑，而程序编程是我们萨凡纳狩猎采集者的大脑天生的。虽然它确实有缺点——编写可靠的并发性在范例中是很重要的——但是这些缺点是绝对可以克服的。Go 本身是一种带有额外并发工具的过程化语言……正如 goroutines 有助于在不脱离范例的情况下解决一个困难的问题一样，模块化和健壮的类型系统通过几十年的集体 C++和 Java 编程经验帮助我们创建保持可读性和可维护性的大型代码库，而不是假装我们在做除过程化编程之外的任何事情。

虽然 FP 具有无与伦比的数学美，并且在一般的声明式编程中有巨大的效用，但是过程性是 OG。这是我们来的地方，也是我们生活的地方。这是软件的牛顿物理学。随着神经或量子计算的出现，技术可能会在未来超越它……但对于我们这些进化到追逐瞪羚直至死亡并采集山药的无毛猿来说，它永远是最舒适的，最贴近我们内心的。

程序化编程是。

*程序化编程是。*

*程序化编程将。*

这没关系。

感激地接受的提示:
XTZ:tz 1 VD MIG 2 hff 4x mzz 3 jfm 8 tuqfsmri 1 xtzkc
ETH:0x7cd 9379 b 19 e 19 c 6 da 303 dec 60 a 14091 cc 472 f 59 f