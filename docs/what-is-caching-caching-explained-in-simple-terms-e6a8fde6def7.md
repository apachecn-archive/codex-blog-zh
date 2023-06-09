# 什么是缓存？用简单的术语解释缓存

> 原文：<https://medium.com/codex/what-is-caching-caching-explained-in-simple-terms-e6a8fde6def7?source=collection_archive---------16----------------------->

![](img/56f67f33f8d2646edaa03098b9b9844d.png)

用简单的术语解释缓存

你有没有遇到过你的电脑出现故障，并被指示删除您的缓存和 cookies 或 DNS 缓存来解决它？你可能听说过它们，但是到底什么是缓存呢？简单地说，缓存意味着将频繁请求的项目存储在离需要它们的人更近的地方。结果，提高了访问速度。一个基本的解释可以在《赖以生存的算法》一书中找到。

假设你正在为一篇论文或一部电影进行研究，需要在图书馆查阅一本书。你可以在任何需要信息的时候去图书馆，但相反，你可能会把这本书带回家，放在桌子上方便取用。在这种情况下，你的桌子变成了一个缓存。现在你可以直接从你的书桌上拿回这本书，而不是多次去同一个图书馆，那可能会耽误你的工作。您可以直观地理解为什么缓存要快得多，但它也有一定的局限性。你可能没有图书馆书架上那么大的桌子空间。你只能在你的藏书室里保留一定数量的书。稍后会有更多！

让我们从高速缓存在计算机中是如何工作的开始。例如，您的网络浏览器会缓存经常浏览的网站的信息。当你第一次访问 YouTube.com 时，你的浏览器对它并不熟悉，所以它会加载构成 YouTube 的所有内容。徽标、图标、字体、脚本和所有缩略图。但是，在以后的访问中，所有这些都可以从缓存中恢复。由于你的网络浏览器只需要获得以前没有看到过的最新资料，网页加载速度会大大加快。在 YouTube 上，这可能只是自您上次访问以来添加的剪辑的缩略图。在这种情况下，您的浏览器缓存节省了本地计算机上的大量资源。通过你的存储器或硬盘恢复信息比通过互联网要快得多。这也是为什么删除您的缓存可能有助于解决一些问题。网站可能会不时改变其外观或脚本，但您的网络浏览器将继续使用缓存的先前版本。

然而，缓存并不局限于浏览器。现代设备中有大量的缓存。在硬件方面，缓存位于 CPU、GPU、硬盘和固态硬盘中。这导致了记忆层次的形成。绝对顶端是集成在 CPU 中的内存，速度极快但极其微小。在这个层次结构的底部，您会发现固态硬盘和硬盘等产品，它们具有巨大的容量，但与顶部相比非常缓慢。

在图书馆里可以看到类似的安排。经常外借的书可以放在前面的小柜子里，在那里可以很快找回。不太受欢迎的书籍将被送到书库。那里的空间比前面的小柜子大得多，但是你要找到你要找的书可能有点困难。最终，你会有一些书被转移到异地存储，因为它们很少被借出。虽然这个集合很可能是最大的，但它确实是检索最慢的。有必要请求工作人员为您获取它们，这可能需要几天时间。

缓存用于各种软件应用，包括操作系统、网络浏览器、域名系统、数据库、网络服务器等。每次都是为了同样的原因:将数据存储在高速缓冲存储器中，以便可以更快地访问。但是让我们回到你桌上的书堆。你的书桌最终会堆满书。那么，当您的缓存已满时会发生什么呢？你如何决定哪些书或产品要保留，哪些要从你的缓存中删除？这被称为高速缓存驱逐方法。你可能会本能地归还你有一段时间没看的书。这被称为最近最少使用，或 LRU，这是一个简单而成功的技术。

确实有必要记下自从你上次访问以来你的缓存中的内容，这会稍微减慢它的速度。随机替换是另一种驱逐技术。这一个是不寻常的，因为它没有试图变得聪明。当缓存满了，它只是删除一个随机的项目。虽然这看起来是一种拙劣的技术，但实际上，它离 LRU 不远，而且更容易实施。因此，它被用于微型 ARM 处理器，以简化其设计。

但是最激起我对缓存兴趣的是它是由英国的计算机科学家莫里斯·威尔克斯于 1965 年发明的。他在文章中指出，缓存应该自动用较慢的主内存中的数据填充自己，以加快后续请求的速度。令人难以置信的是，几乎 56 年前创造的技术现在正在被利用和改进。感谢您的访问和与我们打交道。我希望你喜欢它，如果你喜欢，请考虑跟着我，给我鼓掌！