# JavaScript 中的名称空间

> 原文：<https://medium.com/codex/how-to-stop-polluting-the-global-environment-using-namespace-in-javascript-1ac65863c895?source=collection_archive---------1----------------------->

![](img/ecbea2f7753b68787b1158978d1cde91.png)

卡斯帕·卡米尔·鲁宾在 [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral) 上的照片

## 命名空间解决了编程中的命名冲突。在 javascript 中，默认情况下没有命名空间。但是我们可以创造一个

# 什么是命名空间，为什么我们需要命名空间？

我们用 javascript 写的东西都是全局窗口对象的属性。有时我们需要多次使用同一个标识符(变量、函数)。但是，由于范围问题，会发生命名冲突。

命名空间为标识符提供范围，以避免它们之间的命名冲突。我们在不同的上下文中使用同一个变量。使用名称空间有助于我们在不同的名称空间中使用相同的变量。

假设我们想使用两个同名的函数。但是这样做会产生一个错误

因此，为了避免错误，我们将使用一个名称空间，通过它我们可以轻松地使用这两个函数，而不会出现任何错误

# 我们如何创建名称空间？

我们通常创建一个包含所有变量的全局对象，作为对象的属性。它以不污染全球环境的方式帮助我们。

# 名称空间的示例

看上面的代码。我们在男性和女性对象中都使用了吃饭和睡觉功能。在这里，这些功能不会彼此重叠。

2 个吃饭函数+ 2 个睡觉函数=两个全局对象内总共 4 个函数。这样，我们可以在一个全局对象中嵌套数百个变量和函数。

使用名称空间，我们创建了两个睡眠功能，他们工作没有任何错误。

请记住，这些函数在对象外部是不可访问的。**这没用。**

```
**sleep();**
**eat();**
```

这就是为什么我们可以使用这个命名空间方法来隐藏我们的代码。

还有其他一些隐藏代码的方法。我们来看看这些方法。

# 隐藏代码的方法

**第 1 种方法:**将代码用花括号括起来。必须使用 let/const 来声明变量和函数。

**第二种方法:**用带“()”的函数换行，然后调用末尾带“()”的函数。

使用 const/var/let 来声明变量或函数并不重要。所有的变量和函数从外面都是不可访问的

**非常感谢您阅读我的文章**