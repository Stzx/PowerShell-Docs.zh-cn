---
title: 简介
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: c48340b2fa6141d207c3f7948063f81971183780
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438218"
---
# <a name="introduction"></a><span data-ttu-id="7ce18-102">简介</span><span class="sxs-lookup"><span data-stu-id="7ce18-102">Introduction</span></span>

<table>
  <tr><td>
  <a href="https://leanpub.com/powershell101">
  <img src="media/powershell101-150x194.png" alt="PowerShell 101 (the book)" />
  </a>
  </td>
  <td colspan=2>
<span data-ttu-id="7ce18-103">此内容最初出现在 Mike F Robbins 所著的 <em>PowerShell 101</em> 一书中。</span><span class="sxs-lookup"><span data-stu-id="7ce18-103">This content originally appeared in the book <em>PowerShell 101</em> by Mike F Robbins.</span></span> <span data-ttu-id="7ce18-104">感谢 Mike 许可我们在此重复使用他所写的内容。</span><span class="sxs-lookup"><span data-stu-id="7ce18-104">We thank Mike for granting us permission to reuse his content here.</span></span> <span data-ttu-id="7ce18-105">此内容在原始出版物的基础上进行了编辑。</span><span class="sxs-lookup"><span data-stu-id="7ce18-105">The content has been edited from the original publication.</span></span> <span data-ttu-id="7ce18-106">你仍可以通过 <a href="https://leanpub.com/powershell101">PowerShell 101</a> 从 Leanpub 中获取原版书。</span><span class="sxs-lookup"><span data-stu-id="7ce18-106">You can still get the original book from Leanpub at <a href="https://leanpub.com/powershell101">PowerShell 101</a>.</span></span>
  </td></tr>
</table>

## <a name="who-is-this-book-for"></a><span data-ttu-id="7ce18-107">这本书的受众是谁？</span><span class="sxs-lookup"><span data-stu-id="7ce18-107">Who is this book for?</span></span>

<span data-ttu-id="7ce18-108">这是一本适用于想要学习 PowerShell 的人士的入门级书籍。</span><span class="sxs-lookup"><span data-stu-id="7ce18-108">This is an entry-level book for anyone wanting to learn PowerShell.</span></span>

<span data-ttu-id="7ce18-109">本书重点介绍在 Microsoft Active Directory 域环境中的 Windows 10 和 Windows Server 2016 上运行的 PowerShell 版本 5.1。</span><span class="sxs-lookup"><span data-stu-id="7ce18-109">This book focuses on PowerShell version 5.1 running on Windows 10 and Windows Server 2016 in a Microsoft Active Directory domain environment.</span></span> <span data-ttu-id="7ce18-110">但基本概念适用于在任何受支持的平台上运行的所有 PowerShell 版本。</span><span class="sxs-lookup"><span data-stu-id="7ce18-110">However, the basic concepts apply to all versions of PowerShell running on any supported platform.</span></span>

## <a name="about-this-book"></a><span data-ttu-id="7ce18-111">关于本书</span><span class="sxs-lookup"><span data-stu-id="7ce18-111">About this book</span></span>

<span data-ttu-id="7ce18-112">本书汇集了我开始学习 PowerShell 时希望有人告诉我的内容，以及我在过去 10 年中使用 PowerShell 时所学到的技巧、窍门和最佳做法。</span><span class="sxs-lookup"><span data-stu-id="7ce18-112">This book is a collection of what I wish someone would have told me when I started learning PowerShell, along with the tips, tricks, and best practices that I've learned while using PowerShell during the past 10 years.</span></span>

<span data-ttu-id="7ce18-113">本书尝试为刚开始使用 PowerShell 的用户提供成功所需的足够信息（而不是提供大量信息）。</span><span class="sxs-lookup"><span data-stu-id="7ce18-113">Instead of providing an enormous amount of information, this book attempts to provide a balance of enough information to be successful for someone who is just getting started with PowerShell.</span></span> <span data-ttu-id="7ce18-114">每个章节都包含指向特定帮助主题的链接，以便为那些想要详细了解本章所介绍的主题的用户提供帮助。</span><span class="sxs-lookup"><span data-stu-id="7ce18-114">Each chapter contains links to specific help topics for those who want more information about the topics covered in that chapter.</span></span>

## <a name="about-the-author"></a><span data-ttu-id="7ce18-115">关于作者</span><span class="sxs-lookup"><span data-stu-id="7ce18-115">About the author</span></span>

<span data-ttu-id="7ce18-116">Mike F Robbins 是前 Microsoft MVP，“Windows PowerShell TFM 第 4 版”的合著者以及“PowerShell Deep Dives”一书的特约作者 。</span><span class="sxs-lookup"><span data-stu-id="7ce18-116">Mike F Robbins is a former Microsoft MVP, co-author of _Windows PowerShell TFM 4th Edition_, and a contributing author in the _PowerShell Deep Dives_ book.</span></span> <span data-ttu-id="7ce18-117">Mike 一直是 PowerShell 社区的坚定支持者，目前是 Microsoft 的 [Azure PowerShell][] 的首席作者。</span><span class="sxs-lookup"><span data-stu-id="7ce18-117">Mike has been a strong supporter of the PowerShell community and is now the lead writer for [Azure PowerShell][] at Microsoft.</span></span> <span data-ttu-id="7ce18-118">他通过 [mikefrobbins.com][] 发布博文，并且可通过 twitter [@mikefrobbins][] 找到他。</span><span class="sxs-lookup"><span data-stu-id="7ce18-118">He blogs at [mikefrobbins.com][] and can be found on twitter [@mikefrobbins][].</span></span>

## <a name="lab-environment"></a><span data-ttu-id="7ce18-119">实验室环境</span><span class="sxs-lookup"><span data-stu-id="7ce18-119">Lab environment</span></span>

<span data-ttu-id="7ce18-120">本书中的示例已在 Windows 10 周年版（内部版本 1607）和 Windows Server 2016 上使用 PowerShell 版本 5.1 进行了设计和测试。</span><span class="sxs-lookup"><span data-stu-id="7ce18-120">The examples in this book were designed and tested on Windows 10 Anniversary Edition (build 1607) and Windows Server 2016 using PowerShell version 5.1.</span></span> <span data-ttu-id="7ce18-121">如果使用的是其他版本的 PowerShell 或操作系统，结果可能会与此处显示的结果不同。</span><span class="sxs-lookup"><span data-stu-id="7ce18-121">If you're using a different version of PowerShell or operating system, your results may differ from those shown here.</span></span>

<!-- link references -->
[@mikefrobbins]: https://twitter.com/mikefrobbins
[mikefrobbins.com]: http://mikefrobbins.com/
[PowerShell 101]: https://leanpub.com/powershell101
[Azure PowerShell]: /powershell/azure
