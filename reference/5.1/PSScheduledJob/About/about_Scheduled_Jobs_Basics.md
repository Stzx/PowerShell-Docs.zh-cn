---
description: 说明如何创建和管理计划作业。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_basics?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Basics
ms.openlocfilehash: d957c3267959c13b705e79fb220da4048e27a435
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199912"
---
# <a name="about-scheduled-jobs-basics"></a>关于计划作业基础知识

## <a name="short-description"></a>简短说明

说明如何创建和管理计划作业。

## <a name="long-description"></a>长说明

本文档介绍如何执行创建和管理计划作业的基本任务。 有关更高级任务的信息，请参阅 [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)。

有关 **PSScheduledJob** 模块中包含的 cmdlet 的详细信息，请参阅 [PSScheduledJob](xref:PSScheduledJob)。

## <a name="how-to-create-a-scheduled-job"></a>如何创建计划作业

若要创建计划作业，请使用 `Register-ScheduledJob` cmdlet。 该 cmdlet 需要一个名称以及该作业运行的命令或脚本。 您可以通过添加 **RunNow** 参数来立即运行作业，也可以在创建作业时创建作业触发器并设置作业选项，或者编辑现有作业。

若要创建运行脚本的作业，请使用 **FilePath** 参数指定脚本文件的路径。 若要创建运行命令的作业，请使用 **ScriptBlock** 参数。

`Register-ScheduledJob`Cmdlet 将创建用于运行命令的 **ProcessJob** `Get-Process` 。 此计划作业有默认作业选项，没有作业触发器。

```powershell
Register-ScheduledJob -Name ProcessJob -ScriptBlock { Get-Process }
```

```Output
Id         Name            Triggers        Command       Enabled
--         ----            --------        -------       -------
8          ProcessJob      {}              Get-Process   True
```

## <a name="how-to-create-a-job-trigger"></a>如何创建作业触发器

作业触发器会自动启动计划作业。 作业触发器可以是一次性或定期计划或事件，例如当用户登录或 Windows 启动时。 每个作业可以有零个、一个或多个作业触发器。

若要创建作业触发器，请使用 `New-JobTrigger` cmdlet。 下面的命令创建一个作业触发器，该触发器在每星期一和星期四的上午5:00 启动作业。
该命令将作业触发器保存在 `$T` 变量中。

```powershell
$T = New-JobTrigger -Weekly -DaysOfWeek "Monday", "Thursday" -At "5:00 AM"
```

作业触发器是可选的。 你可以随时通过将 **RunNow** 参数添加到 `Register-ScheduledJob` 命令或使用 cmdlet 来启动计划的作业 `Start-Job` 。

## <a name="how-to-add-a-job-trigger"></a>如何添加作业触发器

将作业触发器添加到计划作业时，会将作业触发器添加到计划作业的计划作业 XML 文件中，并成为计划作业的一部分。

你可以在创建计划作业时向计划作业添加作业触发器，或者编辑现有作业。 你可以随时更改计划作业的作业触发器。

PowerShell 使用任务计划程序使用的一些相同的作业触发器。 有关作业触发器的详细信息，请参阅 [get-jobtrigger](xref:PSScheduledJob.New-JobTrigger) cmdlet 的帮助主题。

下面的示例使用展开来创建 `$JobParms` 传递到 cmdlet 的参数值 `Register-ScheduledJob` 。 有关详细信息，请参阅[about_Splatting。](../../Microsoft.PowerShell.Core/About/about_Splatting.md)
用于 `Register-ScheduledJob` `@JobParms` 创建计划作业的。 它使用 **Trigger** 参数在变量中指定作业触发器 `$T` 。

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Command}
  Trigger = $T
}

Register-ScheduledJob @JobParms
```

你还可以随时将作业触发器添加到现有的计划作业。 `Add-JobTrigger`Cmdlet 会将变量中的作业触发器添加 `$T` 到 **ProcessJob** 计划作业。

```powershell
Add-JobTrigger -Name ProcessJob -Trigger $T
```

因此，作业触发器将在每星期一和星期四的上午5:00 自动启动 **ProcessJob** 。

## <a name="how-to-get-a-job-trigger"></a>如何获取作业触发器

若要获取计划作业的作业触发器，请使用 `Get-JobTrigger` cmdlet。 使用 " **名称** "、" **ID** " 和 " **InputObject** " 参数指定计划的作业，而不指定作业触发器。

`Get-JobTrigger` 获取 **ProcessJob** 的作业触发器。

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id   Frequency       Time                   DaysOfWeek              Enabled
--   ---------       ----                   ----------              -------
1    Weekly          11/7/2011 5:00:00 AM   {Monday, Thursday}      True
```

## <a name="how-to-create-job-options"></a>如何创建作业选项

作业选项用于建立启动和运行作业的条件。 每个作业都有默认作业选项，除非您更改它们。 由于作业选项可以阻止作业在计划的时间运行，因此了解作业选项并仔细使用这些选项非常重要。

PowerShell 使用任务计划程序使用的相同作业选项。 有关作业选项的详细信息，请参阅 [get-scheduledjoboption](xref:PSScheduledJob.New-ScheduledJobOption)的帮助主题。

作业选项存储在计划的作业 XML 文件中。 你可以在创建计划作业时设置作业选项，或者随时对其进行更改。

