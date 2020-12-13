---
ms.date: 09/12/2016
ms.topic: reference
title: 在函数中放置基于注释的帮助
description: 在函数中放置基于注释的帮助
ms.openlocfilehash: 3bd72f0c71d8f6ad54c43c99f044423c072fdeeb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658211"
---
# <a name="placing-comment-based-help-in-functions"></a><span data-ttu-id="a3e41-103">在函数中放置基于注释的帮助</span><span class="sxs-lookup"><span data-stu-id="a3e41-103">Placing Comment-Based Help in Functions</span></span>

<span data-ttu-id="a3e41-104">本主题介绍在何处放置函数的基于注释的帮助，以便该 `Get-Help` cmdlet 将基于注释的帮助主题与正确的函数相关联。</span><span class="sxs-lookup"><span data-stu-id="a3e41-104">This topic explains where to place comment-based help for a function so that the `Get-Help` cmdlet associates the comment-based help topic with the correct function.</span></span>

## <a name="where-to-place-comment-based-help-for-a-function"></a><span data-ttu-id="a3e41-105">函数 Comment-Based 帮助的位置</span><span class="sxs-lookup"><span data-stu-id="a3e41-105">Where to Place Comment-Based Help for a Function</span></span>

- <span data-ttu-id="a3e41-106">函数体的开头。</span><span class="sxs-lookup"><span data-stu-id="a3e41-106">At the beginning of the function body.</span></span>

- <span data-ttu-id="a3e41-107">函数体的末尾。</span><span class="sxs-lookup"><span data-stu-id="a3e41-107">At the end of the function body.</span></span>

- <span data-ttu-id="a3e41-108">关键字之前 `Function` 。</span><span class="sxs-lookup"><span data-stu-id="a3e41-108">Before the `Function` keyword.</span></span> <span data-ttu-id="a3e41-109">当函数在脚本或脚本模块中时，基于注释的帮助的最后一行与关键字之间不能有多个空行 `Function` 。</span><span class="sxs-lookup"><span data-stu-id="a3e41-109">When the function is in a script or script module, there cannot be more than one blank line between the last line of the comment-based help and the `Function` keyword.</span></span> <span data-ttu-id="a3e41-110">否则， `Get-Help` 将帮助与脚本相关联，而不是与函数相关联。</span><span class="sxs-lookup"><span data-stu-id="a3e41-110">Otherwise, `Get-Help` associates the help with the script, not with the function.</span></span>

## <a name="examples-of-help-placement-in-a-function"></a><span data-ttu-id="a3e41-111">函数中帮助位置的示例</span><span class="sxs-lookup"><span data-stu-id="a3e41-111">Examples of Help Placement in a Function</span></span>

<span data-ttu-id="a3e41-112">下面的示例显示了三个位置选项中的每一个选项，用于为函数提供基于注释的帮助。</span><span class="sxs-lookup"><span data-stu-id="a3e41-112">The following examples show each of the three placement options for comment-based help for a function.</span></span>

### <a name="help-at-the-beginning-of-a-function-body"></a><span data-ttu-id="a3e41-113">函数体开始的帮助</span><span class="sxs-lookup"><span data-stu-id="a3e41-113">Help at the Beginning of a Function Body</span></span>

<span data-ttu-id="a3e41-114">下面的示例显示了函数体开头的注释。</span><span class="sxs-lookup"><span data-stu-id="a3e41-114">The following example shows comment-based at the beginning of a function body.</span></span>

```powershell
function MyProcess
{
    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>

    Get-Process powershell
}
```

### <a name="help-at-the-end-of-a-function-body"></a><span data-ttu-id="a3e41-115">函数体末尾的帮助</span><span class="sxs-lookup"><span data-stu-id="a3e41-115">Help at the End of a Function Body</span></span>

 <span data-ttu-id="a3e41-116">下面的示例显示了函数体末尾的注释。</span><span class="sxs-lookup"><span data-stu-id="a3e41-116">The following example shows comment-based at the end of a function body.</span></span>

```powershell
function MyFunction
{
    Get-Process powershell

    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>
}
```

### <a name="help-before-the-function-keyword"></a><span data-ttu-id="a3e41-117">函数关键字之前的帮助</span><span class="sxs-lookup"><span data-stu-id="a3e41-117">Help Before the Function Keyword</span></span>

 <span data-ttu-id="a3e41-118">下面的示例显示了基于函数关键字之前的行的注释。</span><span class="sxs-lookup"><span data-stu-id="a3e41-118">The following examples shows comment-based on the line before the function keyword.</span></span>

```powershell
<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}
```
