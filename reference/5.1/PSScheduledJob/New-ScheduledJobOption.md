---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledJobOption
ms.openlocfilehash: 35ada8d5aaa6a6c1fdc74a089308aefe13598b10
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197785"
---
# New-ScheduledJobOption

## 摘要
为计划作业创建包含高级选项的对象。

## SYNTAX

```
New-ScheduledJobOption [-RunElevated] [-HideInTaskScheduler] [-RestartOnIdleResume]
 [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart] [-RequireNetwork]
 [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery] [-IdleTimeout <TimeSpan>]
 [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## DESCRIPTION
**New-ScheduledJobOption** cmdlet 可为计划作业创建包含高级选项的对象。

你可以使用 **New-ScheduledJobOption** 返回的 **ScheduledJobOptions** 对象，为新的或现有的计划作业设置作业选项。
或者，你可以使用 Get-ScheduledJobOption cmdlet 来设置作业选项，以获取现有计划作业的作业选项，或使用哈希表值来表示作业选项。

如果没有参数，则 **get-scheduledjoboption** 将生成一个对象，该对象包含所有选项的默认值。
由于所有属性都是可编辑的（JobDefinition 属性除外），因此你可以将生成的对象用作模板，并为你的企业创建标准选项对象。

当创建计划作业并设置计划作业选项时，应检查所有计划作业选项的默认值。
仅在满足为其执行所设置的所有条件时才运行计划作业。

**Get-scheduledjoboption** 是 Windows PowerShell 中包含的 PSScheduledJob 模块中的作业计划 cmdlet 集合之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例1：创建具有默认值的计划作业选项对象

```
PS C:\> New-ScheduledJobOption
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
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

此命令创建具有所有默认值的计划作业选项对象。

### 示例2：使用自定义值创建计划作业选项对象

```
PS C:\> New-ScheduledJobOption -RequireNetwork -StartIfOnBattery
StartIfOnBatteries     : True
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

以下命令将创建一个计划作业对象，该对象需要网络并运行该计划作业，即使计算机未连接到交流电源也是如此。

输出显示 *RequireNetwork* 参数已将 RunWithoutNetwork 属性的值更改为 $False，而 *StartIfOnBattery* 参数将 StartIfOnBatteries 属性的值更改为 $True。

### 示例3：设置新计划作业的选项

```
The first command creates a **ScheduledJobOptions** object with the *RunElevated* parameter. It saves the object in the $RunAsAdmin variable.
PS C:\> $RunAsAdmin = New-ScheduledJobOption -RunElevated

The second command uses the Register-ScheduledJob cmdlet to create a new scheduled job. The value of the *ScheduledJobOption* parameter is the option object in the value of the $RunAsAdmin variable.
PS C:\> Register-ScheduledJob -Name Backup -FilePath D:\Scripts\Backup.ps1 -Trigger $Mondays -ScheduledJobOption $RunAsAdmin

The third command uses the Get-ScheduledJobOption cmdlet to get the job options of the Backup scheduled job.The cmdlet output shows that the RunElevated property is set to $True and the JobDefinition property of the job option object is now populated with the scheduled job object for the Backup scheduled job.
PS C:\> Get-ScheduledJobOption -Name Backup
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
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

此示例显示了如何使用 **New-ScheduledJobOption** 返回的 **ScheduledJobOptions** 对象为新的计划作业设置选项。

### 示例4：对计划作业选项对象的属性进行排序

```
PS C:\> $Options = New-ScheduledJobOption -WakeToRun
PS C:\> $Options.PSObject.Properties | Sort-Object -Property Name | Format-Table -Property Name, Value -Autosize
Name                       Value
----                       -----
DoNotAllowDemandStart      False
IdleDuration            00:10:00
IdleTimeout             01:00:00
JobDefinition
MultipleInstancePolicy IgnoreNew
RestartOnIdleResume        False
RunElevated                False
RunWithoutNetwork           True
ShowInTaskScheduler         True
StartIfNotIdle              True
StartIfOnBatteries         False
StopIfGoingOffIdle         False
StopIfGoingOnBatteries      True
WakeToRun                   True
```

