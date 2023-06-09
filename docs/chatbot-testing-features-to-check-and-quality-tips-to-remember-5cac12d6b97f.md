# 聊天机器人测试:要检查的功能和要记住的质量技巧

> 原文：<https://medium.com/codex/chatbot-testing-features-to-check-and-quality-tips-to-remember-5cac12d6b97f?source=collection_archive---------15----------------------->

聊天机器人是基于人工智能的计算机程序，通过理解上下文并从口头或书面语言中获取意义来模拟人类对话。机器人解释对话的目的，并提供相关的答案或方向。聊天机器人通过文本和语音进行通信，并根据其使用的行业进行分类，如银行聊天机器人、医疗聊天机器人、个人金融聊天机器人等。聊天机器人已经成为加强客户支持的首选媒介。

![](img/0d414ea90fda000fe3d6aacbc5495e41.png)

聊天机器人需求激增

与人类高管不同，机器人会全天候回应客户的询问，自新冠肺炎出现以来，世界各地的组织对聊天机器人的采用出现了大幅增长。现在已经充分认识到，客户支持不能仅仅依靠人力资源，拥有一个智能聊天机器人对于防止客户因延迟响应而不满意是绝对重要的。

**为什么聊天机器人测试至关重要？**

虽然组织很喜欢利用聊天机器人作为新的和始终运行的客户支持渠道，但它似乎没有像预期的那样激发最终用户的热情。根据 Forrester 最近的一份报告，54%的客户预计聊天机器人会对他们的体验产生负面影响。许多聊天机器人失败是因为他们不理解客户的意图，这是由于训练和测试不足。聊天机器人的训练和测试包括几个阶段和特定的技术，以精心引导它达到完美模仿人类对话的阶段。

在商业中使用聊天机器人的最大困难是它可能会失败。大多数一般性问题会让客户感到沮丧，并影响品牌形象和业务效率。在设计不良、测试不充分的聊天机器人中，一些常见的问题是导致故障、回复延迟、无法连接到其他业务渠道、缺乏准确性、导航生锈和对话设计不当的破损脚本。

根据行业的不同，测试聊天机器人的过程会有所不同，但某些原则是相同的。QA 专家在构建聊天机器人测试程序时的一些主要考虑因素如下:

*   从识别聊天机器人的用例开始。为每个场景准备一组问题和可能的答案，并根据它们的重要性排列优先级。重要性可以通过评估其在实时使用中的频率来衡量，或者通过权衡查询的严重性和聊天机器人提供错误响应的后果来衡量。
*   评估聊天机器人的对话能力和客户期望它的智能程度。应该为每个用例明确定义可测试的需求和关键性能指标(KPI)。聊天机器人允许的数据类型也应该清楚地标识和记录。KPI 可以是

a.Self-service rates，即聊天机器人在没有客户服务主管参与的情况下可以自行解决的客户参与总数。

b.转换率，这是通过聊天机器人对话带来的业务转换与参与的客户总数的比率。

c.平均客户评分。

*   一旦清楚地列出了可测试的需求，就要理解构建聊天机器人的基础架构和技术。聊天机器人通常建立在自然语言处理(NLP)的基础上，这是一种计算机从书面或口头语言中分析和推导意义的方法。理解底层架构对于正确训练聊天机器人至关重要。
*   聊天机器人的训练还应该考虑影响书面或口头对话的变化，使其独特。特定的方言、俚语、缩写、带有背景噪音的对话、独特的措辞，以及在同一请求中处理多个指令，这些都是需要测试的其他场景。此外，还应该验证聊天机器人处理错误的能力。如果您希望在多个渠道、用户界面和设备上使用 chatbot，还应该计划全渠道兼容性测试。
*   从非功能角度来看，必须测试聊天机器人在同时为数百名其他客户服务时对每个客户查询的响应速度。测试聊天机器人的安全特性也很重要，例如认证和授权、消息的加密传输以及遵守法规。

**测试聊天机器人时要检查的功能**

**对话流程**

作为一名测试人员，你的主要目标应该是测试你的聊天机器人是否能够理解客户在对话中的询问，并在规定的时间内提供适当的答案。聊天机器人是否能在处理等待时间内让客户参与进来也需要测试。从最基本、最常见的问题开始，然后转移到关键的测试场景，最后处理边缘案例。

由于人类的语言充满了细微差别，如双面含义、幽默、讽刺、挖苦等等，它们也应该成为聊天机器人训练的特色。向自己提出以下问题，看看答案是否符合你的预期，以评估聊天机器人的进展。

*   你的聊天机器人理解对话上下文中的查询吗？
*   它通常会对这些询问给予迅速的答复吗？
*   对发布的问题的回应是否恰当？
*   聊天机器人提供解决方案的步骤是足够多还是太多？
*   你的聊天机器人能让用户在等待期间保持活跃吗？

**特定业务查询**

当对话流被批准后，测试人员应该继续测试聊天机器人如何处理业务明确的查询。如今，聊天机器人主要被银行、零售商、急救诊所和行政机构使用。每个行业都有无数的行话和微妙之处。这种特定领域的查询也应该在测试过程中体现出来。

**混乱处理**

