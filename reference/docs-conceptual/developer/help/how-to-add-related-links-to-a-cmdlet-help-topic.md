---
ms.date: 09/12/2016
ms.topic: reference
title: 如何向 Cmdlet 帮助主题添加相关链接
description: 如何向 Cmdlet 帮助主题添加相关链接
ms.openlocfilehash: 7f1baefea69310bdf835c52461f8d3f49c4d94e8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662000"
---
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a><span data-ttu-id="79512-103">如何向 Cmdlet 帮助主题添加相关链接</span><span class="sxs-lookup"><span data-stu-id="79512-103">How to Add Related Links to a Cmdlet Help Topic</span></span>

<span data-ttu-id="79512-104">本部分介绍如何添加对与 PowerShell cmdlet 帮助主题相关的其他内容的引用。</span><span class="sxs-lookup"><span data-stu-id="79512-104">This section describes how to add references to other content that is related to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="79512-105">由于这些引用显示在命令窗口中，因此它们不会直接链接到引用的内容。</span><span class="sxs-lookup"><span data-stu-id="79512-105">Because these references appear in a command window, they do not link directly to the referenced content.</span></span>

<span data-ttu-id="79512-106">在 PowerShell 中包含的 cmdlet 帮助主题中，这些链接引用其他 cmdlet、概念内容 (`about_`) 以及其他与 PowerShell 无关的文档和帮助文件。</span><span class="sxs-lookup"><span data-stu-id="79512-106">In the cmdlet Help topics that are included in PowerShell, these links reference other cmdlets, conceptual content (`about_`), and other documents and Help files that are not related to PowerShell.</span></span>

<span data-ttu-id="79512-107">下面的 XML 演示如何将包含两个引用的 **RelatedLinks** 节点添加到相关主题。</span><span class="sxs-lookup"><span data-stu-id="79512-107">The following XML shows how to add a **RelatedLinks** node that contains two references to related topics.</span></span>

```xml
<maml:relatedLinks>
  <maml:navigationLink>
    <maml:linkText>Topic-name</maml:linkText>
  </maml:navigationLink>
  <maml:navigationLink>
    <maml:linkText>Topic-name</maml:linkText>
  </maml:navigationLink>
</ maml:relatedLinks >
```
