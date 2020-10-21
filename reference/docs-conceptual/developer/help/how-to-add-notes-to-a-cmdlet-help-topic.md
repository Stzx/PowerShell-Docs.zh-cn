---
title: 如何向 Cmdlet 帮助主题添加备注
ms.date: 10/20/2020
ms.openlocfilehash: 7f8be34a82de2c12cfd2a05deed139ddb30da95f
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "92298310"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="cee20-102">如何向 Cmdlet 帮助主题添加备注</span><span class="sxs-lookup"><span data-stu-id="cee20-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="cee20-103">本部分介绍了如何将“备注”部分添加到 PowerShell cmdlet 帮助主题中。</span><span class="sxs-lookup"><span data-stu-id="cee20-103">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="cee20-104">“备注”部分用于解释不容易归入其他结构化部分的细节，如对参数的更详细解释。</span><span class="sxs-lookup"><span data-stu-id="cee20-104">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="cee20-105">此内容可能包括有关 cmdlet 如何与特定提供程序一起使用的注释、一些独特但重要的 cmdlet 用法，或避免可能出现错误情况的方法。</span><span class="sxs-lookup"><span data-stu-id="cee20-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="cee20-106">“备注”部分是使用单个 `<maml:alertset>` 节点定义的。</span><span class="sxs-lookup"><span data-stu-id="cee20-106">The **NOTES** section is defined using a single `<maml:alertset>` node.</span></span> <span data-ttu-id="cee20-107">可以添加到“备注”部分中的备注数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="cee20-107">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="cee20-108">对于每个备注，将一对 `<maml:alert>` 标记添加到 `<maml:alertset>` 节点。</span><span class="sxs-lookup"><span data-stu-id="cee20-108">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="cee20-109">每个备注的内容都添加在一组 `<maml:para>` 标记中。</span><span class="sxs-lookup"><span data-stu-id="cee20-109">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="cee20-110">使用空白 `<maml:para>` 标记作为间距。</span><span class="sxs-lookup"><span data-stu-id="cee20-110">Use blank `<maml:para>` tags for spacing.</span></span>

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
