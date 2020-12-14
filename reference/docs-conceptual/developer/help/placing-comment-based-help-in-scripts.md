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
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="fdacd-103">在脚本中放置基于注释的帮助</span><span class="sxs-lookup"><span data-stu-id="fdacd-103">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="fdacd-104">本主题介绍在何处放置脚本的基于注释的帮助，以便该 `Get-Help` cmdlet 将基于注释的帮助主题与脚本关联，而不是与脚本中可能包含的任何函数关联。</span><span class="sxs-lookup"><span data-stu-id="fdacd-104">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="fdacd-105">在何处放置脚本 Comment-Based 帮助</span><span class="sxs-lookup"><span data-stu-id="fdacd-105">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="fdacd-106">位于脚本文件的开头。</span><span class="sxs-lookup"><span data-stu-id="fdacd-106">At the beginning of the script file.</span></span>

  <span data-ttu-id="fdacd-107">脚本帮助的前面只能是注释和空行。</span><span class="sxs-lookup"><span data-stu-id="fdacd-107">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="fdacd-108">脚本文件末尾。</span><span class="sxs-lookup"><span data-stu-id="fdacd-108">At the end of the script file.</span></span>

  <span data-ttu-id="fdacd-109">如果在 "帮助") 后 (脚本正文中的第一项是函数声明，则脚本的末尾和函数声明之间必须至少有两个空行。</span><span class="sxs-lookup"><span data-stu-id="fdacd-109">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="fdacd-110">否则，"帮助" 将被解释为该函数的帮助，而不是脚本的帮助。</span><span class="sxs-lookup"><span data-stu-id="fdacd-110">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="fdacd-111">脚本中帮助位置的示例</span><span class="sxs-lookup"><span data-stu-id="fdacd-111">Examples of Help Placement in a Script</span></span>

<span data-ttu-id="fdacd-112">下面的示例显示了每个用于脚本的基于注释的帮助的放置选项。</span><span class="sxs-lookup"><span data-stu-id="fdacd-112">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="fdacd-113">脚本开始的帮助</span><span class="sxs-lookup"><span data-stu-id="fdacd-113">Help at the Beginning of a Script</span></span>

<span data-ttu-id="fdacd-114">下面的示例显示了脚本开始时的注释。</span><span class="sxs-lookup"><span data-stu-id="fdacd-114">The following example shows comment-based at the beginning of a script.</span></span>

```powershell
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="fdacd-115">脚本结束时的帮助</span><span class="sxs-lookup"><span data-stu-id="fdacd-115">Help at the End of a Script</span></span>

 <span data-ttu-id="fdacd-116">下面的示例显示了脚本结束时的注释。</span><span class="sxs-lookup"><span data-stu-id="fdacd-116">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>
```
