# 在 AWS 中创建 Linux 实例

> 原文：<https://medium.com/codex/creating-a-linux-instance-in-aws-82c94e77e166?source=collection_archive---------3----------------------->

## [法典](http://medium.com/codex)

## 借助 AWS，在几分钟内开始免费利用云计算的强大功能

如果你从事科技行业，你很可能会遇到 Linux，并且可能会在某个时候需要使用它。现在就开始吧，按照这个简单的指南在云中启动 Linux 实例。

从托管 web 应用程序、数据库、应用程序测试或集成构建，云计算可以提供一种极其经济高效的方式来实现您的目标。

Linux 有大量被称为“发行版”的变种。Red Hat (RHEL) SUSE 和 CentOS 是常见的基于 RPM 的发行版，Ubuntu 可能是最常见的基于 Debian 的发行版之一。发行版之间有很多核心的相似之处。刚开始的时候，你可能很难看到很多，但它们确实存在，而且[研究一下什么最适合你](https://en.wikipedia.org/wiki/List_of_Linux_distributions)也是值得的。

本指南将解释:

*   创建一个预算来防止任何不必要的花费
*   设置一个 EC2 Linux 实例，包括存储和安全性
*   通过 SSH 连接到新实例

![](img/3a765204ff3aa10ceb8181461ab8503d.png)

AWS 提供了各种各样的机器映像(ami ),您可以从中选择启动实例。在这个例子中，我将使用 Ubuntu 20.04，但实际上你可以使用任何你想要的 Linux AMI。

首先，您需要创建一个 AWS 帐户，这既快速又简单。创建完成后，您将到达 AWS 控制台，在那里您将看到一个现在可用的服务世界。[在这一点上，有必要查看一下免费层页面，了解一下第一年你将免费获得什么，以及](https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc)将收取什么费用。

## 预算

一个很好的安全网是在开始时设定预算，以防止你不小心欠下 AWS 的账单。要快速设置，请在页面顶部的搜索栏中键入 billing 以找到计费服务。从那里点击预算。

单击创建预算，并选择第一步的成本预算。接下来，给它起一个名字，将周期设置为每月，并将其作为一个经常性预算。下面，将其作为固定预算，并设定一个金额。我建议将第一个预算设置为 0.01 美元，这样当你产生费用时，你会得到警告。然后，你可以继续设定更多的预算，比如 0.10 美元，或者 1 美元，如果你想花钱的话。忽略其他一切，进入下一步。

根据实际成本设置阈值，并将阈值设置为 100%。添加您的电子邮件地址，以便您可以得到通知，确认和创建预算。一旦超出预算，您就会收到电子邮件。

## 创建实例

从顶部的服务搜索栏导航到 EC2。这代表弹性计算云。弹性部分本质上意味着计算服务是可伸缩的，可以很容易地扩展以满足计算需求。

EC2 控制台将为您提供涵盖存储计算和安全性的几乎无与伦比的功能和服务。我们将着重于启动一个实例，这将涉及与安全和存储特性的少量交互，但是启动向导使这一切变得非常容易处理。

找到橙色的“启动实例”下拉按钮，并选择“启动实例”。在这里，您将看到一个 ami 列表。寻找实例徽标下有“符合自由层条件”的产品。选择要使用的 Linux 实例。

接下来，实例类型允许您选择实例的计算能力。使用免费层“t2.micro”实例，您可以获得惊人的数量。选中后，单击“下一步:配置实例”。

Configure Instance 步骤中的所有缺省值都应该没问题，但是值得通读它们，以了解您可以控制什么。一个重要的设置是“IAM 角色”。指定的角色使您的实例能够与其他服务进行交互。AWS 遵循最小特权的通用安全概念，这意味着您的实例不能与任何东西进行交互，除非得到特别的许可。

另一个有趣的字段是底部的“用户数据”。这可以是实例启动时运行的脚本。如果您经常启动实例，并要求它们具有相同的设置，如安装包或运行服务，这将非常方便。

接下来，添加存储。这里需要注意的一点是，当一个实例被销毁时，存储在其上的所有数据也会消失。弹性块存储(EBS)允许您拥有持久的数据，您可以在实例之间移动这些数据。每个块一次只能连接到一个实例。如果您想了解如何在 Linux 中管理存储，比如使用分区和逻辑卷，那么在这里添加一些代码块，让您在启动时有所收获。

接下来，添加标签。这对于识别资源很有用。当您的云基础架构开始增长时，拥有一个良好的标记策略是很有价值的，并且还可以帮助管理使用成本。

接下来，配置安全组。把一个安全组想象成一个名为 Your-EC2 的高级夜总会的保镖名单。如果你在名单上，你被允许进入实例，其他人都可以去 Wetherspoons。这也是最低特权安全原则的应用。现在，我们只需要允许从您的个人计算机进行 SSH 连接。将来，您可能希望允许 web 或数据库流量访问其他端口。

要设置这一点，缺省值应该可以让您开始，类型为 SSH，协议为 TCP，端口为 22。您需要将源设置为您的 IP。幸运的是，这很容易。点击来源栏中的下拉，选择“我的 IP”。然后给这个规则一个描述。

审核并启动！仔细检查您的所有设置，然后单击启动。会出现一个弹出窗口，让您选择一个密钥对。密钥对支持密钥持有者和实例之间的安全通信。从第一个下拉列表中选择“创建新的密钥对”，并为其命名。按键与您正在启动的区域相关，并且只能在该区域访问。

下载密钥后，您就可以启动实例了。

回到 EC2 控制台，您可以从左边的资源部分或导航栏中选择实例。您应该会看到一个包含新实例的表格，并且状态会很快变为 running。一旦运行，你可以连接到它。复制实例的公共 IP 并打开您的终端。

您可能需要将文件所有者对文件的权限更改为只读，这可以通过命令`chmod 400 your-key.pem`来完成。

在您的终端中，您可以运行以下命令来连接到您的实例:

```
ssh -i AWS-KEY.pem ubuntu@3.10.72.41
```

命令分解成以下几个部分:

```
ssh -i <yourkey> <username>@<public-ip>
```

用您的密钥文件替换`AWS-KEY.pem`。请记住，您需要位于保存密钥的文件夹中，或者提供密钥位置的绝对路径。比如说`/Users/Me/Downloads/aws-key.pem`。

如果你使用的是 Ubuntu AMI，你可以把 Ubuntu 留在那里，只需要改变你的实例的 IP 地址。如果您使用不同的 AMI，您需要将 ubuntu 更改为在您的实例上创建的用户名。AWS 可以在这方面提供一些帮助。选择实例后，单击右上角的 Actions，然后连接。在 SSH 客户端下，您将得到一个如何连接的演练。

就这样，你被录取了。你现在有了一台全新的电脑。托管网站、编译项目或了解 Linux 的来龙去脉。

为了了解 Linux 的基础知识，[阅读这篇文章，学习如何导航和管理目录和文件。](https://max-a-raju.medium.com/getting-to-grips-with-linux-27c1ce12f313)

如果你想更深入地了解 AWS，[阅读这篇关于使用 CloudFormation 创建基础设施的文章](https://max-a-raju.medium.com/an-introduction-to-cloudformation-awss-infrastructure-as-code-234331cf4817)。

希望这份指南能让你有所行动。欢迎评论或提问！