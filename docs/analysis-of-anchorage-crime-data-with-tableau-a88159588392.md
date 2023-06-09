# 用 Tableau 分析锚地犯罪数据

> 原文：<https://medium.com/codex/analysis-of-anchorage-crime-data-with-tableau-a88159588392?source=collection_archive---------7----------------------->

我最近在数据分析课上第一次尝到了 Tableau 的味道。当选择一个数据集来练习创建可视化时，我想选择在我的家乡阿拉斯加州公开发布的数据。最后，我用了联邦调查局安克雷奇的统一犯罪报告数据。该数据集本身相当小，其中的列用于跟踪每年已清理(已解决)和已报告的暴力和财产犯罪。有兴趣自己玩的可以在这里找到[，我对 Tableau 的第一印象可以在这里](https://data.muni.org/Public-Safety/UCR-Anchorage-Crime-Data/mjhu-xscr)找到[。](/@aibromaghin/diving-into-tableau-6213e381fad1)

# 第一眼

![](img/6c46930863c4d68d2c26b7fd78925dcc.png)

如上所示，财产犯罪在过去 30 年中有所波动，在 90 年代中期和 2010 年达到高峰。相比之下，暴力犯罪稳步增长，2019 年是 1986 年原始值的两倍。我发现这两者之间的差异很有意思，并想查看一段时间内暴力犯罪和财产犯罪案件的报告和结案总数。具体来说，我很想看看伊森·伯克维兹担任市长期间的这些变化。

伯克维茨是一名民主党市长，任期为 2015 年至 2020 年。阿拉斯加整体上被认为是一个红色的州，安克雷奇是其中一个蓝色的热点。由于犯罪是保守派经常谈论的话题，我很想知道民主党人对我家乡犯罪的影响。

# 伯克维茨&财产犯罪

![](img/440de0b01ffcf1f7f81b7a9b35911505.png)

我们可以看到，财产犯罪在伯克维兹任期内开始上升，然后回落。已结案的案件数量有一些小的变化，随着报告案件数量的增加而上下波动。2019 年，结案数量明显下降。

这里有几个值得注意的比较。2013 年报告的财产犯罪数量与 2019 年大致相同，但破案率要高得多。次年，报告的财产案件数量略有下降，但结案数量急剧下降。

总的来说，我们可以看到，在伯克维兹执政期间，财产犯罪激增，然后开始回落。在 2014 年(他任职前)和 2019 年，有两次结案数量大幅下降。让我们来看看暴力犯罪的相同信息，看看是否复制了相同的模式。

# 伯克维茨&暴力犯罪

![](img/a3fde3025bfad2fd4a2c9508629c80dd.png)

暴力犯罪的趋势遵循一种明显不同的模式。2015 年，也就是伯克维兹上任的那一年，案件数量立即增加，但我们也看到，作为回应，结案数量大幅增加。尽管财产犯罪在 2017 年稳步增长，达到一个明显的峰值，然后回落，但暴力犯罪在他的任期内仍然居高不下-2019 年略有下降。与伯克维茨上任前一年相比，2019 年报告的暴力犯罪增加了 37%。

但我们也可以看到，结案数量明显增加，在 2018 年达到峰值。这与财产犯罪数据形成了鲜明的对比，在财产犯罪数据中，已结案件的数量只有小幅波动。

# 添加一些上下文

我们可以看到，伊森·伯克维茨担任市长期间，犯罪率上升了，但我们的数据给了我们一个更微妙的视角。暴力犯罪自 21 世纪初以来稳步上升，并在 2010 年中期伯克维兹上任时达到顶峰，但破案数量相应上升到新的水平。财产犯罪在 2017 年达到顶峰，但在伯克维茨离任时急剧下降。当时的政策或环境有什么变化可以解释这些变化吗？

2010 年中期，安克雷奇的毒品和酒精问题激增。这座城市长期以来一直有滥用毒品的历史，酗酒在整个州都很普遍。正如当时的警察局长贾斯汀·多尔(Justin Dole)在接受《安克雷奇每日新闻》(Anchorage Daily News)采访时所说，追踪特定包装的非法药物的来源从困难到不可能(霍普金斯，2018 年)。我们知道，无论毒品从哪里贩运，药物滥用都急剧上升。加上阿片类药物的持续流行，这些变化是犯罪快速增长的驱动力(Hopkins，2018)。随着海洛因和冰毒成瘾者人数的增加，他们为资助其成瘾而实施的盗窃量也在增加(Hopkins，2018)。

大约在同一时间，一项名为 SB-91 的有争议的司法改革法案出现了。SB-91 的目标是在不损害公共安全的情况下，通过减少监狱中的囚犯人数来削减成本(Kelly 等人，2017 年)。从理论上讲，减少州监狱服刑人数可以节省州政府的资金，将更多的资源用于预防将有助于降低犯罪率。该政策基于许多其他州使用的 an 方法，通常具有积极的效果(Kelly 等人，2017)。然而，Burkowitz 承认，事情并非如此:对非暴力犯罪的处罚有所减少，但在改善康复和预防方面几乎没有做什么(Hopkins，2018)。该法案最终是短命的，在 2018 年被下届政府废除(Brooks，2019)。

由于 SB-91 的短暂，很难说它产生了什么影响，但很明显它确实产生了一些影响。在与上述相同的采访中，Justin Dole 表示，该法案对罪犯的影响好坏参半。一些人意识到对非暴力犯罪的处罚降低了，因此增加了他们的犯罪活动。然而，其他人不知道立法的变化。不管会受到什么样的惩罚，他们都会被毒瘾驱使犯罪(Hopkins，2018)。

# **最终想法**

那么伯克维兹在这一切中扮演了什么角色呢？很难说。很明显，在他的任期内，安克雷奇的财产和暴力犯罪都增加了。SB-91 降低了对非暴力犯罪的处罚，这似乎导致了财产犯罪的上升。药物滥用的增加可能起了更大的作用，因为整体犯罪增长迅速。随着财产犯罪案件数量的增加，警察似乎难以满足对他们的要求。

总的来说，Burkowitz 似乎面临着药物滥用急剧上升的困难局面，并尽力采取了相应的行动。在他任期结束的前一年，也是该数据可用的最后一年，犯罪率比他上任时还要高。然而，我们确实看到，这些数字已经见顶，并呈下降趋势。此外，与他的前任相比，已结案的暴力犯罪案件数量有了显著改善。随着他任期的结束，事情似乎朝着正确的方向发展。

阿拉斯加是美国最危险的州之一(斯特宾斯，2020)。它的暴力犯罪和药物滥用水平很高，并继续面临如何处理无家可归者，公共卫生需求，气候变化和资源管理的问题。许多部分需要走到一起，国家才能应对它面临的许多挑战。我坚信数据是其中之一。为数据驱动的政府而努力，客观和理解比简单地大声说话更重要。

快乐编码。

# **引文:**

布鲁克斯，J. (2019 年 5 月 29 日)。*阿拉斯加州参议院投票废除并替换 SB 91 的大部分内容，将犯罪法案送到州长的办公桌上*。安克雷奇每日新闻。[https://www . adn . com/politics/Alaska-legislative/2019/05/29/Alaska-Senate-votes-to-abuse-and-replace-most-of-s b-91-sending-crime-bill-to-governors-desk/](https://www.adn.com/politics/alaska-legislature/2019/05/29/alaska-senate-votes-to-repeal-and-replace-most-of-sb-91-sending-crime-bill-to-governors-desk/)

霍普金斯大学(2018 年 6 月 28 日)。去年安克雷奇有 4500 万美元的财产被盗。今年更惨。安克雷奇每日新闻。[https://www . adn . com/Alaska-news/crime-courts/2018/06/28/after-a-record-year-for-property-crime-in-anchorage-car-theft-is-skirting-in-2018/](https://www.adn.com/alaska-news/crime-courts/2018/06/28/after-a-record-year-for-property-crime-in-anchorage-car-thefts-are-skyrocketing-in-2018/)

霍普金斯大学(2018 年 7 月 26 日)。*‘我不只是听到，我感觉到了’:与市长伯克维兹关于安克雷奇犯罪的对话*。安克雷奇每日新闻。[https://www . adn . com/Alaska-news/crime-courts/2018/07/26/what-happed-a-conversation-on-anchorage-crime-with-mayor-Ethan-berkowitz/](https://www.adn.com/alaska-news/crime-courts/2018/07/26/what-happened-a-conversation-on-anchorage-crime-with-mayor-ethan-berkowitz/)

凯利，博士，博茨，硕士和赫兹，N. (2017 年 10 月 21 日)。SB 91 如何改变了阿拉斯加的刑事司法系统。安克雷奇每日新闻。[https://www . adn . com/Alaska-news/crime-courts/2017/10/21/how-s b-91-has-change-alaskas-criminal-justice-system/](https://www.adn.com/alaska-news/crime-courts/2017/10/21/how-sb-91-has-changed-alaskas-criminal-justice-system/)

南斯特宾斯(2020 年 1 月 13 日)。*危险的州:哪些州的暴力犯罪率和谋杀率最高？*今日美国。[https://www . USA today . com/story/money/2020/01/13/most-dangerous-States-in-America-violent-crime-murder-rate/40968963/](https://www.usatoday.com/story/money/2020/01/13/most-dangerous-states-in-america-violent-crime-murder-rate/40968963/)