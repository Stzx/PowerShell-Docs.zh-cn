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
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>如何向 Cmdlet 帮助主题添加备注

本部分介绍如何将 "**注释**" 部分添加到 PowerShell cmdlet 帮助主题。 "**注释**" 部分用于解释不能轻松地加入其他结构化部分的详细信息，如更详细的参数说明。 此内容可能包括有关 cmdlet 如何与特定提供程序一起使用的注释、对 cmdlet 的一些独特但重要的使用，或者用于避免可能的错误情况的方法。

可以添加到注释部分的便笺数量没有限制。 对于每个注释，将一对 `<maml:alert>` 标记添加到 `<maml:alertset>` 节点。 每个注释的内容会添加到一组 `<maml:para>` 标记中。 使用空白 `<maml:para>` 标记进行间距。

下面的 XML 演示 `<maml:alertset>` 具有两个注释的节点。 请注意，每个注释都有一个可选 `<maml:title>` 标记（标题可用于对任意一组标记进行分组 `<maml:alert>` ），并且每个注释在内容后均为空白行。

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
