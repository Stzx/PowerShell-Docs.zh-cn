---
ms.date: 09/12/2016
ms.topic: reference
title: 在脚本中放置基于注释的帮助
description: 在脚本中放置基于注释的帮助
ms.openlocfilehash: b0d32b7ab063269085899a643b0c3a17da2073fc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645431"
---
# <a name="placing-comment-based-help-in-scripts"></a>在脚本中放置基于注释的帮助

本主题介绍在何处放置脚本的基于注释的帮助，以便该 `Get-Help` cmdlet 将基于注释的帮助主题与脚本关联，而不是与脚本中可能包含的任何函数关联。

## <a name="where-to-place-comment-based-help-for-a-script"></a>在何处放置脚本 Comment-Based 帮助

- 位于脚本文件的开头。

  脚本帮助的前面只能是注释和空行。

- 脚本文件末尾。

  如果在 "帮助") 后 (脚本正文中的第一项是函数声明，则脚本的末尾和函数声明之间必须至少有两个空行。 否则，"帮助" 将被解释为该函数的帮助，而不是脚本的帮助。

## <a name="examples-of-help-placement-in-a-script"></a>脚本中帮助位置的示例

下面的示例显示了每个用于脚本的基于注释的帮助的放置选项。

### <a name="help-at-the-beginning-of-a-script"></a>脚本开始的帮助

下面的示例显示了脚本开始时的注释。

```powershell
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a>脚本结束时的帮助

 下面的示例显示了脚本结束时的注释。

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>
```
