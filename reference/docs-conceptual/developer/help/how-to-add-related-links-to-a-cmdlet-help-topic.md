---
title: 如何向 Cmdlet 帮助主题添加相关链接
ms.date: 09/12/2016
ms.openlocfilehash: 7557b3856d8470434070dd286cd7e30c9ba015c5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893367"
---
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a>如何向 Cmdlet 帮助主题添加相关链接

本部分介绍如何添加对与 PowerShell cmdlet 帮助主题相关的其他内容的引用。 由于这些引用显示在命令窗口中，因此它们不会直接链接到引用的内容。

在 PowerShell 中包含的 cmdlet 帮助主题中，这些链接引用其他 cmdlet、概念内容（ `about_` ），以及其他不与 PowerShell 相关的文档和帮助文件。

下面的 XML 演示如何将包含两个引用的**RelatedLinks**节点添加到相关主题。

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
