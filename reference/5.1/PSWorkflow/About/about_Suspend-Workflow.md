---
description: 描述 `Suspend-Workflow` 活动，该活动将挂起活动显示的工作流。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_suspend-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Suspend 工作流
ms.openlocfilehash: cbe5386ae5aa4bd863079fde240ddf2ce5384727
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199896"
---
# <a name="about-suspend-workflow"></a>关于 Suspend-Workflow

## <a name="short-description"></a>简短说明

描述 `Suspend-Workflow` 活动，该活动将挂起活动显示的工作流。

## <a name="long-description"></a>长说明

`Suspend-Workflow`活动从工作流中暂时停止工作流处理。 在挂起之前，Windows PowerShell 工作流将采用一个检查点，以便保留工作流的状态和数据，并且工作流可以从挂起点恢复。

若要恢复工作流，运行工作流的用户将使用 `Resume-Job` cmdlet。 无法从工作流中恢复工作流。

## <a name="syntax"></a>语法

```
workflow <Verb-Noun>
{
    Suspend-Workflow
}
```

## <a name="detailed-description"></a>详细说明

`Suspend-Workflow`暂时停止工作流并返回表示工作流作业的作业对象。 即使未将工作流作为作业运行，也会返回一个作业对象。 例如，使用 **AsJob** 工作流通用参数。 作业状态为 "已 **挂起** "。

可以使用作业 cmdlet 来管理挂起的工作流作业。 若要恢复工作流作业，请使用 `Resume-Job` cmdlet。

在恢复工作流作业时，工作流将继续执行活动后面的命令 `Suspend-Workflow` 。

例如，以下工作流包括 `Suspend-Workflow` 活动。
运行工作流时，它会运行该 `Get-Date` 活动，将其输出保存到 `$a` 变量中，然后挂起工作流，并返回一个作业对象，该对象表示挂起的工作流。 作业类型为 **PSWorkflowJob** 。

可以使用作业 cmdlet （如 `Get-Job` ）来管理工作流作业。

```powershell
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

Test-Suspend
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Suspended  True         localhost Test-Suspend
```

## <a name="resuming-a-workflow-job"></a>恢复工作流作业

若要恢复工作流作业，请使用 `Resume-Job` cmdlet。 `Resume-Job` cmdlet 会立即返回工作流作业对象（即使它可能尚未恢复）。 要等待作业恢复，请使用 **wait** 参数，或使用 `Get-Job` cmdlet 获取当前作业对象。

```powershell
Resume-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State    HasMoreData  Location  Command
--  ----  -------------  -----    -----------  --------  -------
8   Job8  PSWorkflowJob  Running  True         localhost Test-Suspend
```

```powershell
Get-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Completed  True         localhost Test-Suspend
```

## <a name="getting-the-output-of-a-workflow-job"></a>获取工作流作业的输出

若要获取工作流作业的输出，请使用 `Receive-Job` cmdlet。 输出显示工作流已在遵循 cmdlet 的命令处恢复 `Suspend-Workflow` 。 在 `$a` 挂起之前填充的变量的值可在工作流恢复时使用。

```powershell
Get-Job -Name Job8 | Receive-Job
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 19
Milliseconds      : 823
Ticks             : 198230041
TotalDays         : 0.000229432917824074
TotalHours        : 0.00550639002777778
TotalMinutes      : 0.330383401666667
TotalSeconds      : 19.8230041
TotalMilliseconds : 19823.0041
PSComputerName    : localhost
```

## <a name="see-also"></a>另请参阅

[about_Workflows](about_Workflows.md)

[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)

[PSWorkflow](xref:PSWorkflow) cmdlet

[工作流指南](/previous-versions/powershell/scripting/components/workflows-guide)

[编写 Windows PowerShell 工作流](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