`New-ScheduledJobOption`Cmdlet 将创建一个计划作业选项，其中 **WakeToRun** 计划作业选项设置为 True。 即使在计划的开始时间计算机处于睡眠或休眠状态， **WakeToRun** 选项也会运行该计划作业。 该命令将作业选项保存在 `$O` 变量中。

```powershell
$O = New-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-job-options"></a>如何获取作业选项

若要获取计划作业的作业选项，请使用 `Get-ScheduledJobOption` cmdlet。 使用 " **名称** "、" **ID** " 和 " **InputObject** " 参数指定计划的作业，而不是作业选项。

`Get-ScheduledJobOption` 获取 **ProcessJob** 的作业选项。

```powershell
Get-ScheduledJobOption -Name ProcessJob
```

```Output
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
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

## <a name="how-to-change-job-options"></a>如何更改作业选项

你可以在创建计划作业时更改计划作业的作业选项，或者编辑现有作业。

Splatted `$JobParms` 传递给 `Add-JobTrigger` cmdlet 来创建进程作业。 它使用 **get-scheduledjoboption** 参数来指定变量中的作业选项 `$O` 。

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  ScheduledJobOption = $O
}

Add-JobTrigger @JobParms
```

你还可以随时将作业选项更改为现有的计划作业。
以下命令使用 cmdlet 将 `Set-ScheduledJobOption` **ProcessJob** get-scheduledjob 的 **WakeToRun** 选项的值更改为 **True** 。

`Set` **PSScheduledJob** 模块中的 cmdlet （如 `Set-ScheduledJobOption` cmdlet）没有 **Name** 或 **ID** 参数。 可以使用 **InputObject** 参数指定计划作业选项，或通过管道将计划作业从 cmdlet 传递 `Get-ScheduledJobOption` 给 `Set-ScheduledJobOption` 。

此示例使用 `Get-ScheduledJob` cmdlet 获取 ProcessJob。 它使用 `Get-ScheduledJobOption` cmdlet 获取 **ProcessJob** 中的作业选项，并使用 cmdlet 将 `Set-ScheduledJobOption` ProcessJob 中的 **WakeToRun** 作业选项更改为 True。

```powershell
Get-ScheduledJob -Name ProcessJob | Get-ScheduledJobOption |
 Set-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-scheduled-job-instances"></a>如何获取计划的作业实例

启动计划的作业时，PowerShell 会创建类似于标准 PowerShell 后台作业的作业实例。 可以使用作业 cmdlet （如 `Get-Job` ） `Stop-Job` 和 `Receive-Job` 管理作业实例。

> [!NOTE]
> 若要在计划作业的实例上使用作业 cmdlet，则必须将 **PSScheduledJob** 模块导入到会话中。 若要导入 **PSScheduledJob** 模块，请键入 `Import-Module PSScheduledJob` 或使用任何计划的作业 cmdlet，例如 `Get-ScheduledJob` 。

若要获取 PowerShell 计划作业的所有实例和所有活动的标准作业，请使用 `Get-Job` cmdlet。 `Import-Module`Cmdlet 将导入 **PSScheduledJob** 模块，并 `Get-Job` 获取本地计算机上的作业。

```powershell
Import-Module PSScheduledJob
Get-Job
```

`Get-Job` 获取本地计算机上的 **ProcessJob** 的实例。

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

默认显示不显示开始时间，这通常会区分同一计划作业的实例。

`Get-Job`Cmdlet 沿管道向下发送对象。 `Format-Table`Cmdlet 显示计划作业的 **名称** 、 **ID** 和 **system.windows.media.animation.timeline.begintime** 属性。

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, BeginTime
```

```Output
Name       Id BeginTime
----       -- ---------
ProcessJob 43 11/2/2011 3:00:02 AM
ProcessJob 44 11/3/2011 3:00:02 AM
ProcessJob 45 11/4/2011 3:00:02 AM
ProcessJob 46 11/5/2011 3:00:02 AM
ProcessJob 47 11/6/2011 3:00:02 AM
ProcessJob 48 11/7/2011 12:00:01 AM
ProcessJob 49 11/7/2011 3:00:02 AM
ProcessJob 50 11/8/2011 3:00:02 AM
```

## <a name="get-scheduled-job-results"></a>获取计划作业结果

若要获取某个计划作业的实例的结果，请使用 `Receive-Job` cmdlet。

> [!NOTE]
> 若要在计划作业的实例上使用作业 cmdlet，则必须将 **PSScheduledJob** 模块导入到会话中。 若要导入 **PSScheduledJob** 模块，请键入 `Import-Module PSScheduledJob` 或使用任何计划的作业 cmdlet，例如 `Get-ScheduledJob` 。

此示例将获取 **ProcessJob** 计划作业的最新实例的结果 (ID = 51) 。

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 51 -Keep
```

计划作业的结果保存在磁盘上，因此不需要 **Keep** 参数 `Receive-Job` 。 但是，如果不使用 **Keep** 参数，只需在每个 PowerShell 会话中获得一次计划作业的结果。 若要启动新的 PowerShell 会话，请键入 `PowerShell` 或打开一个新的 powershell 窗口。

## <a name="see-also"></a>另请参阅

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

[about_Splatting md](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

[PSScheduledJob](xref:PSScheduledJob) 模块 cmdlet

[任务计划程序](/windows/desktop/TaskSchd/task-scheduler-reference)
