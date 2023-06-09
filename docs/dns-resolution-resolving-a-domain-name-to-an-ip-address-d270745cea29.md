# DNS 解析:将域名解析为 IP 地址

> 原文：<https://medium.com/codex/dns-resolution-resolving-a-domain-name-to-an-ip-address-d270745cea29?source=collection_archive---------4----------------------->

![](img/1dccbb798bd564972e41a5f6d624b555.png)

当你在浏览器中输入域名时会发生什么？

我们都知道计算机只懂 IP 地址不懂域名，那么域名是如何映射到 IP 地址的呢？

大多数人都知道有一个将域名转换成 IP 地址的 DNS 解析过程，但是这个过程是如何进行的呢？

这篇文章将涵盖将域名解析成相应 IP 地址的每一个步骤。

# **第一步:检查浏览器缓存**

如果这不是你第一次访问一个网站，有可能你的浏览器已经缓存了该 IP 地址。

这是为了提高性能，避免花费时间寻找 IP 地址。

如果是这种情况，那么该过程在此结束。

但是如果你是第一次访问这个网站，或者可能是很久以后，我们将不会有浏览器缓存

# **第二步:将解析转发给 OS**

如果浏览器没有找到缓存，它会对操作系统进行系统调用。发出的系统调用是 [gethostbyname](https://man7.org/linux/man-pages/man3/gethostbyname.3.html) 。

一旦进行了这个调用，操作系统就会查看文件 [/etc/nsswitch.conf](https://man7.org/linux/man-pages/man5/nsswitch.conf.5.html) 。

这个文件很可能有一个类似于

```
hosts:    files dns
```

这意味着它现在需要检查/etc/hosts 文件

# **第三步:/etc/hosts and and/etc/resolv . conf**

/etc/hosts 文件包含以下格式的条目

```
127.0.0.1 localhost.localdomain localhost
::1 localhost.localdomain localhost
```

操作系统检查/etc/hosts 文件中是否有请求域名的 DNS 条目。

如果找到条目，则返回相应的 IP 地址。如果/etc/hosts 文件中没有该域名的条目，它将对/etc/resolv.conf 文件进行 DNS 调用。

如果没有响应，将向该文件中的第一个 IP 地址发送 DNS 请求。

这通常是 DNS 解析器的 IP 地址。

# **步骤 4: DNS 解析器**

一旦 DNS 解析器收到 DNS 请求，它就会在缓存中查找。也许其他主机也向它查询了域名的解析，并且它的缓存中存在该条目。

如果是，它返回缓存的 IP 地址作为响应。

如果没有条目，DNS 解析器会将请求发送到根机构

# **第五步:根权限**

DNS 解析器拥有根权威名称服务器的 IP 地址。

这些名称服务器包含域扩展的权威名称服务器的 IP 地址。

因此，对于我们的例子，如果我们正在解析 medium.com，根权威服务器将查找 *com* 扩展的权威域名服务器的 IP 地址。

# **第六步:联系域名扩展的权威服务器**

根域名服务器返回 *com* 权威域名服务器的 IP 地址。

一旦我们的解析器(从第 4 步开始)得到这个 IP 地址，它就向 *com* 权威服务器发送一个 DNS 请求。

这个权威服务器查找它的记录并返回 medium.com 域名服务器的 IP 地址

# **第七步:获取最终的 DNS 记录**

一旦我们的解析器(来自步骤 4)收到 medium.com 域名服务器的 IP 地址，它就向它发送 DNS 查询。

这一次，域名服务器查看其 DNS 记录，并获取映射到 medium.com 的记录。

这可能是一个 A 记录，CNAME 或任何其他记录。

然后，这将作为响应发送给我们的 DNS 解析器。

如果是 A 记录，解析器会缓存 IP 地址并发送给我们的操作系统，操作系统会将其转发给浏览器。然后浏览器也会缓存它。

如果是 CNAME，则执行从步骤 4 到步骤 7 的完整过程，以将相应的 CNAME 解析为其 IP 地址。

# **一些基本要点**

现在我们知道了 DNS 解析的整个过程，让我们看看它有时会如何影响我们的日常生活。

因此，假设您的一个浏览器正在打开网站，而另一个浏览器显示一些错误。这很可能是因为 IP 地址已经改变，其中一个浏览器正在使用其缓存来解析 IP 地址。在这种情况下，只要缓存过期，一切都会恢复正常。

假设你的一个朋友在不同的州可以访问一个网站，但是你在打开这个网站时会遇到错误。这是相同的缓存问题，但这一次是在解析器级别。

虽然这些缓存问题很少发生，但是无论何时发生，我们都不知道发生了什么，它们似乎可以神奇地自我修复。

DNS 解析过程也解释了为什么拥有 CNAMEs 是一个性能问题。因为现在要打开你的网站，DNS 解析过程要进行两次(或者更多，如果 CNAME 指向另一个 CNAME)。