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
# <a name="about-inlinescript"></a>关于 InlineScript

## <a name="short-description"></a>简短说明

描述 `InlineScript` 在工作流中运行 PowerShell 命令的活动。

## <a name="long-description"></a>长说明

`InlineScript`活动在共享 PowerShell 会话的工作流中运行命令。 `InlineScript` 仅在工作流中有效。

## <a name="syntax"></a>语法

```
InlineScript {<script block>} <ActivityCommonParameters>
```

## <a name="detailed-description"></a>详细说明

`InlineScript`活动在共享 PowerShell 会话中运行命令。 可以将其包含在工作流中，以运行共享不在工作流中无效的数据和命令的命令。

`InlineScript`脚本块可以包括所有有效的 PowerShell 命令和表达式。 由于脚本块中的命令和表达式 `InlineScript` 在同一会话中运行，因此它们共享所有状态和数据，包括导入的模块和变量的值。

您可以将 `InlineScript` 活动放置在工作流或嵌套工作流中的任意位置，包括在循环或控制语句或并行或序列脚本块中。

`InlineScript`活动具有活动通用参数，包括 **PSPersist** 。 但是，脚本块中的命令和表达式 `InlineScript` 不具有工作流功能，如检查点或持久性、工作流或活动通用参数。 有关详细信息，请参阅 [about_ActivityCommonParameters](about_ActivityCommonParameters.md)。

## <a name="inlinescript-variables"></a>InlineScript 变量

默认情况下，工作流中定义的变量对脚本块中的命令不可见 `InlineScript` 。 若要使工作流变量对可见 `InlineScript` ，请使用 `$Using` 作用域修饰符。 `$Using`对于中的每个变量，只需要作用域修饰符一次 `InlineScript` 。

有关 `$Using` 作用域修饰符的详细信息，请参阅 [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)。

下面的示例演示 `$Using` 作用域修饰符使 `$a` 顶级工作流变量的值对脚本块中的命令可用 `InlineScript` 。

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

## <a name="returning-variables-in-inlinescript"></a>返回 InlineScript 中的变量

`InlineScript` 命令可以更改从工作流作用域导入的变量的值，但这些更改在工作流作用域中不可见。 若要使其可见，则将更改的值返回到工作流作用域，如下面的示例所示。

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
> 具有 `$Using` 作用域修饰符的语句应出现在脚本块中任何变量的使用之前 `InlineScript` 。

## <a name="running-in-process"></a>正在进程内运行

为了提高可靠性， `InlineScript` 脚本块中的命令在其自己的进程中运行，不同于工作流的运行进程，然后将其输出返回到工作流进程。

若要指示 PowerShell 运行 `InlineScript` 工作流进程中的活动，请 `InlineScript` 从会话配置的 **OutOfProcessActivity** 属性中删除该值，如使用 `New-PSWorkflowExecutionOption` cmdlet。

### <a name="example"></a>示例

`InlineScript`以下工作流中的包含在 PowerShell 中有效但在工作流中无效的命令。 例如， `New-Object` 带有 **ComObject** 参数的 cmdlet。

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

## <a name="see-also"></a>另请参阅

[about_ActivityCommonParameters](about_ActivityCommonParameters.md)

[about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)

[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)

[PSWorkflow](xref:PSWorkflow) cmdlet

[工作流指南](/previous-versions/powershell/scripting/components/workflows-guide)

[编写 Windows PowerShell 工作流](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
