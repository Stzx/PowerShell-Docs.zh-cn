---
description: 介绍计划作业并说明如何在 PowerShell 和任务计划程序中使用和管理计划作业。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs
ms.openlocfilehash: 4d4e86957a584bb4deb47cadcd8588c1236455ac
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199915"
---
# <a name="about-scheduled-jobs"></a>关于计划作业

## <a name="short-description"></a>简短说明

介绍计划作业并说明如何在 PowerShell 和任务计划程序中使用和管理计划作业。

## <a name="long-description"></a>长说明

PowerShell 计划作业是 PowerShell 后台作业和任务计划程序任务的有用混合。

与 PowerShell 后台作业一样，计划作业在后台以异步方式运行。 可以使用作业 cmdlet （如、、和）管理已运行的计划作业的实例 `Start-Job` `Get-Job` `Stop-Job` `Receive-Job` 。

与任务计划程序任务一样，计划作业保存到磁盘。 可以在任务计划程序中查看和管理作业，根据需要启用和禁用这些作业，运行这些作业，或将其用作模板，建立用于启动作业的一次性或重复计划，或设置作业的开始时间。

此外，计划作业实例的结果将以易于访问的格式保存到磁盘，同时提供作业输出的运行日志。 计划作业附带一组用于管理它们的自定义 cmdlet。 Cmdlet 可用于创建、编辑、管理、禁用和重新启用计划作业、作业触发器和作业选项。

这一套全面的灵活的工具使计划的作业成为许多专业 PowerShell IT 解决方案的重要组成部分。

计划的作业 cmdlet 包含在随 PowerShell 一起安装的 **PSScheduledJob** 模块中。 此模块是在 PowerShell 3.0 中引入的，并且适用于 powershell 3.0 和更高版本的 PowerShell。 有关 **PSScheduledJob** 模块中包含的 cmdlet 的详细信息，请参阅 [PSScheduledJob](xref:PSScheduledJob)。

有关 PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md)。

有关任务计划程序的详细信息，请参阅 [任务计划程序](/windows/desktop/TaskSchd/task-scheduler-reference)。

> [!NOTE]
> 可以在任务计划程序中查看和管理 PowerShell 计划作业。 PowerShell 作业和计划作业 cmdlet 仅适用于在 PowerShell 中创建的计划作业。

## <a name="quick-start"></a>快速入门

此示例将创建一个计划作业，该作业在每天凌晨3:00 开始，并运行 `Get-Process` cmdlet。 即使计算机在电池上运行，也会启动该作业。

```powershell
$trigger = New-JobTrigger -Daily -At 3AM
$options = New-ScheduledJobOption -StartIfOnBattery
Register-ScheduledJob -Name ProcessJob -ScriptBlock {Get-Process} `
-Trigger $trigger -ScheduledJobOption $options
```

`Get-ScheduledJob`Cmdlet 将获取本地计算机上的计划作业。

```powershell
Get-ScheduledJob
```

```Output
Id         Name            Triggers        Command            Enabled
--         ----            --------        -------            -------
7          ProcessJob      {1}             Get-Process        True
```

`Get-JobTrigger` 获取 **ProcessJob** 的作业触发器。 输入参数指定计划的作业，而不是触发器，因为触发器保存在计划作业中。

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id         Frequency       Time                   DaysOfWeek        Enabled
--         ---------       ----                   ----------        -------
1          Daily           11/5/2011 3:00:00 AM                     True
```

此示例使用 cmdlet 的 **ContinueIfGoingOnBattery** 参数 `Set-ScheduledJob` 将 **ProcessJob** 的 **StopIfGoingOnBatteries** 属性更改为 **False** 。

```powershell
Get-ScheduledJob -Name ProcessJob | Set-ScheduledJobOption `
-ContinueIfGoingOnBattery -Passthru
```

```Output
StartIfOnBatteries     : True
StopIfGoingOnBatteries : False
WakeToRun              : True
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