此示例显示了如何按字母顺序对 **ScheduledJobOptions** 对象的属性进行排序以供轻松阅读。

第一个命令使用 **New-ScheduledJobOption** cmdlet 创建 **ScheduledJobOptions** 对象。
此命令使用 *WakeToRun* 参数并将生成的对象保存在 $Options 变量中。

若要以对象的形式获取 $Options 的属性，第二个命令使用所有 Windows PowerShell 对象的 **PSObject** 属性及其 properties 属性。
然后，该命令将属性对象通过管道传递给 Sort-Object cmdlet，该 cmdlet 将按名称的字母顺序对属性进行排序，然后指向 Format-Table cmdlet，后者将在表中显示属性的名称和值。

这种格式使你可以更轻松地在 $Options 中查找 **ScheduledJobOptions** 对象的 WakeToRun 属性，并验证其值是否已从 "$False" 更改为 "$True"。

## PARAMETERS

### -ContinueIfGoingOnBattery
如果计算机在正在运行计划作业时切换到电池电源（断开交流电源），请不要停止运行该作业。
默认情况下，计划作业在计算机断开交流电源时将停止运行。

*ContinueIfGoingOnBattery* 参数将计划作业的 StopIfGoingOnBatteries 属性值设置为 $True。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DoNotAllowDemandStart
仅在触发作业时它才启动。
用户无法手动启动作业，例如通过使用任务计划程序中的 Run 功能。

此参数仅影响任务计划程序。
它不会阻止用户使用 Start-Job cmdlet 来启动作业。

*DoNotAllowDemandStart* 参数将计划作业的 DoNotAllowDemandStart 属性值设置为 $True。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HideInTaskScheduler
不会在任务计划程序中显示作业。
此值仅影响运行该作业的计算机。
默认情况下，计划任务将显示在任务计划程序中。

即使某个任务处于隐藏状态，用户也可以通过选择 "任务计划程序中的" 显示隐藏的任务 "视图选项来显示该任务。

*HideInTaskScheduler* 参数将计划作业的 ShowInTaskScheduler 属性值设置为 $False。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleDuration
指定在启动作业之前计算机必须处于空闲状态的时长。
默认值为 10 分钟。
如果在 *IdleTimeout* 的值过期前，计算机在指定的持续时间内不处于空闲状态，则在下一个计划时间（如果有）之前计划作业不会启动。

输入一个 **TimeSpan** 对象，例如 New-TimeSpan cmdlet 生成的一个 timespan 对象，或输入 \<hours\> ： \<minutes\> ： \<seconds\> 格式自动转换为 **TimeSpan** 对象的值。

若要启用此值，请使用 *StartIfIdle* 参数。
默认情况下，计划作业的 StartIfNotIdle 属性设置为 $True，Windows PowerShell 将忽略 *IdleDuration* 和 *IdleTimeout* 值。

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleTimeout
指定计划作业等待计算机进入空闲状态的时长。
如果超过此超时而计算机仍未在 *IdleDuration* 参数指定的时间段保持空闲状态，则在下一个计划时间（如果有）之前该作业不会运行。
默认值为 1 小时。

输入一个 **TimeSpan** 对象，例如 New-TimeSpan cmdlet 生成的一个 timespan 对象，或输入 \<hours\> ： \<minutes\> ： \<seconds\> 格式自动转换为 **TimeSpan** 对象的值。

若要启用此值，请使用 *StartIfIdle* 参数。
默认情况下，计划作业的 StartIfNotIdle 属性设置为 $True，Windows PowerShell 将忽略 *IdleDuration* 和 *IdleTimeout* 值。

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MultipleInstancePolicy
确定系统如何在计划作业的某个实例正在运行时响应启动该作业的其他实例。
默认值为 IgnoreNew。
此参数的可接受值为：

