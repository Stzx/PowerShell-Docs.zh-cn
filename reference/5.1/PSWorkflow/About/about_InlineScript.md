---
description: 描述 `InlineScript` 在工作流中运行 PowerShell 命令的活动。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_inlinescript?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_InlineScript
ms.openlocfilehash: 2eaeb02c6441865551b586e27a39c4000826752b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199906"
---
# <a name="about-inlinescript"></a><span data-ttu-id="ce7a9-104">关于 InlineScript</span><span class="sxs-lookup"><span data-stu-id="ce7a9-104">About InlineScript</span></span>

## <a name="short-description"></a><span data-ttu-id="ce7a9-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="ce7a9-105">Short description</span></span>

<span data-ttu-id="ce7a9-106">描述 `InlineScript` 在工作流中运行 PowerShell 命令的活动。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-106">Describes the `InlineScript` activity, that runs PowerShell commands in a workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="ce7a9-107">长说明</span><span class="sxs-lookup"><span data-stu-id="ce7a9-107">Long description</span></span>

<span data-ttu-id="ce7a9-108">`InlineScript`活动在共享 PowerShell 会话的工作流中运行命令。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-108">The `InlineScript` activity runs commands in a shared PowerShell session's workflow.</span></span> <span data-ttu-id="ce7a9-109">`InlineScript` 仅在工作流中有效。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-109">`InlineScript` is only valid in workflows.</span></span>

## <a name="syntax"></a><span data-ttu-id="ce7a9-110">语法</span><span class="sxs-lookup"><span data-stu-id="ce7a9-110">Syntax</span></span>

```
InlineScript {<script block>} <ActivityCommonParameters>
```

## <a name="detailed-description"></a><span data-ttu-id="ce7a9-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="ce7a9-111">Detailed description</span></span>

<span data-ttu-id="ce7a9-112">`InlineScript`活动在共享 PowerShell 会话中运行命令。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-112">The `InlineScript` activity runs commands in a shared PowerShell session.</span></span> <span data-ttu-id="ce7a9-113">可以将其包含在工作流中，以运行共享不在工作流中无效的数据和命令的命令。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-113">You can include it in a workflow to run commands that share data and commands that aren't otherwise valid in a workflow.</span></span>

<span data-ttu-id="ce7a9-114">`InlineScript`脚本块可以包括所有有效的 PowerShell 命令和表达式。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-114">The `InlineScript` script block can include all valid PowerShell commands and expressions.</span></span> <span data-ttu-id="ce7a9-115">由于脚本块中的命令和表达式 `InlineScript` 在同一会话中运行，因此它们共享所有状态和数据，包括导入的模块和变量的值。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-115">Because the commands and expressions in an `InlineScript` script block run in the same session, they share all state and data, including imported modules and the values of variables.</span></span>

<span data-ttu-id="ce7a9-116">您可以将 `InlineScript` 活动放置在工作流或嵌套工作流中的任意位置，包括在循环或控制语句或并行或序列脚本块中。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-116">You can place an `InlineScript` activity anywhere in a workflow or nested workflow, including inside a loop or control statement or a Parallel or Sequence script block.</span></span>

<span data-ttu-id="ce7a9-117">`InlineScript`活动具有活动通用参数，包括 **PSPersist** 。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-117">The `InlineScript` activity has the activity common parameters, including **PSPersist** .</span></span> <span data-ttu-id="ce7a9-118">但是，脚本块中的命令和表达式 `InlineScript` 不具有工作流功能，如检查点或持久性、工作流或活动通用参数。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-118">However, the commands and expressions in an `InlineScript` script block don't have the workflow features such as checkpointing, or persistence, and workflow or activity common parameters.</span></span> <span data-ttu-id="ce7a9-119">有关详细信息，请参阅 [about_ActivityCommonParameters](about_ActivityCommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-119">For more information, see [about_ActivityCommonParameters](about_ActivityCommonParameters.md).</span></span>

## <a name="inlinescript-variables"></a><span data-ttu-id="ce7a9-120">InlineScript 变量</span><span class="sxs-lookup"><span data-stu-id="ce7a9-120">InlineScript Variables</span></span>

<span data-ttu-id="ce7a9-121">默认情况下，工作流中定义的变量对脚本块中的命令不可见 `InlineScript` 。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-121">By default, the variables that are defined in a workflow aren't visible to the commands in the `InlineScript` script block.</span></span> <span data-ttu-id="ce7a9-122">若要使工作流变量对可见 `InlineScript` ，请使用 `$Using` 作用域修饰符。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-122">To make workflow variables visible to the `InlineScript`, use the `$Using` scope modifier.</span></span> <span data-ttu-id="ce7a9-123">`$Using`对于中的每个变量，只需要作用域修饰符一次 `InlineScript` 。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-123">The `$Using` scope modifier is required only once for each variable in the `InlineScript`.</span></span>

