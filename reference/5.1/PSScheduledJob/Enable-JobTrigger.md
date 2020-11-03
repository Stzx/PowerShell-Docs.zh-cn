---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-JobTrigger
ms.openlocfilehash: d08b55f4ba78af69608ac74c097fc6851164093b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197791"
---
# Enable-JobTrigger

## 摘要
启用计划作业的作业触发器。

## SYNTAX

```
Enable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Enable-JobTrigger** cmdlet 重新启用作业计划的作业触发器，例如通过 Disable-JobTrigger cmdlet 禁用的作业触发器。
启用和重新启用的作业触发器均可立即启动计划作业；无需重新启动 Windows 或 Windows PowerShell。

若要使用此 cmdlet，请使用 Get-JobTrigger cmdlet 获取作业触发器。
然后，通过管道将这些作业触发器传递给 **Enable-JobTrigger** ，或使用其 *InputObject* 参数。

若要启用作业触发器， **Enable-JobTrigger** cmdlet 应将该作业触发器的 Enabled 属性设置为 $True。

**Enable-ScheduledJob** 是 **PSScheduledJob** 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：启用作业触发器

```
PS C:\> Get-JobTrigger -Name Backup-Archives -TriggerID 1 | Enable-JobTrigger
```

启用本地计算机上 Backup-Archives 计划作业的第一个触发器（ID 为 1）。

此命令使用 Get-JobTrigger cmdlet 获取作业触发器。
管道运算符将该作业触发器发送到 **Enable-JobTrigger** cmdlet，此 cmdlet 将对其进行启用。

### 示例 2：启用所有作业触发器

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Enable-JobTrigger
```

此命令使用 Get-ScheduledJob cmdlet 获取本地计算机上的计划作业。
管道运算符 (|) 将计划作业发送到 Get-JobTrigger cmdlet，此 cmdlet 从计划作业中获取所有作业触发器。
另一个管道运算符将这些作业触发器发送到 **Enable-JobTrigger** cmdlet，此 cmdlet 将对其进行启用。

### 示例 3：启用远程计算机上计划作业的作业触发器

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "AtLogon"} | Enable-JobTrigger}
```

此命令在 Server01 远程计算机上重新启用 DeployPackage 计划作业中的 AtLogon 作业触发器。

该命令使用 Invoke-Command cmdlet 在 Server01 计算机上运行命令。
远程命令使用 Get-JobTrigger cmdlet 获取 DeployPackage 计划作业的作业触发器。
管道运算符将作业触发器发送到 Where-Object cmdlet，此 cmdlet 仅返回 AtLogon 作业触发器。
另一个管道运算符将 AtLogon 作业触发器发送到 **Enable-JobTrigger** cmdlet，此 cmdlet 将对其进行启用。

### 示例 4：显示禁用的作业触发器

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | where {!$_.Enabled} | Format-Table Id, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}}
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
 1    Weekly 9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
 2    Daily  9/29/2011 1:00:00 AM              False   Backup-Archive
 1    Weekly 10/20/2011 11:00:00 PM {Friday}   False   Inventory
 1    Weekly 11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

此命令将所有计划作业的所有禁用的作业触发器都显示在某个表中。
你可以使用类似此命令的命令来发现可能需要启用的作业触发器。

此命令使用 Get-ScheduledJob cmdlet 获取本地计算机上的计划作业。
管道运算符 (|) 将计划作业发送到 Get-JobTrigger cmdlet，此 cmdlet 从计划作业中获取所有作业触发器。
另一个管道运算符将作业触发器发送到 Where-Object cmdlet，此 cmdlet 仅返回已禁用的作业触发器，即其中作业触发器的 Enabled 属性值不为 (!) true。

另一个管道运算符将禁用的作业触发器发送到 Format-Table cmdlet，后者在表中显示作业触发器的选定属性。
这些属性包含新的 JobName 属性，该属性可在作业触发器的 JobDefinition 属性中显示计划作业的名称。

## PARAMETERS

### -InputObject
指定要启用的作业触发器。
输入包含 **ScheduledJobTrigger** 对象的变量，或者键入获取 **ScheduledJobTrigger** 对象的命令或表达式，如 Get-JobTrigger 命令。
还可以通过管道将 **ScheduledJobTrigger** 对象传递给 **Enable-JobTrigger** 。

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
可以通过管道将作业触发器传递给 **Enable-JobTrigger** 。

## 输出

### 无
此 cmdlet 将不生成任何输出。

## 注释

* 如果启用某个已启用的作业触发器， **Enable-JobTrigger** 不会生成错误或警告。

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
