---
ms.date: 10/20/2020
ms.topic: reference
title: 如何向 Cmdlet 帮助主题添加备注
description: 如何向 Cmdlet 帮助主题添加备注
ms.openlocfilehash: 61363c26ab0172277d1332ed1e9de080d8da200c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659561"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="44e7d-103">如何向 Cmdlet 帮助主题添加备注</span><span class="sxs-lookup"><span data-stu-id="44e7d-103">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="44e7d-104">本部分介绍了如何将“备注”部分添加到 PowerShell cmdlet 帮助主题中。</span><span class="sxs-lookup"><span data-stu-id="44e7d-104">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="44e7d-105">“备注”部分用于解释不容易归入其他结构化部分的细节，如对参数的更详细解释。</span><span class="sxs-lookup"><span data-stu-id="44e7d-105">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="44e7d-106">此内容可能包括有关 cmdlet 如何与特定提供程序一起使用的注释、一些独特但重要的 cmdlet 用法，或避免可能出现错误情况的方法。</span><span class="sxs-lookup"><span data-stu-id="44e7d-106">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="44e7d-107">“备注”部分是使用单个 `<maml:alertset>` 节点定义的。</span><span class="sxs-lookup"><span data-stu-id="44e7d-107">The **NOTES** section is defined using a single `<maml:alertset>` node.</span></span> <span data-ttu-id="44e7d-108">可以添加到“备注”部分中的备注数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="44e7d-108">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="44e7d-109">对于每个备注，将一对 `<maml:alert>` 标记添加到 `<maml:alertset>` 节点。</span><span class="sxs-lookup"><span data-stu-id="44e7d-109">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="44e7d-110">每个备注的内容都添加在一组 `<maml:para>` 标记中。</span><span class="sxs-lookup"><span data-stu-id="44e7d-110">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="44e7d-111">使用空白 `<maml:para>` 标记作为间距。</span><span class="sxs-lookup"><span data-stu-id="44e7d-111">Use blank `<maml:para>` tags for spacing.</span></span>

```xml
<maml:alertSet>
  <maml:title>Optional title for Note</maml:title>
  <maml:alert>
    <maml:para>Note 1</maml:para>
    <maml:para>Note a</maml:para>
  </maml:alert>
  <maml:alert>
    <maml:para>Note 2</maml:para>
  </maml:alert>
</maml:alertSet>
```
