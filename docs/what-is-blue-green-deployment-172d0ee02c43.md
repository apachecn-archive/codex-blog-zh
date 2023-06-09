# 什么是蓝绿色部署

> 原文：<https://medium.com/codex/what-is-blue-green-deployment-172d0ee02c43?source=collection_archive---------17----------------------->

![](img/ad0647684b80d698193da32a17c2a669.png)

软件开发团队经常面临前所未有的挑战，比如他们的应用程序频繁发布和更新。他们必须在不损害质量和客户体验的情况下实现平稳发布。

为了在这两者之间取得平衡，软件开发中出现了许多发展和范式转变，例如敏捷和 DevOps。像持续集成和持续部署这样的方法在过去几年里获得了巨大的吸引力。

简而言之，如今测试、构建和发布应用程序的能力是由各种各样的工具和方法支持的。应用程序发布自动化和构建自动化软件在无需人工干预的情况下将更新推向生产中发挥着关键作用，从而最大程度地减少了技术麻烦。

现在，让我们深入研究全球企业使用的最佳部署模型之一——蓝绿色部署。

**目录**

1.  什么是蓝绿部署？
2.  蓝绿部署的特点？
3.  实施蓝绿色部署的工具和服务
4.  蓝绿部署工作
5.  结论

# 什么是蓝绿部署？

蓝绿色部署是一种在生产环境中执行更新的部署方法，其核心目标是减少服务器停机时间。这使得回滚新的更改和避免对有严格运行时间要求的应用程序的服务中断变得极其容易。

一个蓝绿色的部署服务器使用两个相同的硬件环境——一个为用户服务，另一个设置为空闲，作为临时环境。如果一个是蓝色的，另一个是绿色的。活动环境充当新的更新和功能的目标，而非活动部署槽基本上是备份环境，当第一个环境被请求淹没时，流量可以被重定向到该备份环境。在一些组织中，这种方法也被称为红黑部署方法。

# 蓝绿色部署的特征

1.  蓝绿色部署允许在部署期间在两个环境之间无缝切换，从而降低停机风险。
2.  它结合了数据库版本管理实践。这意味着它为开发人员提供了单独的数据库实例，以避免冲突和不必要的差异。
3.  立即回滚到以前的部署是蓝绿部署的一个值得称赞的特性。如果已经被推入活动环境(生产环境)的当前版本中出现 bug，切换到先前版本是非常容易的。
4.  它不会在部署后改变生产环境的价值，包括用户配置和其他角色。

# 实施蓝绿色部署的工具和服务

基于应用程序的基础设施和构建，有各种各样的服务，如 Docker、AWS、Kubernetes 和 Cloud Foundry，其中可以整合蓝绿部署。

随着云计算在部署中的出现，它明显降低了在整个部署和集成过程中面临的相关发布风险。云工具、计费和自动化越来越容易以低成本快速部署蓝绿技术。

蓝绿部署可以通过 AWS 实现，方法是访问它的几个服务，这些服务有助于部署和基础设施的自动化，如 AWS CLI、SDK、ElasticBean 和云形成。

# 蓝绿部署工作

让我们假设一家云服务公司的 DevOps 团队开发了一款游戏(cloud-native app)——这款游戏基本上是一个无止境的跑步者，只有一张定制的地图。游戏的后端由多个基于容器的微服务支持，这些微服务负责评分、多人游戏、地标和成就。

该应用程序在首次发布后就见证了巨大的流量。用户每分钟都在记录事务。DevOps 团队热衷于发布一个小更新——一个力学微服务，涉及到将新地图推送到游戏服务器中。

该团队计划在高峰时段通过蓝绿部署策略推送更新，而不是在用户不太活跃的午夜推送更新，零宕机。整个过程是这样进行的-

将生产环境(本例中为蓝色环境)中的“mechanics”微服务复制到另一个相同的试运行环境(绿色环境)中。在绿色环境中推出新的更新(游戏的新地图)后，Jenkins(一个开源压力测试项目)进行了 Q/A 测试和准备，然后最终部署在活动的蓝色环境中。

当 green 处于活动状态时，DevOps 团队还可以使用负载平衡器将用户的流量从蓝色环境分配到绿色环境。然后，蓝色环境可以离线，并用作灾难恢复目的的备份。因此，蓝绿色部署提供了一个可靠的双向结构来简化部署和发布事件。

![](img/0ebeaaeb6a9f00b2fb301b52336f9847.png)

上图描述了蓝绿色部署如何工作，以及在发布阶段的更新推送期间，生产环境如何从蓝色切换到绿色。

# 结果

尽管蓝绿部署非常可靠，但它也有自己的缺点。它是高度资源密集型的，因为维护两个生产环境成本更高，并且浪费了系统管理员太多的时间。此外，并行生产插槽的多个数据库可能会导致复杂的场景，这对一些组织来说可能太多了。

然而，蓝绿方法的使用已经席卷了 IT 界，尤其是对于提供云服务和托管的组织。公司甚至试图设计新的想法，进一步使部署完全自动化，并使发布过程成为一项简单的任务。

*原载于*[*https://www . partech . nl*](https://www.partech.nl/nl/publicaties/2021/07/what-is-blue-green-deployment)*。*