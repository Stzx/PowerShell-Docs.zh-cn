---
title: 基于注释的帮助的语法
ms.date: 09/12/2016
ms.openlocfilehash: 950afecc39f9d27207f77547679faab700481458
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893214"
---
# <a name="syntax-of-comment-based-help"></a>基于注释的帮助的语法

本部分介绍基于注释的帮助的语法。

## <a name="syntax-diagram"></a>语法关系图

 基于注释的帮助的语法如下所示：

```
# .< help keyword>
# <help content>

-or -

<#
.< help keyword>
< help content>
#>
```

## <a name="syntax-description"></a>语法说明

 基于注释的帮助以一系列注释形式编写。 可以在 `#` 每行注释之前键入注释符号（），也可以使用 `<#` 和 `#>` 符号来创建注释块。 注释块内的所有行都解释为注释。

 基于注释的帮助的每个部分都由关键字定义，每个关键字前面有一个点（ `.` ）。 关键字可以按任意顺序出现。 关键字名称不区分大小写。

 注释块必须包含至少一个 help 关键字。 **例如**，某些关键字可以在同一注释块中出现多次。 每个关键字的帮助内容都从关键字后面的行开始，可以跨多行。

 基于注释的帮助主题中的所有行都必须是连续的。 如果基于注释的帮助主题遵循的注释不是帮助主题的一部分，则最后一个非帮助注释行与基于注释的帮助的开头之间必须至少有一个空白行。

 例如，下面的基于注释的帮助主题包含。Description 关键字及其值，这是对函数或脚本的描述。

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```
