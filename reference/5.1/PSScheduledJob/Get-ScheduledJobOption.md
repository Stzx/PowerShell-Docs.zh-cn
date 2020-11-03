---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJobOption
ms.openlocfilehash: 5c317be9add0898137aceed6c39032f3e271bac1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197787"
---
# Get-ScheduledJobOption

## 摘要
获取计划作业的作业选项。

## SYNTAX

### JobDefinition（默认值）

```
Get-ScheduledJobOption [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### JobDefinitionId

```
Get-ScheduledJobOption [-Id] <Int32> [<CommonParameters>]
```

### JobDefinitionName

```
Get-ScheduledJobOption [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
**Get-scheduledjoboption** cmdlet 获取计划作业的作业选项。
你可以使用此命令检查作业选项或通过管道将其传递给其他 cmdlet。

不会单独将作业选项保存到磁盘，因为它们是计划作业的一部分。
若要获取某个计划作业的作业选项，请指定该计划作业。

使用 **Get-ScheduledJobOption** cmdlet 的参数来标识计划作业。
可以通过其名称或标识号来识别计划作业，或者通过将 **get-scheduledjob** 对象（如 Get-ScheduledJob cmdlet 返回的对象）输入或管道传递给 **get-scheduledjoboption** 。

**Get-ScheduledJobOption** 是 PSScheduledJob 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：获取作业选项

```
PS C:\> Get-ScheduledJobOption -Name "*Backup*"
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : False

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

此命令获取其名称中有备份的计划作业的作业选项。
结果将显示 **Get-ScheduledJobOption** 返回的作业选项对象。

### 示例 2：获取所有作业选项

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption
```

此命令获取本地计算机上的所有计划作业的作业选项。

此命令使用 Get-ScheduledJob cmdlet 获取本地计算机上的计划作业。
管道运算符 (|) 将计划作业发送到 **get-scheduledjoboption** cmdlet，此 cmdlet 可获取每个计划作业的作业选项。

### 示例 3：获取选定的作业选项

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun}
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : True

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The second command shows how to find to which scheduled job the job options belong. This command uses a pipeline operator (|) to send the selected job options to the ForEach-Object cmdlet, which gets the JobDefinition property of each options object. The JobDefinition property contains the originating job object. The results show that the selected options came from the DeployPkg scheduled job.
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun} | ForEach-Object {$_.JobDefinition}
Id         Name            Triggers        Command                                  Enabled

--         ----            --------        -------                                  -------

2          DeployPkg         {1, 2}        DeployPackage.ps1                        True
```

此示例显示了如何使用特定值查找作业选项对象。

第一个命令获取 RunElevated 属性值为 $True，RunWithoutNetwork 属性值为 $False 的作业选项。
输出显示选定的 **JobOptions** 对象。

### 示例 4：使用作业选项创建新作业

```
PS C:\> $Opts = Get-ScheduledJobOption -Name "BackupTestLogs"
PS C:\> Register-ScheduledJob -Name "Archive-Scripts" -FilePath "\\Srv01\Scripts\ArchiveScripts.ps1" -ScheduledJobOption $Opts
```

此示例演示如何使用 Get-ScheduledJobOption 在新的计划作业中获取的作业选项。

第一个命令使用 **get-scheduledjoboption** 获取 BackupTestLogs 计划作业的作业选项。
此命令将这些选项保存在 $Opts 变量中。

第二个命令使用 Register-ScheduledJob cmdlet 创建新的计划作业。
*ScheduledJobOption* 参数的值是 $Opts 变量中的选项对象。

### 示例 5：从远程计算机获取作业选项

```
PS C:\> $O = Invoke-Command -ComputerName "Srv01" -ScriptBlock {Get-ScheduledJob -Name "DataDemon" }
```

此命令使用 Invoke-Command cmdlet 获取 Srv01 计算机上的 DataDemon 作业的计划作业选项。
该命令将选项保存在 $O 变量中。

## PARAMETERS

### -Id
指定计划作业的标识号。
**Get-ScheduledJobOption** 可获取指定的计划作业的作业选项。

若要获取本地计算机或远程计算机上的计划作业的标识号，请使用 Get-ScheduledJob cmdlet。

```yaml
Type: System.Int32
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
指定计划作业。
请输入包含 **ScheduledJob** 对象的变量，或者键入获取 **ScheduledJob** 对象的命令或表达式，例如 Get-ScheduledJob 命令。
还可以通过管道将 **ScheduledJob** 对象传递给 **Get-ScheduledJobOption** 。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
指定计划作业的名称。
**Get-ScheduledJobOption** 可获取指定的计划作业的作业选项。
支持通配符。

若要获取本地计算机或远程计算机上的计划作业的名称，请使用 Get-ScheduledJob cmdlet。

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
可以通过管道将计划作业从 Get-ScheduledJob 传递到 **Get-ScheduledJobOption** 。

## 输出

### Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions

## 注释

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
