---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJobOption
ms.openlocfilehash: 6647e9ba4e2ee49afa90dd382573d437d2deaee6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197774"
---
# Set-ScheduledJobOption

## 摘要
更改计划作业的作业选项。

## SYNTAX

```
Set-ScheduledJobOption [-InputObject] <ScheduledJobOptions> [-PassThru] [-RunElevated] [-HideInTaskScheduler]
 [-RestartOnIdleResume] [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart]
 [-RequireNetwork] [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery]
 [-IdleTimeout <TimeSpan>] [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## DESCRIPTION
**Set-ScheduledJobOptions** cmdlet 可更改计划作业的作业选项。

若要更改计划作业的选项，请首先使用 Get-ScheduledJobOption cmdlet 来获取计划作业的作业选项。
然后，通过管道将这些选项传递给 **Set-ScheduledJobOption** 或将其保存在某个变量中，并且使用 *Set-ScheduledJobOption* cmdlet 的 **InputObject** 参数来标识这些选项。
使用 **Set-ScheduledJobOption** 的剩余参数来更改作业选项。

若要启用作业选项，请使用设置该选项的参数。
若要关闭某个选项，请键入参数名称、冒号 (： ) 和 $False。
例如，若要关闭 *RunElevated* 选项，请键入 `-RunElevated:$False` 。

每个作业选项对象都包括 JobDefinition 属性，该属性包含计划作业，以便在作业选项发生更改后保留计划作业的关联内容。

计划作业选项确定作业在由任务计划程序启动后的运行方式。
这些选项不适用于在使用 Start-Job cmdlet 启动计划作业时使用。

**Get-scheduledjoboption** 是 Windows PowerShell 中包含的 PSScheduledJob 模块中的作业计划 cmdlet 集合之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例1：更改作业选项

```
PS C:\> Get-ScheduledJobOption -Name "DeployPackage"
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
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          :

The second command uses the **Set-ScheduledJobOpton** cmdlet to change the job options so the values of the WakeToRun and RunWithoutNetwork properties are $True. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-ScheduledJobOption -Name "DeployPackage" | Set-ScheduledJobOption -WakeToRun -RequireNetwork:$False -Passthru
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
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
MultipleInstancePolicy : IgnoreNewJobDefinition          :
```

此示例显示了如何更改本地计算机上的计划作业选项。

第一个命令使用 Get-ScheduledJobOption cmdlet 来获取 DeployPackage 计划作业的作业选项。
输出显示 "WakeToRun" 和 "RunElevated" 属性设置为 $False。

此命令不是必需的；包含它只是为了显示选项更改的效果。

### 示例2：更改所有远程计划作业的选项

```
PS C:\> Invoke-Command -Computer "Server01" -ScriptBlock {Get-ScheduledJob | Get-ScheduledJobOption | Set-ScheduledJobOption -IdleTimeout 2:00:00}
```

此命令会将 *IdleTimeout* 的值从一个小时更改 (默认值) 为 Server01 计算机上所有计划作业的两个小时。

该命令使用 Invoke-Command cmdlet 在 Server01 计算机上运行命令。

远程命令以获取计算机上所有计划作业的 Get-ScheduledJob 命令开头。
计划作业将通过管道传递给 Get-ScheduledJobOption cmdlet，该 cmdlet 可获取计划作业的作业选项。
每个作业选项对象都包含 JobDefinition 属性，该属性包括计划作业，因此选项对象与计划作业保持关联，即使该作业出现更改也是如此。

将作业触发器传递给 **get-scheduledjoboption** cmdlet，该 cmdlet 会将 *IdleTimeout* 选项的值更改为两个小时 (2:00:00) 。

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

即使某个任务处于隐藏状态，用户也可以通过选择 "任务计划程序中的" **显示隐藏的任务** "视图选项来显示该任务。

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

输入一个 timespan 对象，例如 New-TimeSpan cmdlet 生成的一个 timespan 对象，或输入 \<hours\> ： \<minutes\> ： \<seconds\> 格式自动转换为 **timespan** 对象的值。

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
指定在启动作业之前计算机必须处于空闲状态的时长。
默认值为 10 分钟。
如果在 **IdleTimeout** 的值过期前，计算机在指定的持续时间内不处于空闲状态，则在下一个计划时间（如果有）之前计划作业不会启动。

输入一个 timespan 对象，例如 New-TimeSpan cmdlet 生成的一个 timespan 对象，或输入 \<hours\> ： \<minutes\> ： \<seconds\> 格式自动转换为 **timespan** 对象的值。

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

### -InputObject
指定作业选项。
输入包含 **ScheduledJobOptions** 对象的变量，或者键入获取 **ScheduledJobOptions** 对象的命令或表达式，如 Get-ScheduledJobOption 命令。
还可以通过管道将 **ScheduledJobOptions** 对象传递给 **get-scheduledjoboption** 。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MultipleInstancePolicy
确定系统如何在计划作业的某个实例正在运行时响应启动该作业的其他实例。
此参数的可接受值为：

- IgnoreNew.
忽略新的作业实例。
这是默认值。
- 并行。
立即启动新的作业实例。
- 队列。
在当前实例完成后立即启动新的作业实例。
- StopExisting.
停止当前的作业实例，并启动新的实例。

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

### -PassThru
返回一个代表你所处理的项目的对象。
默认情况下，此 cmdlet 将不产生任何输出。

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

**RunElevated** 参数将计划作业的 **RunElevated** 属性值设置为 True。

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
如果在 **IdleDuration** 参数指定的时间到期之前，计算机在 *IdleTimeout* 参数指定的时间内已处于空闲状态，将启动计划作业。

默认情况下，将忽略 *IdleDuration* 和 *IdleTimeout* 参数，并且作业将在计划开始时间启动，即使计算机处于繁忙状态也是如此。

如果指定了此参数，但计算机在计划开始时间处于繁忙状态（不空闲），则在下一个计划开始时间（如果有）之前该作业不会运行。

*StartIfIdle* 参数将计划作业的 **StartIfNotIdle** 属性值设置为 False。

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
默认值为 False。

*StartIfOnBattery* 参数将计划作业的 **StartIfOnBatteries** 属性值设置为 $True。

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

### Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
你可以通过管道将计划作业选项对象传递给 **Set-ScheduledJobOption** 。

## 输出

### None 或 Get-scheduledjob。 ScheduledJobOptions
当使用 *Passthru* 参数时， **Set-ScheduledJobOption** 将返回已更改的作业选项。
否则，此 cmdlet 将不生成任何输出。

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