- IgnoreNew.
忽略新的作业实例。
- 并行。
立即启动新的作业实例。
- 队列。
在当前实例完成后立即启动新的作业实例。
- StopExisting.
作业的当前实例将停止并启动新实例。

若要运行该作业，必须满足作业计划的所有条件。
例如，如果不满足 *RequireNetwork* 、 *IdleDuration* 和 *IdleTimeout* 参数设置的条件，则不会启动作业实例，无论此参数的值如何。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.TaskMultipleInstancePolicy
Parameter Sets: (All)
Aliases:
Accepted values: None, IgnoreNew, Parallel, Queue, StopExisting

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireNetwork
仅在网络连接可用时才运行计划作业。

如果指定了此参数，但网络在计划开始时间不可用，则在下一个计划开始时间（如果有）之前该作业不会运行。

*RequireNetwork* 参数将计划作业的 RunWithoutNetwork 属性值设置为 $False。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestartOnIdleResume
在计算机处于空闲状态后重新启动计划作业。
在计算机处于活动状态（退出空闲状态）后，将此参数与可挂起正在运行的计划作业的 *StopIfGoingOffIdle* 参数一起使用。

*RestartOnIdleResume* 参数将计划作业的 RestartOnIdleResume 属性值设置为 $True。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunElevated
使用运行计划作业的计算机上 Administrators 组成员权限来运行该作业。

若要使用管理员权限启用计划作业，请使用 Register-ScheduledJob 的 *Credential* 参数为作业提供显式凭据。

*RunElevated* 参数将计划作业的 RunElevated 属性值设置为 $True。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartIfIdle
如果在 *IdleDuration* 参数指定的时间到期之前，计算机在 *IdleTimeout* 参数指定的时间内已处于空闲状态，将启动计划作业。

默认情况下，将忽略 *IdleDuration* 和 *IdleTimeout* 参数，并且作业将在计划开始时间启动，即使计算机处于繁忙状态也是如此。

如果指定了此参数，但计算机在计划开始时间处于繁忙状态（不空闲），则在下一个计划开始时间（如果有）之前该作业不会运行。

*StartIfIdle* 参数将计划作业的 StartIfNotIdle 属性值设置为 $False。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartIfOnBattery
在计划开始时间启动计划作业，即使计算机使用电池电源运行也是如此。
默认值为 $False。

*StartIfOnBattery* 参数将计划作业的 StartIfOnBatteries 属性值设置为 $True。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StopIfGoingOffIdle
如果计算机在计划作业正在运行时处于活动状态（不空闲），则挂起运行的作业。

默认情况下，计划作业将在计算机处于活动状态时挂起，而在计算机再次处于空闲状态时恢复运行。
若要更改该默认行为，请使用 *RestartOnIdleResume* 参数。

*StopIfGoingOffIdle* 参数将计划作业的 StopIfGoingOffIdle 属性值设置为 $True。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WakeToRun
在计划开始时间，将计算机从休眠或睡眠状态唤醒，以便它可以运行该作业。
默认情况下，如果计算机在计划开始时间处于休眠或睡眠状态，则不会运行该作业。

*WakeToRun* 参数将计划作业的 WakeToRun 属性值设置为 $True。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无
不能通过管道将输入传递给此 cmdlet。

## 输出

### Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions

## 注释

* 你可以使用 **get-scheduledjoboption** 创建的 **ScheduledJobOptions** 对象作为 Register-ScheduledJob cmdlet 的 *get-scheduledjoboption* 参数的值。 但是， *get-scheduledjoboption* 参数也可以采用哈希表值来指定 **ScheduledJobOptions** 对象的属性及其值，例如：

  `@{ShowInTaskScheduler=$False; RunElevated=$True; IdleDuration="00:05"}`

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
