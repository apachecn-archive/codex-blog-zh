# Spring 框架事务的基础

> 原文：<https://medium.com/codex/the-basics-of-spring-framework-transactions-6a99045dba8?source=collection_archive---------3----------------------->

## 在这篇文章中，我将详细介绍 Spring Framework 如何在幕后处理事务

![](img/22974d1961313b8f290b9e9356190f88.png)

图片由 spring.io 提供

在我们讨论框架如何处理事务之前，我们需要理解一些基本概念，这些概念对于理解本文的内容至关重要。

# 第一个概念:酸的分离。

*“如果你不知道*[](https://en.wikipedia.org/wiki/ACID)**(原子性、一致性、隔离性、持久性)是什么意思，我建议你去寻找相关资料，因为在这篇文章中，我不会深入讨论这些内容。”**

*此时，我们将简要讨论一下 ACID 的隔离，更具体地说是关于**读现象**和**隔离级别。***

*当在数据库中处理并发事务时，我们需要了解 DBMS 提供什么级别的隔离，以及每个级别解决什么类型的读取现象。*

***在这些现象中，我们有:***

***脏读:**当数据在提交之前就可以在并发事务中被读取时，就会出现这种现象。*

***不可重复读取:**当一条记录可以被读取两次而得到不同的结果时，会出现这种现象，因为该记录在两次读取之间的并发事务中被更改。*

***幻像读取:**这种现象与不可重复读取非常相似，但是在这种情况下，在其中一个事务中，执行查询的条件会返回多条记录，而在另一个事务中，我们会插入或删除影响并发事务的查询条件的记录，从而改变查询的结果。*

***在隔离级别中，我们有:***

***Read Uncommitted:** 在这个级别，同时发生的事务之间可以看到未提交的数据，从而允许“脏读”现象发生。*

***读取已提交:**在此级别，在并发事务中只能查看已提交的数据。在这个级别，我们不再有“脏读”现象，但我们仍然可以有“不可重复读”和“幻影读”现象。*

***Repeatable Read:** 在这个级别，我们可以保证在事务的查询中返回相同的记录，不管它是否在另一个并发事务中被更改和提交。在这个级别，我们不再有不可重复读取现象的发生，但是我们仍然可以有幻像读取现象。*

***Serializable:** 这是最高级别的隔离，在这种情况下，我们避免了上述所有现象的发生，但我们会对性能产生相当大的影响，因为数据库试图通过顺序执行调用来保证更高级别的数据完整性。*

*重要的是要弄清楚，上面所说的与隔离级别相关的一切都是基于 ANSI 标准中的描述，但是每个 DBMS 可以不同地实现隔离级别。因此，我们可能会有不同的行为，这取决于所使用的 DBMS。*

*另一个要点是，每个 DBMS 都有默认的隔离级别。例如，在 Oracle、Postgres 和 SQL Server 中，默认值是 Read Committed。在 Mysql 中，默认是可重复读取。*

*了解阅读每个 DBMS 的文档、理解它实现的隔离级别以及它如何处理每种现象总是很重要的。*

# *第二个概念:Spring 框架代理*

*对于使用 Spring 框架的人来说，这是一个非常重要的概念。每当您通过 Spring 注释(如@Transactional)在类中放置指令时，Spring 都需要将指令翻译成特定的代码块，这就是代理出现的时候。*

*特别提到@Transactional 注释，当您用它来注释您的类的方法时，Spring 会创建一个基于您的类的代理，并添加用于打开和关闭事务的代码块，在创建的代码块中间调用原始类的方法。*

*然而，要记住的非常重要的一点是，对于这些添加到代理中以便在代码执行期间调用的指令，对带注释的方法的调用需要来自外部类。当从类本身内部调用方法时，执行不通过代理，注释被忽略。*

***但是这个代理是什么时候创建的，执行是如何通过它的？***

*例如，当您注入一个通过@Autowired 创建的类时，Spring 会分析被注入的类是否有任何类型的注释需要解释，如果有，它会注入一个封装了原始类所有逻辑的代理，而不是注入您的类。*

*例如，您创建了一个名为 MyService 的@Service 类型的类，它有一个用@Transactional 注释的方法，该方法将数据写入数据库，名为 saveData。*

*现在让我们假设您有一个类型为[@控制器](http://twitter.com/Controller)的类，它通过[@自动连线](http://twitter.com/Autowired)注释执行 MyService 类的注入。*

*当 Spring 将要注入 MyService 类时，它将注入一个名为 my service $ $ enhancerbyspringglib 的类，而不是注入原来的类，例如，它也将有一个 saveData 方法。然而，这个方法不同于原始的类方法，它包括:*

```
*public void saveData (Object data) { // begin of transaction here originalClass.saveData(data); // commit or rollback of transaction here}*
```

***注意:**这只是一个说教的例子，它并不完全是框架生成的原始代码。*

# *但是，Spring 如何处理事务呢？*

*既然我们已经对这两个概念有了肤浅的了解，那么让我们来谈谈 spring 是如何处理事务的。*

*所有神奇的事情实际上都是通过@Transactional 注释发生的。*

*@Transactional 注释既可以在类级别使用，也可以在方法级别使用，这取决于所需的事务范围。*

*当我们在 Spring 中使用事务时，需要知道的重要一点与事务的回滚有关。只有当用@Transactional 注释的代码块抛出未检查的异常时，才会发生回滚。如果您希望回滚也在检查异常的情况下发生，您需要使用@Transactional 注释的“roll back on**”**属性来指定异常，例如:*

```
*@Transactional(**rollbackOn** = YourCheckedException.**class**)*
```

*@Transactional 注释有两个非常重要的属性，我们将在下面详述，这些属性是**隔离**和**传播**。*

## *隔离*

*隔离属性你应该已经想象出它是干什么用的了，基于我们在帖子开头看到的。*

*您可以在 Spring 事务中设置隔离级别，用下面的可能值填充隔离属性的值:*

*   *@Transactional(isolation =隔离。已读 _ 未提交)*
*   *@Transactional(isolation =隔离。READ_COMMITTED)*
*   *@Transactional(isolation =隔离。可重复 _ 读取)*
*   *@Transactional(isolation =隔离。可序列化)*
*   *@Transactional(isolation =隔离。默认)*

*上面提到的每一层都代表了 DBMS 中实现的相关层的行为。*

*如果没有填写该属性的值，其默认值将是 Isolation。缺省值，因此会考虑 DBMS 的缺省隔离级别。*

## *传播*

*另一方面，传播属性与事务在代码执行过程中必须传播的方式有关。*

*该属性的可能值为:*

***@Transactional(传播=传播。必需)***

*如果没有填充，这是传播属性的默认值。该值的行为是如果有当前事务，则使用当前事务，如果没有，则创建新事务。*

***@Transactional(传播=传播。支持)***

*对于 SUPPORTS 值，它使用当前的事务(如果有)，如果没有正在进行的事务，它不会创建新的事务。*

***@Transactional(传播=传播。强制)***

*在 MANDATORY 中，如果有正在进行的事务，就会使用它，否则 Spring 会抛出一个 IllegalTransactionStateException 类型的异常。*

***@Transactional(传播=传播。从不)***

*在 NEVER 值的情况下，将不允许使用事务，如果有正在进行的事务，将引发 IllegalTransactionStateException 类型的异常。*

***@Transactional(传播=传播。不支持)***

*在 NOT_SUPPORTED 中，我们有一个非常类似于 NEVER 的场景，但是 Spring 不会抛出异常，而是会挂起当前的事务(如果它存在的话)。*

***@Transactional(传播=传播。【需要 _ 新)***

*在 REQUIRES_NEW 的情况下，如果有一个正在进行的事务，Spring 会暂停它并创建一个新的。一旦这个新事务结束，Spring 将恢复暂停的事务。*

***@Transactional(传播=传播。嵌套)***

*嵌套值在您想要使用保存点时使用，因此有可能部分回滚。当没有正在进行的事务时，它具有所需的相同行为，并创建一个新事务。*

*非常重要的一点是，为了使用嵌套值，我们依赖于外部因素，例如所使用的 JDBC 驱动程序的兼容性。*

*您可能已经注意到，当我们谈论传播属性的值时，我们谈论很多关于当前事务，但是什么是当前事务呢？*

*当前的事务只不过是来自外部的事务，具有更广泛的作用域，例如，假设您有一个使用@Transactional 注释的@Controller 类型的类，该控制器调用另一个使用@Transactional 注释的@Service 类型的类。当发生从控制器到服务的调用并且调用服务方法时，已经有一个来自控制器类的当前事务。*

# *结论*

*我希望我能够澄清一点关于 Spring 中事务的使用以及它是如何处理它们的。当涉及到大量访问和并发的场景时，知道使用事务的正确方法会有很大的不同。如果使用不当，它还会损害应用程序的性能和业务规则。*