`Get-ScheduledJob`Cmdlet 将获取 **ProcessJob** 计划作业。

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command        Enabled
--         ----            --------        -------        -------
7          ProcessJob      {1}             Get-Process    True
```

该 `Get-Job` cmdlet 将获取 **ProcessJob** 计划作业的所有已运行的实例。 `Get-Job`仅当 **PSScheduledJob** 模块导入到当前会话中时，cmdlet 才会获取计划作业。

> [!TIP]
> 请注意，使用计划作业 cmdlet 来管理计划作业，但使用作业 cmdlet 来管理计划作业的实例。

```powershell
Get-Job -Name ProcessJob
```

```Output
Id     Name        PSJobTypeName  State    HasMoreData   Location   Command
--     ----        ------------   -----    -----------   --------   -------
45     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
46     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
47     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
48     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
49     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
50     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
51     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
```

该 `Receive-Job` cmdlet 将获取 **ProcessJob** 计划作业的最新实例的结果 (ID = 51) 。

```powershell
Receive-Job -ID 51
```

即使该 `Receive-Job` 命令不包含 **Keep** 参数，该作业的结果也将保存在磁盘上，直到您删除它们或超出最大结果数。

作业结果在此会话中不再可用，但如果你启动新会话或打开新的 PowerShell 窗口，则该作业的结果将再次可用。

以下命令使用 cmdlet 的 **DefinitionName** 参数 `Start-Job` 来启动 **ProcessJob** 计划作业。

使用 cmdlet 启动的作业 `Start-Job` 是标准 PowerShell 后台作业，而不是计划作业的实例。 与所有后台作业一样，这些作业会立即启动，它们不受作业选项的影响，也不受作业触发器的影响，并且其输出不会保存在计划的作业目录的输出目录中。

```powershell
Start-Job -DefinitionName ProcessJob
```

`Unregister-ScheduledJob`Cmdlet 将删除 **ProcessJob** 计划作业及其所有已保存的作业实例结果。

```powershell
Unregister-ScheduledJob ProcessJob
```

## <a name="scheduled-jobs-concepts"></a>计划的作业概念

计划作业运行命令或脚本。 计划作业可以包括启动作业的作业触发器，以及用于设置运行作业的条件的作业选项。

作业触发器会自动启动计划作业。 作业触发器可以包含一次性或定期计划，或者指定事件，例如当用户登录或 Windows 启动时。 计划作业可以有一个或多个作业触发器，你可以创建、添加、启用、禁用和获取作业触发器。

作业触发器是可选的。 可以通过使用 `Start-Job cmdlet` 或将 **RunNow** 参数添加到命令，来立即启动计划作业 `Register-ScheduledJob` 。

作业选项设置运行计划作业的条件。 每个计划作业都有一个作业选项对象。 你可以创建和编辑作业选项对象，并将其添加到一个或多个计划作业。

每次启动计划作业时，将创建一个作业实例。 使用 PowerShell 作业 cmdlet 查看和管理作业实例。

计划作业保存到磁盘并使用 cmdlet 谓词， `Register` 而不是 `New` 。 XML 文件位于本地计算机上的目录中 `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` 。

PowerShell 为每个计划作业创建一个目录，并将作业命令、作业触发器、作业选项和作业结果保存在计划的作业目录中。 不会单独将作业触发器和作业选项保存到磁盘。
它们保存在与它们关联的每个计划作业的计划作业 XML 中。

计划作业、作业触发器和作业选项在 PowerShell 中显示为对象。
对象是了的，这使它们可以在命令和脚本中轻松发现和使用。

计划作业显示为 **ScheduledJobDefinition** 对象。 **ScheduledJobDefinition** 对象包含一个 **JobTriggers** 属性，该属性包含计划作业的作业触发器和一个包含作业选项的 **Options** 属性。 分别表示作业触发器和作业选项的 **ScheduledJobTriggers** 和 **ScheduledJobOptions** 对象，每个对象都有一个 **JobDefinition** 属性，其中包含关联的计划作业。 利用这种递归互连，可以轻松查找计划作业的触发器和选项，查找、编写脚本，并显示与任何作业触发器或作业选项关联的计划作业。

## <a name="see-also"></a>另请参阅

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

[PSScheduledJob](xref:PSScheduledJob) 模块 cmdlet

[任务计划程序](/windows/desktop/TaskSchd/task-scheduler-reference)
