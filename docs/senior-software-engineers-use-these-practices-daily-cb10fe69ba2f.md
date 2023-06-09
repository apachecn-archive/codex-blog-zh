# 高级软件工程师每天都在使用这些实践

> 原文：<https://medium.com/codex/senior-software-engineers-use-these-practices-daily-cb10fe69ba2f?source=collection_archive---------9----------------------->

## 加速您的旅程。

任何级别的开发人员都可以通过关注一些小细节来实现完美的交付。

你可以让卓越成为你日常生活的一部分，尤其是当你以开发和维护软件为生的时候。

将这些实践变成习惯，加速你迈向高级软件工程师的旅程。

![](img/2023e8667291c51434dd64894eef2a56.png)

照片由 [Pixabay](https://www.pexels.com/photo/close-up-of-human-hand-327533/) 拍摄

# 将卓越付诸实践

找出不属于你的技能的做法。

1.  看看输出。
2.  合并前检查更改。
3.  [向某人演示](/codex/how-every-engineer-can-demonstrate-working-software-every-day-eaaf30071b79)功能。
4.  向某人解释实现。
5.  以[小增量](/codex/software-developers-should-deliver-thin-slices-of-functionality-510d8a0bb6de)工作。
6.  [测试](/codex/you-dont-need-to-ask-for-permission-to-set-a-variable-b7190ecafdb2)一切。
7.  捍卫你的选择。
8.  把事情写下来。
9.  [再次测试一切](/codex/how-engineering-managers-should-balance-system-reliability-and-new-features-761f160b921)。
10.  [与你的团队沟通](/codex/your-engineering-director-does-not-want-you-to-optimize-for-utilization-a48ad0368b8)。

选择一项实践。设定一个持续使用这种实践的意图。回顾你每天是怎么做的。当你准备好了，开始下一个练习。

> 我们就是我们反复做的事情。
> 
> 因此，优秀不是一种行为，而是一种习惯。
> 
> *—亚里士多德*

# 优秀是一种习惯。

这些实践适用于大多数开发环境、语言和配置。然而，我假设:

*   您正在使用源代码管理。
*   你有一个功能齐全的本地环境。
*   您有一个类似生产的测试环境。

# 1.看看输出

运行您的应用程序会生成大量输出，这些输出提供了关于正在发生的事情的有价值的信息。

当运行您的应用程序时，遵循日志并查看发生了什么。输出是您期望的吗？那里有额外的东西吗？丢了什么东西吗？

当运行任何脚本时，输出是您所期望的吗？脚本是干净地结束了还是出错了？脚本产生了您期望的结果吗？

如果你有自动化测试，他们干净利落地完成了吗？每个测试都按预期运行了吗？测试运行得够快吗？

# 2.合并前检查更改

知道你在任何时候对代码库做了什么改变。

在提交之前，检查每一个被修改的文件和每一行，即使是本地提交。我遇到过太多文件被*【意外】*合并到代码库的主要开发分支中的情况。你可以通过这个简单的练习来阻止这些意想不到的变化。

如果您在功能的薄片上进行非常小的增量工作，那么变更的数量将会很少，审查将会很快。

# 3.向某人演示功能

当你完成工作后，[向某人展示你所做的。](/codex/how-every-engineer-can-demonstrate-working-software-every-day-eaaf30071b79)

告诉他们系统是做什么的。向他们展示不同场景是如何工作的。更好的是，让他们使用系统并指出任何问题或错误。

无论你的团队如何定义这个特性，他们对未来都没有一个完美的愿景。通过查看运行中的特性，您的团队现在有了更多关于如何使其工作得更好的信息。变更是软件开发不可或缺的一部分。当评审者开始要求修改时，不要沮丧。

利用评论的反馈来创造一个真正令人惊叹的产品。

# 4.向某人解释实现

在您使特性工作，并且您的实现完成之后，回顾您与其他开发人员所做的工作。这可以在配对时实时完成，也可以在事后通过拉取请求或代码审查来完成。

对别人要说的持开放态度。利用这个机会了解替代解决方案。利用任何反馈作为集体经验，尽可能产生最好的代码。

记住，他们评论的是实现，而不是作为开发人员的你。

# 5.以小增量工作

将功能构建成[小增量](/codex/software-developers-should-deliver-thin-slices-of-functionality-510d8a0bb6de)。

解决一个小问题比解决一个复杂的问题要容易得多。将你的系统进化成每个人都梦想的功能齐全的系统。你会很快达到稳定，并迅速改变方向。

除了专注之外，你还会从每项职能的快速成功中获得动力。

保持稳定——经常提交。

一旦你的小改变起作用了，就把它们提交到你的存储库中。

当一个队友想看你在做什么的时候，你应该在几分钟内展示给他们看。您的代码更改应该足够小，可以根据需要丢弃并重新创建。

这允许你在有一个安全的地方回来的同时进行实验。这也让你可以根据需要换挡。通过关注小的增量，您的系统总是接近一个可以向全功能发展的工作状态。

# 6.测试一切

在您的系统中练习大多数用户会遇到的主要路径，以及任何替代路径和错误场景。

我的意思是运行你的代码，查看你的应用程序，确保没有明显的错误。你的程序编译干净。没有拼写错误，没有错别字，没有明显的错误。尝试运行代码中的所有分支，以确保它们正常工作。

除了应用程序代码和可见屏幕之外，还要运行系统中的任何脚本、作业和实用程序任务。如果您正在计划离线任务，请在计划之前手动运行该任务以确保其正常工作。

即使你正在使用[自动化测试](/codex/you-dont-need-to-ask-for-permission-to-set-a-variable-b7190ecafdb2)，也要像用户一样检查你的应用程序，确保没有明显的错误。

# 7.捍卫你的选择

你一整天所做的一切，都是一种选择。

证明一切。你写的每一行代码。你不写的每一行。你添加的一切，和你删除的一切。你选择的每一个名字，和你避免的每一个名字。所有你决定先做的事情，以及所有你决定推迟做的事情。你做的每一个选择，你权衡的每一个选择。

**慎重考虑你所做的选择。**

答案可以简单到“我在 StackOverflow 上看到一个例子”，也可以细致到“我应用了 QQQ 模式，并在本书中引用了 RRR，用 SSS 换来了 TTT”。尽你所能用你的经历来回答，同时理解你为什么这么做。

你的答案不一定要对，但一定要反映出你当时所知道的最好的。

# 8.把事情写下来

把你的清单放在附近。

开发工作变得非常复杂。不要因为忘记你需要做什么而增加复杂性。无论你是在讨论一个新的特性还是进行代码评审，或者讨论当天需要做什么。

公开您的笔记。让每个人都看到你在做什么。你和你的队友可能会发现一些重复的工作，或者一种简化工作的方法。

***写(好)给未来的自己。***

像编辑一样思考，修改任何模糊之处，让读者一目了然。

注意你选择的词，无论是变量、方法、类、模块、注释还是提交消息。当你开发一个功能的时候，一切都很明显，就像你会记得一切。

记住两件事:

*   你的队友没有你现在拥有的即时环境
*   在不久的将来，你将不会有那种直接的背景。

写作是为了帮助别人熟悉你的作品。

# 9.再次测试所有东西

跟随您的代码进入测试环境。在类似于生产的环境中运行它。查看您的功能。炫耀一下。获取反馈。检查它的工作和性能。在您的[生产环境](/codex/how-engineering-managers-should-balance-system-reliability-and-new-features-761f160b921)中做同样的事情。

深呼吸，微笑，庆祝你的特色是**完成**。

# 10.与您的团队沟通

成为信息的辐射者。

你在做什么？你有什么问题？你找到了哪些解决方法？[有哪些地方可以做得更好](/codex/your-engineering-director-does-not-want-you-to-optimize-for-utilization-a48ad0368b8)？你什么时候集成和部署你的变更？

不要把这局限于技术任务。

你什么时候休假？你明天会迟到吗？你星期五要早走吗？尽早并经常让你的队友知道。不要害怕信息过载。

每个人掌握的信息越多，整个团队就能更好地协同行动。

***你并不孤单***

你的队友、你的组织、你的经理、你的公司和你的社区都在这里帮助你。

![](img/6c3cf77578a555767a6fcba7955faa13.png)

照片由 [Olya Kobruseva](https://www.pexels.com/photo/a-person-writing-on-a-desk-calendar-5408684/) 拍摄

> 很快，优秀将成为一种习惯。

将这些实践变成习惯将会加速你迈向高级软件工程师的旅程。

*👏🏻如果你喜欢这篇文章，请为我鼓掌并跟随***。**

## *📋关于米洛*

*我是一名科技高管、作家、演说家、企业家和发明家。我从 1995 年开始开发软件，过去十年一直在开发团队。🚀*

*我写关于软件、工程、管理和领导力的文章。*

**你也可以* [*在 Twitter 上关注我*](https://twitter.com/milotodorovich) *。🐦**