---
title: 如何向 Cmdlet 帮助主题添加注释 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bea35e5-b680-4f86-b928-176890aac99d
caps.latest.revision: 5
ms.openlocfilehash: 1a365a167c245006bb882a542aedb5c43cfc4c96
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557101"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="fba97-102">如何向 Cmdlet 帮助主题添加备注</span><span class="sxs-lookup"><span data-stu-id="fba97-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="fba97-103">本部分介绍如何向 Windows PowerShell® cmdlet 帮助主题添加注释部分。</span><span class="sxs-lookup"><span data-stu-id="fba97-103">This section describes how to add a Notes section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="fba97-104">"注释" 部分用于解释不能轻松地加入其他结构化部分的详细信息，如更详细的参数说明。</span><span class="sxs-lookup"><span data-stu-id="fba97-104">The Notes section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="fba97-105">此内容可能包括有关 cmdlet 如何与特定提供程序一起使用的注释、对 cmdlet 的一些独特但重要的使用，或者用于避免可能的错误情况的方法。</span><span class="sxs-lookup"><span data-stu-id="fba97-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="fba97-106">可以添加到注释部分的便笺数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="fba97-106">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="fba97-107">对于每个注释，在 \< \< maml： alertset> 节点中添加一对 maml： alert> 标记。</span><span class="sxs-lookup"><span data-stu-id="fba97-107">For each note, add a pair of \<maml:alert> tags to the \<maml:alertset> node.</span></span> <span data-ttu-id="fba97-108">每个注释的内容添加在一组 \< maml：> 标记中。</span><span class="sxs-lookup"><span data-stu-id="fba97-108">The content of each note is added within a set of \<maml:para> tags.</span></span> <span data-ttu-id="fba97-109">使用空白 \< maml：段落> 标签进行间距。</span><span class="sxs-lookup"><span data-stu-id="fba97-109">Use blank \<maml:para> tags for spacing.</span></span>

<span data-ttu-id="fba97-110">以下 XML 显示了 \< maml： alertset> 具有两个注释的节点。</span><span class="sxs-lookup"><span data-stu-id="fba97-110">The following XML shows an \<maml:alertset> node with two notes.</span></span> <span data-ttu-id="fba97-111">请注意，每个注释都有一个可选的 \< maml： title> 标记（标题可用于对任何一组 \< maml： alert> 标记）进行分组，并且每个注释的内容后面都有一个空行。</span><span class="sxs-lookup"><span data-stu-id="fba97-111">Notice that each note has an optional \<maml:title> tag (titles can be used to group any set of \<maml:alert> tags), and that each note has a blank line following the content for spacing.</span></span>

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