<span data-ttu-id="ce7a9-124">有关 `$Using` 作用域修饰符的详细信息，请参阅 [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-124">For more information about the `$Using` scope modifier, see [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span></span>

<span data-ttu-id="ce7a9-125">下面的示例演示 `$Using` 作用域修饰符使 `$a` 顶级工作流变量的值对脚本块中的命令可用 `InlineScript` 。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-125">The following example shows that the `$Using` scope modifier makes the value of the `$a` top-level workflow variable available to the commands in the `InlineScript` script block.</span></span>

```powershell
workflow Test-Workflow {
  $a = 3

  ## Without $Using, the $a workflow variable isn't visible
  ## in inline script.
  InlineScript {"Inline A0 = $a"}

  ## $Using imports the variable and its current value.
  InlineScript {"Inline A1 = $Using:a"}
}

Test-Workflow
```

```output
Inline A0 =
Inline A1 = 3
```

## <a name="returning-variables-in-inlinescript"></a><span data-ttu-id="ce7a9-126">返回 InlineScript 中的变量</span><span class="sxs-lookup"><span data-stu-id="ce7a9-126">Returning variables in InlineScript</span></span>

<span data-ttu-id="ce7a9-127">`InlineScript` 命令可以更改从工作流作用域导入的变量的值，但这些更改在工作流作用域中不可见。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-127">`InlineScript` commands can change the value of the variable that was imported from workflow scope, but the changes aren't visible in workflow scope.</span></span> <span data-ttu-id="ce7a9-128">若要使其可见，则将更改的值返回到工作流作用域，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-128">To make them visible, return the changed value to the workflow scope, as shown in the following example.</span></span>

```powershell
workflow Test-Workflow {
  $a = 3

  ##  Changes to the InlineScript variable value don't
  ##  change the workflow variable.
  InlineScript {
    $a = $Using:a+1;
    "Inline A = $a"
  }
  "Workflow A = $a"

  ##  To change the variable in workflow scope, return the
  ##  new value.
  $a = InlineScript {$b = $Using:a+1; $b}
  "Workflow New A = $a"
}

Test-Workflow
```

```output
Inline A = 4
Workflow A = 3
Workflow New A = 4
```

> [!NOTE]
> <span data-ttu-id="ce7a9-129">具有 `$Using` 作用域修饰符的语句应出现在脚本块中任何变量的使用之前 `InlineScript` 。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-129">A statement with the `$Using` scope modifier should appear before any use of the variable in the `InlineScript` script block.</span></span>

## <a name="running-in-process"></a><span data-ttu-id="ce7a9-130">正在进程内运行</span><span class="sxs-lookup"><span data-stu-id="ce7a9-130">Running in-process</span></span>

<span data-ttu-id="ce7a9-131">为了提高可靠性， `InlineScript` 脚本块中的命令在其自己的进程中运行，不同于工作流的运行进程，然后将其输出返回到工作流进程。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-131">To improve reliability, the commands in the `InlineScript` script block run in their own process, separate from the process in which the workflow runs, and then return their output to the workflow process.</span></span>

<span data-ttu-id="ce7a9-132">若要指示 PowerShell 运行 `InlineScript` 工作流进程中的活动，请 `InlineScript` 从会话配置的 **OutOfProcessActivity** 属性中删除该值，如使用 `New-PSWorkflowExecutionOption` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-132">To direct PowerShell to run the `InlineScript` activity in the workflow process, remove the `InlineScript` value from the **OutOfProcessActivity** property of the session configuration, such as by using the `New-PSWorkflowExecutionOption` cmdlet.</span></span>

### <a name="example"></a><span data-ttu-id="ce7a9-133">示例</span><span class="sxs-lookup"><span data-stu-id="ce7a9-133">Example</span></span>

<span data-ttu-id="ce7a9-134">`InlineScript`以下工作流中的包含在 PowerShell 中有效但在工作流中无效的命令。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-134">The `InlineScript` in the following workflow includes commands that are valid in PowerShell but aren't valid in workflows.</span></span> <span data-ttu-id="ce7a9-135">例如， `New-Object` 带有 **ComObject** 参数的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ce7a9-135">For example, the `New-Object` cmdlet with the **ComObject** parameter.</span></span>

```powershell
workflow Test-Workflow
{
  $ie = InlineScript {
    $ie = New-Object -ComObject InternetExplorer.Application -Property @{navigate2="www.microsoft.com"}

    $ie.Visible = $true
  }

  $ie
}

Test-Workflow
```

## <a name="see-also"></a><span data-ttu-id="ce7a9-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce7a9-136">See also</span></span>

[<span data-ttu-id="ce7a9-137">about_ActivityCommonParameters</span><span class="sxs-lookup"><span data-stu-id="ce7a9-137">about_ActivityCommonParameters</span></span>](about_ActivityCommonParameters.md)

[<span data-ttu-id="ce7a9-138">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="ce7a9-138">about_Remote_Variables</span></span>](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)

[<span data-ttu-id="ce7a9-139">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="ce7a9-139">about_WorkflowCommonParameters</span></span>](about_WorkflowCommonParameters.md)

<span data-ttu-id="ce7a9-140">[PSWorkflow](xref:PSWorkflow) cmdlet</span><span class="sxs-lookup"><span data-stu-id="ce7a9-140">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="ce7a9-141">工作流指南</span><span class="sxs-lookup"><span data-stu-id="ce7a9-141">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="ce7a9-142">编写 Windows PowerShell 工作流</span><span class="sxs-lookup"><span data-stu-id="ce7a9-142">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
