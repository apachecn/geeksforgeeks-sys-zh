# 网络安全中新出现的攻击媒介

> 原文:[https://www . geesforgeks . org/emerging-网络安全中的攻击媒介/](https://www.geeksforgeeks.org/emerging-attack-vectors-in-cyber-security/)

在本文中，我们将讨论一些新兴的攻击媒介，它们对 web 应用程序的安全性具有潜在的巨大影响。我们将介绍攻击向量、不安全的直接对象引用、相对路径覆盖、目录暴力强制。我们一个一个来讨论。

**攻击向量:**

*   攻击向量基本上是黑客或安全分析师用来渗透到目标应用程序中进行恶意使用或检查应用程序安全特性的方法。
*   每个有道德的黑客都有自己独特的攻击媒介来检查目标应用程序的安全性，这个应用程序可能会变成 web 应用程序或 android 应用程序，但在本文中我们主要关注 web 应用程序。
*   在本文中，您可以了解一些新兴的攻击媒介及其影响。如果且仅当您拥有检查其安全功能的合法权限时，您可以在应用程序上使用任何攻击媒介。未经应用程序所有者的许可，不要在应用程序上应用任何攻击媒介。未经合法许可，在应用程序中渗透是完全非法的。

**不安全直接对象引用:**

*   不安全直接对象引用俗称 **IDOR** ，它基本上是基于权限的漏洞，允许攻击者修改或访问属于应用程序其他用户的资源。
*   IDOR 漏洞背后的基本概念是应用程序的端点试图为修改和访问用户数据提供访问权限，数据可能包含图像、地址、文件，在某些情况下主要包含用户的用户名和密码。
*   现在，IDOR 是 web 应用程序常见和新兴攻击媒介，因为 IDOR 漏洞原因是访问权限，与权限相关问题无法自动或默认修复，因为在 web 应用程序中，权限因用户而异。
*   例如，在任何应用程序中，普通用户和主要用户具有不同的访问权限，普通用户和管理员具有不同的数据修改权限。
*   基本上这类漏洞无处不在，事实上是如此的普遍，以至于大部分的 web 应用都受此影响。

**相对路径覆盖:**

*   安全研究员加雷斯·海耶斯发现了新的攻击向量，即相对路径覆盖。RPO 利用浏览器在将 CSS 文件导入 DOM(文档对象模型)的过程中解释相对路径的方式，因此这种攻击也被称为**路径相对样式表导入** (PRSSI)。

```
Relative Path -
<link href="database/xyz.css" rel="stylesheet" type="text/css"/>
```

```
Absolute Path -
<link href="https://example.com /database/xyz.css" rel="stylesheet" type="text/css"/>
```

*   **Example –**
    For example, if the document was loaded at https://example.com /database then the CSS will be loaded from the path https://example.com /database/xyz.css in the case of relative path. If website has URL : https://example.com /index.html and they link the <link href=”resource/rpo.css” rel=”stylesheet” type=” text/CSS”/> given path in html file. 

    在这种情况下，如果我们访问 https://example.com/index . html 这个网址，那么网站可以通过给定的路径导入它的 CSS 文件，但是如果攻击者将网址更改为 https://example.com/index . htm/random/payload，由于服务器端编程语言和 web 框架的灵活性，它也可以工作，但是这次 CSS 不从 html 文件中给定的路径加载。通过在易受攻击的端点添加有效载荷，攻击者可以控制网络应用程序的 CSS。

**目录暴力强制:**

*   这是非常流行和简单的攻击向量，大多数有道德的黑客使用这个向量来寻找网络应用程序上隐藏和敏感的目录。有各种自动化工具可用于测试这种攻击媒介。
*   很多时候开发者忘记了隐藏敏感文件和目录，比如包含数据库用户名、密码、网站源代码等的文件。由于这种信息可能会在特定的端点泄漏，通过强力强制目录攻击可能会发现 web 应用程序的隐藏数据和敏感信息。
*   作为开发人员，最好对用户隐藏所有敏感目录。