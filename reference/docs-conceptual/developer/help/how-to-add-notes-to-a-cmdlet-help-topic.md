---
title: 如何向 Cmdlet 帮助主题添加备注
ms.date: 09/12/2016
ms.openlocfilehash: d3679126ea34d7e86bcda700d0d050d8312a7aa2
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893401"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="6c71f-102">如何向 Cmdlet 帮助主题添加备注</span><span class="sxs-lookup"><span data-stu-id="6c71f-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="6c71f-103">本部分介绍如何将 "**注释**" 部分添加到 PowerShell cmdlet 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="6c71f-103">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="6c71f-104">"**注释**" 部分用于解释不能轻松地加入其他结构化部分的详细信息，如更详细的参数说明。</span><span class="sxs-lookup"><span data-stu-id="6c71f-104">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="6c71f-105">此内容可能包括有关 cmdlet 如何与特定提供程序一起使用的注释、对 cmdlet 的一些独特但重要的使用，或者用于避免可能的错误情况的方法。</span><span class="sxs-lookup"><span data-stu-id="6c71f-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="6c71f-106">可以添加到注释部分的便笺数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="6c71f-106">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="6c71f-107">对于每个注释，将一对 `<maml:alert>` 标记添加到 `<maml:alertset>` 节点。</span><span class="sxs-lookup"><span data-stu-id="6c71f-107">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="6c71f-108">每个注释的内容会添加到一组 `<maml:para>` 标记中。</span><span class="sxs-lookup"><span data-stu-id="6c71f-108">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="6c71f-109">使用空白 `<maml:para>` 标记进行间距。</span><span class="sxs-lookup"><span data-stu-id="6c71f-109">Use blank `<maml:para>` tags for spacing.</span></span>

<span data-ttu-id="6c71f-110">下面的 XML 演示 `<maml:alertset>` 具有两个注释的节点。</span><span class="sxs-lookup"><span data-stu-id="6c71f-110">The following XML shows an `<maml:alertset>` node with two notes.</span></span> <span data-ttu-id="6c71f-111">请注意，每个注释都有一个可选 `<maml:title>` 标记（标题可用于对任意一组标记进行分组 `<maml:alert>` ），并且每个注释在内容后均为空白行。</span><span class="sxs-lookup"><span data-stu-id="6c71f-111">Notice that each note has an optional `<maml:title>` tag (titles can be used to group any set of `<maml:alert>` tags), and that each note has a blank line following the content for spacing.</span></span>

```xml
<maml:alertSet>
  <maml:title>title for Note 1</maml:title>
  <maml:alert>
    <maml:para> Note 1</maml:para>
    <maml:para></maml:para>
  </maml:alert>
  <maml:title>title for Note 2</maml:title>
  <maml:alert>
    <maml:para> Note 1</maml:para>
    <maml:para></maml:para>
  </maml:alert>
</maml:alertSet>
```
