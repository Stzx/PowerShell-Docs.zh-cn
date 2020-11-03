---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJob
ms.openlocfilehash: 40224432c208ee45efc20f556312fa250e9bb7a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197789"
---
# Get-ScheduledJob

## 摘要
获取本地计算机上的计划作业。

## SYNTAX

### DefinitionId（默认值）

```
Get-ScheduledJob [[-Id] <Int32[]>] [<CommonParameters>]
```

### DefinitionName

```
Get-ScheduledJob [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION
**Get-ScheduledJob** cmdlet 可获取本地计算机上的计划作业。
**Get-ScheduledJob** 仅获取当前用户使用 Register-ScheduledJob cmdlet 创建的计划作业。

尽管使用 **Register-ScheduledJob** cmdlet 所创建的作业会显示在任务计划程序中，但 **Get-ScheduledJob** 仅获取计划作业。
它不会获取在任务计划程序中创建的计划任务。

在没有参数的情况下， **Get-ScheduledJob** 将获取计算机上的所有计划作业。
你可以使用 **Get-ScheduledJob** 的参数，按 ID 或名称获取计划作业并对其进行检查，或者通过管道将它们传递给其他 cmdlet。

**Get-ScheduledJob** 是 **PSScheduledJob** 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：获取所有计划作业

```
PS C:\> Get-ScheduledJob
```

此命令获取本地计算机上的所有计划作业。

### 示例 2：按名称获取计划作业

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive*
```

此命令获取计算机上的其名称包含“Backup”或“Archive”的所有计划作业。
你可通过此命令格式搜索特定作业。

### 示例 3：获取远程计算机上的计划作业

```
PS C:\> Invoke-Command -ComputerName (Get-Content Servers.txt) {Get-ScheduledJob}
```

在 Servers.txt 文件中，此命令获取计算机上的所有计划作业。
该命令使用 Invoke-Command cmdlet 在每台计算机上运行 **Get-ScheduleJob** 命令。

### 示例 4：通过管道将计划作业传递给其他 cmdlet

```
PS C:\> Get-ScheduledJob DailyBackup, WeeklyBackup | Get-JobTrigger
```

此命令获取 DailyBackup 和 WeeklyBackup 计划作业的作业触发器。
它使用 **Get-ScheduledJob** cmdlet 获取计划作业，并使用 Get-JobTrigger cmdlet 获取计划作业的作业触发器。

## PARAMETERS

### -Id
仅获取具有指定标识号 (ID) 的计划作业。
在计算机上输入一个或多个计划作业的 ID。
默认情况下， **Get-ScheduledJob** 将获取计算机上的所有计划作业。

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
仅获取具有指定名称的计划作业。
在计算机上输入一个或多个计划作业的名称。
支持通配符。
默认情况下， **Get-ScheduledJob** 将获取计算机上的所有计划作业。

```yaml
Type: System.String[]
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无
不能通过管道将输入传递给 **Get-ScheduledJob** 。

## 输出

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

## 注释

* 每个计划作业都保存在本地计算机上的 $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs 目录的子目录中。 该子目录是按计划作业命名的，并且包含计划作业的 XML 文件以及该计划作业的执行历史记录。 有关磁盘上计划作业的详细信息，请参阅 about_Scheduled_Jobs_Advanced。
* 在 Windows PowerShell 中创建的计划作业会显示在 Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs 文件夹中的任务计划程序中。 你可以使用任务计划程序查看和编辑计划作业。
* 你可以使用任务计划程序、SchTasks.exe 命令行工具和 Task Scheduler cmdlet 来管理使用 Scheduled Job cmdlet 创建的计划作业。 但是，你无法使用 Scheduled Job cmdlet 来管理在任务计划程序中创建的任务。

## 相关链接

[Add-JobTrigger](Add-JobTrigger.md)

[Disable-JobTrigger](Disable-JobTrigger.md)

[Disable-ScheduledJob](Disable-ScheduledJob.md)

[Enable-JobTrigger](Enable-JobTrigger.md)

[Enable-ScheduledJob](Enable-ScheduledJob.md)

[Get-JobTrigger](Get-JobTrigger.md)

[Get-ScheduledJob](Get-ScheduledJob.md)

[Get-ScheduledJobOption](Get-ScheduledJobOption.md)

[New-JobTrigger](New-JobTrigger.md)

[New-ScheduledJobOption](New-ScheduledJobOption.md)

[Register-ScheduledJob](Register-ScheduledJob.md)

[Remove-JobTrigger](Remove-JobTrigger.md)

[Set-JobTrigger](Set-JobTrigger.md)

[Set-ScheduledJob](Set-ScheduledJob.md)

[Set-ScheduledJobOption](Set-ScheduledJobOption.md)

[Unregister-ScheduledJob](Unregister-ScheduledJob.md)
