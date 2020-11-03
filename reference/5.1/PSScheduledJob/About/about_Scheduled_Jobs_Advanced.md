---
description: 说明高级计划作业主题，包括构成计划作业的基础的文件结构。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_advanced?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Advanced
ms.openlocfilehash: 7b09a72e8ad7e68641c73d2f7e59065dbf8f889b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199914"
---
# <a name="about-scheduled-jobs-advanced"></a>关于计划作业高级

## <a name="short-description"></a>简短说明

说明高级计划作业主题，包括构成计划作业的基础的文件结构。

## <a name="long-description"></a>长说明

有关 **PSScheduledJob** 模块中包含的 cmdlet 的详细信息，请参阅 [PSScheduledJob](xref:PSScheduledJob)。

## <a name="scheduled-job-directories-and-files"></a>计划的作业目录和文件

PowerShell 计划作业既是 PowerShell 作业，又是任务计划程序任务。
每个计划作业都在任务计划程序中注册，并保存在磁盘上，Microsoft .NET 框架序列化 XML 格式。

在创建计划作业时，PowerShell 会在本地计算机上的目录中为计划作业创建一个目录 `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` 。 目录名称与作业名称相同。

下面是一个示例 **ScheduledJobs** 目录。

```powershell
Get-ChildItem $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs
```

```Output
Directory: C:\Users\User01\AppData\Local
               \Microsoft\Windows\PowerShell\ScheduledJobs

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         9/29/2011  10:03 AM            ArchiveProjects
d----         9/30/2011   1:18 PM            Inventory
d----        10/20/2011   9:15 AM            Backup-Scripts
d----         11/7/2011  10:40 AM            ProcessJob
d----         11/2/2011  10:25 AM            SecureJob
d----         9/27/2011   1:29 PM            Test-HelpFiles
d----         9/26/2011   4:22 PM            DeployPackage
```

每个计划作业都有其自己的目录。 目录包含计划的作业 XML 文件和 **输出** 子目录。

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell"
$Path += "\ScheduledJobs\ProcessJob"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/1/2011   3:00 PM            Output
-a---         11/1/2011   3:43 PM       7281 ScheduledJobDefinition.xml
```

计划作业的 **输出** 目录包含其执行历史记录。
每次作业触发器启动计划作业时，PowerShell 都会在输出目录中创建一个时间戳名称的目录。 Timestamp 目录包含 **Results.xml** 文件中的作业结果和 **Status.xml** 文件中的作业状态。

以下命令显示 **ProcessJob** 计划作业的执行历史记录目录。

```powershell
$Path = "$home\AppData\Local\Microsoft"
$Path += "\Windows\PowerShell\ScheduledJobs\ProcessJob\Output"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft
               \Windows\PowerShell\ScheduledJobs\ProcessJob\Output

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/2/2011   3:00 AM            20111102-030002-260
d----         11/3/2011   3:00 AM            20111103-030002-277
d----         11/4/2011   3:00 AM            20111104-030002-209
d----         11/5/2011   3:00 AM            20111105-030002-251
d----         11/6/2011   3:00 AM            20111106-030002-174
d----         11/7/2011  12:00 AM            20111107-000001-914
d----         11/7/2011   3:00 AM            20111107-030002-376
```

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell\"
$Path += "ScheduledJobs\ProcessJob\Output\20111102-030002-260"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output\20111102-030002-260

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         11/2/2011   3:00 AM     581106 Results.xml
-a---         11/2/2011   3:00 AM       9451 Status.xml
```

您可以打开并检查 **ScheduledJobDefinition.xml** 、 **Results.xml** 和 **Status.xml** 文件，或使用 `Select-XML` cmdlet 分析文件。

> [!WARNING]
> 不要编辑 XML 文件。 如果任何 XML 文件包含无效的 XML，则 PowerShell 会删除计划的作业及其执行历史记录（包括作业结果）。

## <a name="start-a-scheduled-job-immediately"></a>立即启动计划作业

可以通过以下两种方式之一立即启动计划作业：

- 运行 `Start-Job` cmdlet 以启动任何计划作业。
- 将 **RunNow** 参数添加到 `Register-ScheduledJob` 命令，以便在命令运行后立即启动作业。

使用 cmdlet 启动的作业 `Start-Job` 是标准 PowerShell 后台作业，而不是计划作业的实例。 与所有后台作业一样，这些作业会立即启动，它们不受作业选项的影响，也不受作业触发器的影响。 作业输出不会保存在计划作业目录的 **输出** 目录中。

以下命令使用 cmdlet 的 **DefinitionName** 参数 `Start-Job` 来启动 ProcessJob 计划作业。

```powershell
Start-Job -DefinitionName ProcessJob
```

若要管理作业并获取作业结果，请使用作业 cmdlet。 有关作业 cmdlet 的详细信息，请参阅 [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md)。