如果客户向聊天机器人输入一些多方面的细微差别或晦涩难懂的单词，可能会产生混淆。应该训练聊天机器人在这种情况下提供友好的回答，要求客户再次提供他的查询或改写他的查询。测试人员的目标是检查聊天机器人是否能够处理错误、异常和不常见的情况。

**速度和精度**

用户期望聊天机器人对他们的查询提供准确及时的响应，这强调了性能测试的重要性。延迟——聊天机器人检索响应并将其转发给客户所需的时间应该尽可能短。另一个基本测试是对反应的准确性。测试设计者应该计算机器人对相同意思的不同措辞的查询提供准确响应的次数。

**格式验证**

如果聊天机器人接受诸如电子邮件地址、电话号码和邮政编码之类的输入，那么在处理这些信息之前，它必须检测这些信息的正确格式。如果发现信息无效，聊天机器人应该通知用户修改细节。聊天机器人应该在详尽的数据集上训练，使用该数据集需要彻底检查格式验证行为。

**界面和图形内容测试**

聊天机器人定期向客户提供:品牌网站或其他资源的链接、插入数据的卡片，或者各种格式和分辨率的图片。所有这些元素都应该按照预期运行，没有任何故障。除了文本之外，所有接受的格式也应该包含在训练中，以查看它们是否如预期那样显示在 chatbot 界面上。

**兼容性测试**

测试聊天机器人在不同小工具上的所有上述参数的外观和功能是否相同被称为兼容性测试。测试 chatbot UI 元素及其可用性在不同设备、浏览器和操作系统版本上是否保持一致。需要测试在 PC 屏幕上调整浏览器窗口大小时，图形是否没有失真，聊天机器人窗口的用户界面是否没有中断。文本应该保持可读性，不要超出限制。

**未知输入的错误处理**

重要的是调查编程逻辑的限制，并确保机器人对它不理解的输入返回适当的响应。探索性测试是了解聊天机器人如何处理非标准输入的一种有价值的技术，这些非标准输入包括:

*   与聊天机器人的目的无关的随意讨论。
*   通常不会出现在客户对话中的无用句子或发音。语言错误，拼写错误的单词，英语拼写的变化。
*   令人困惑和充满敌意的信息。

**API/集成测试**

一般来说，聊天机器人不会独自工作，它会成为组织的计算机化生态系统的一个组成部分。也就是说，你最终需要将它关联到你的官方网站、社交网络账户、messenger、应用程序或任何其他数字媒体。

如果您使用机器人构建编程，您可能会发现一个 API，它允许聊天机器人与您的框架进行接口，并在其上运行 API 测试。如果您使用定制安排，运行集成测试来检查 bot 和其他框架在关联时的行为是非常重要的。

**测试聊天机器人时要记住的质量提示:**

![](img/43d02d5da153acd9ad8101787dc22d4b.png)

*   数据验证应该立即进行，然后是相应的消息。对于无效信息，返回的消息应该通知客户查询中的错误。如果信息是合法的，客户端应该会看到一条成功消息，表明机器人已经接受了所提供的信息。
*   应该要求客户对聊天机器人的体验进行评价。实时用户可能会发现并报告一些在训练/测试阶段可能遗漏的缺陷。
*   在上线之前，聊天机器人应该在广泛使用的小工具、程序和操作系统版本上进行测试。
*   聊天机器人应该能够友好地回答复杂的问题。
*   测试以检查聊天机器人是否避免进入循环。
*   与聊天机器人的讨论应该有一个合理的必要信息流，类似于与客户支持主管的对话。
*   关注输入的多样性——不同的语言、格式、长度和字符组合。
*   确保聊天机器人足够智能，能够记住客户在同一对话中提供的详细信息。永远不要询问已经分享过的细节。
*   当聊天机器人无法解决特定的查询时，它应该有助于顺利过渡到客户支持主管，而接管的主管必须拥有客户提供给机器人的所有信息。
*   聊天机器人测试的自动化可以通过使用另一个成熟的聊天机器人与你正在测试的聊天机器人进行交互来完成。
*   将聊天机器人的测试分为三个级别:可能的场景、预期的场景和几乎不可能的场景，并确保聊天机器人以迅速的方式提供预期的回复。
*   检查聊天机器人是否符合你的听众的语气和每次谈话的性质。
*   应该总是有最后一条消息标志，表示讨论结束。
*   如果聊天机器人的响应延迟超过五秒钟，这肯定会导致沮丧，客户可能会放弃解决问题的尝试。因此，确保客户在五秒钟内得到响应，如果等待时间更长，聊天机器人应该不断更新正在发生的事情。
*   如果聊天机器人可以识别客户的时区，并在对话开始时问候他们，那就太好了。这是一个很小的动作，但它对赋予聊天机器人人性化有很大帮助。

**结论**

测试聊天机器人不是一项简单的任务，因为它涉及到对其内部编程、规划、思维、技术应用、数据集、实时场景预测和专家思维过程的技术理解。此外，聊天机器人需要不断的支持和升级。在第一次发布后，当聊天机器人开始与实时用户交谈时，真正的测试就开始了。

建设性地接受客户的反馈，努力提供更好的更新。持续不断的测试过程对于保持聊天机器人的相关性、准确性和经得起未来考验的性能至关重要。

**作者:Vijayakumar A&Mohan bharat hi S**