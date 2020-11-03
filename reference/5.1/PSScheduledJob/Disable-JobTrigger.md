---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-JobTrigger
ms.openlocfilehash: 236e6b7e6e450bd1f3f868f889a19cf796890127
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197803"
---
# Disable-JobTrigger

## 摘要
禁用计划作业的作业触发器。

## SYNTAX

```
Disable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Disable-JobTrigger** cmdlet 可临时禁用计划作业的作业触发器。
该禁用操作会保留所有作业触发器属性，但它会阻止作业触发器启动计划作业。

若要使用此 cmdlet，请使用 Get-JobTrigger cmdlet 来获取作业触发器。
然后，通过管道将这些作业触发器传递给 **Disable-JobTrigger** ，或使用其 *InputObject* 参数。

若要禁用作业触发器， **get-jobtrigger** cmdlet 会将该作业触发器的 Enabled 属性设置为 $False。
若要重新启用作业触发器，请使用 Enable-JobTrigger cmdlet，该 cmdlet 可将作业触发器的 **Enabled** 属性设置为 $True。
禁用某个作业触发器不会禁用计划作业（例如可通过 Disable-ScheduledJob 来实现），但如果禁用所有作业触发器，结果与禁用计划作业相同。

如果禁用了计划作业或者禁用了计划作业的所有作业触发器，你仍然可以使用 Start-Job cmdlet 来启动该作业，或将禁用的计划作业用作模板。

**Disable-ScheduledJob** 是 **PSScheduledJob** 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：禁用作业触发器

```
PS C:\> Get-JobTrigger -Name "Backup-Archives" -TriggerID 1 | Disable-JobTrigger
```

此命令禁用本地计算机上 Backup-Archives 计划作业的第一个触发器（ID 为 1）。

此命令使用 Get-JobTrigger cmdlet 获取作业触发器。
管道运算符将该作业触发器发送到 **Disable-JobTrigger** cmdlet，此 cmdlet 将对其进行禁用。

### 示例 2：禁用所有作业触发器

```
The first command uses the Get-ScheduledJob cmdlet to get the Backup-Archives and Inventory scheduled jobs. A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs. Another pipeline operator sends the job triggers to the **Disable-JobTrigger** cmdlet, which disables them.The first command uses the **Get-ScheduledJob** cmdlet to get the jobs, because its *Name* parameter takes multiple names.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Disable-JobTrigger

The second command displays the results. The command repeats the **Get-ScheduledJob** and **Get-JobTrigger** command. A pipeline operator sends the job triggers to the Format-Table cmdlet, which displays the job triggers in a table. The **Format-Table** command adds a JobName property that displays the value of the Name property of the scheduled job in the JobDefinition property of the job trigger object.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
1  Weekly    9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
2  Daily     9/29/2011 1:00:00 AM              False   Backup-Archive
1  Weekly    10/20/2011 11:00:00 PM {Friday}   False   Inventory
1  Weekly    11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

以下命令禁用两个计划作业上的所有作业触发器并显示结果。

### 示例3：禁用远程计算机上计划作业的作业触发器

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "Daily"} | Disable-JobTrigger}
```

此命令在 Server01 远程计算机上禁用 DeployPackage 计划作业中每日作业触发器。

该命令使用 Invoke-Command cmdlet 在 Server01 计算机上运行命令。
远程命令使用 Get-JobTrigger cmdlet 获取 DeployPackage 计划作业的作业触发器。
管道运算符将作业触发器发送到 Where-Object cmdlet，该 cmdlet 仅返回每日作业触发器。
管道运算符将每日作业触发器发送到 **get-jobtrigger** cmdlet，这会将其禁用。

## PARAMETERS

### -InputObject
指定要禁用的作业触发器。
输入包含 **ScheduledJobTrigger** 对象的变量，或者键入可获取 **ScheduledJobTrigger** 对象的命令或表达式，例如 Get-JobTrigger 命令。
还可以通过管道将 **ScheduledJobTrigger** 对象传递给 **Disable-JobTrigger** 。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -Confirm
提示你在运行 cmdlet 之前进行确认。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
显示运行该 cmdlet 时会发生什么情况。
此 cmdlet 未运行。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger
你可以通过管道将作业触发器传递给 **Disable-JobTrigger** 。

## 输出

### 无
此 cmdlet 将不生成任何输出。

## 注释

* **Disable-JobTrigger** 不会在你禁用某个已禁用的作业触发器时生成错误或警告。

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