> [!NOTE]
> 若要在计划作业的实例上使用作业 cmdlet，则必须将 **PSScheduledJob** 模块导入到会话中。 若要导入 **PSScheduledJob** 模块，请键入 `Import-Module PSScheduledJob` 或使用任何计划的作业 cmdlet，例如 `Get-ScheduledJob` 。

## <a name="rename-a-scheduled-job"></a>重命名计划作业

若要重命名计划作业，请使用该 cmdlet 的 Name 参数 `Set-ScheduledJob` 。 重命名计划作业时，PowerShell 会更改计划作业的名称和计划作业目录。 但是，它不会更改已运行的计划作业的实例的名称。

## <a name="get-start-and-end-times"></a>获取开始时间和结束时间

若要获取作业实例开始和结束的日期和时间，请使用 **PSBeginTime** 为计划作业返回的 get-scheduledjob 对象的 PSBeginTime 和 **PSEndTime** 属性 `Get-Job` 。

下面的示例使用 cmdlet 的 **Property** 参数 `Format-Table` 来显示表中每个作业实例的 **PSBeginTime** 和 **PSEndTime** 属性。 名为 **Label** 的计算属性显示每个作业实例的运行时间。

```powershell
Get-job -Name UpdateHelpJob | 
  Format-Table -Property ID, PSBeginTime, PSEndTime,
@{Label="Elapsed Time";Expression={$.PsEndTime - $.PSBeginTime}}
```

```Output
Id   PSBeginTime             PSEndTime                Elapsed Time
--   -----------             ---------                ------------
 2   11/3/2011 3:00:01 AM    11/3/2011 3:00:39 AM     00:00:38.0053854
 3   11/4/2011 3:00:02 AM    11/4/2011 3:01:01 AM     00:00:59.1188475
 4   11/5/2011 3:00:02 AM    11/5/2011 3:00:50 AM     00:00:48.3692034
 5   11/6/2011 3:00:01 AM    11/6/2011 3:00:54 AM     00:00:52.8013036
 6   11/7/2011 3:00:01 AM    11/7/2011 3:00:38 AM     00:00:37.1930350
 7   11/8/2011 3:00:01 AM    11/8/2011 3:00:57 AM     00:00:56.2570556
 8   11/9/2011 3:00:03 AM    11/9/2011 3:00:55 AM     00:00:51.8142222
 9   11/10/2011 3:00:02 AM   11/10/2011 3:00:42 AM    00:00:40.7195954
```

## <a name="manage-execution-history"></a>管理执行历史记录

您可以确定为每个计划作业保存的作业实例结果数，并删除任何计划作业的执行历史记录和保存的作业结果。

计划作业的 **ExecutionHistoryLength** 属性决定为计划作业保存的作业实例结果数。 当保存的结果数超过 **ExecutionHistoryLength** 属性的值时，PowerShell 会删除最旧实例的结果，以便为最新实例的结果腾出空间。

默认情况下，PowerShell 会保存每个计划作业的执行历史记录和32实例的结果。 若要更改该值，请使用 **MaxResultCount** 或 Cmdlet 的 MaxResultCount `Register-ScheduledJob` 参数 `Set-ScheduledJob` 。

若要删除计划作业的执行历史记录和所有结果，请使用 cmdlet 的 **ClearExecutionHistory** 参数 `Set-ScheduledJob` 。 删除此执行历史记录不会阻止 PowerShell 保存计划作业的新实例的结果。

下面的示例使用展开来创建 `$JobParms` 传递到 cmdlet 的参数值 `Register-ScheduledJob` 。 有关详细信息，请参阅[about_Splatting。](../../Microsoft.PowerShell.Core/About/about_Splatting.md)
用于 `Register-ScheduledJob` `@JobParms` 创建计划作业的。 该命令使用值为12的 **MaxResultCount** 参数来仅保存计划作业的12个最新的作业实例结果。

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  MaxResultCount = "12"
}

Register-ScheduledJob @JobParms
```

以下命令使用 cmdlet 的 **MaxResultCount** 参数将 `Set-ScheduledJob` 保存的实例结果的数目增加到
15.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 15
```

以下命令删除 **ProcessJob** 计划作业的执行历史记录和当前保存的结果。

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

以下命令将获取计算机上所有计划作业的 name 和 **ExecutionHistoryLength** 属性的值，并将它们显示在一个表中。

```powershell
Get-ScheduledJob | 
  Format-Table -Property Name, ExecutionHistoryLength -AutoSize
```

## <a name="see-also"></a>另请参阅

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

[about_Splatting md](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

[PSScheduledJob](xref:PSScheduledJob) 模块 cmdlet

[任务计划程序](/windows/desktop/TaskSchd/task-scheduler-reference)
