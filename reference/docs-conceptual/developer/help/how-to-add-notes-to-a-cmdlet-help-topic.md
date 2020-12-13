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
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>如何向 Cmdlet 帮助主题添加备注

本部分介绍了如何将“备注”部分添加到 PowerShell cmdlet 帮助主题中。 “备注”部分用于解释不容易归入其他结构化部分的细节，如对参数的更详细解释。 此内容可能包括有关 cmdlet 如何与特定提供程序一起使用的注释、一些独特但重要的 cmdlet 用法，或避免可能出现错误情况的方法。

“备注”部分是使用单个 `<maml:alertset>` 节点定义的。 可以添加到“备注”部分中的备注数量没有限制。 对于每个备注，将一对 `<maml:alert>` 标记添加到 `<maml:alertset>` 节点。 每个备注的内容都添加在一组 `<maml:para>` 标记中。 使用空白 `<maml:para>` 标记作为间距。

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
