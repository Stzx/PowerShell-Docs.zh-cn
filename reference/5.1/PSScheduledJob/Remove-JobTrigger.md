---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/remove-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-JobTrigger
ms.openlocfilehash: adcd74361b1a045a57c7db2f15996f4ea53d6d5b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197783"
---
# Remove-JobTrigger

## 摘要
从计划作业中删除作业触发器。

## SYNTAX

### JobDefinition（默认值）

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-InputObject] <ScheduledJobDefinition[]> [<CommonParameters>]
```

### JobDefinitionId

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Id] <Int32[]> [<CommonParameters>]
```

### JobDefinitionName

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION
**Get-jobtrigger** cmdlet 从计划作业中删除作业触发器。

作业触发器定义用于启动计划作业的循环计划或条件。
若要管理作业触发器，请使用 New-JobTrigger、Add-JobTrigger、Set-JobTrigger 和 Set-ScheduledJob cmdlet。

使用 *Remove-JobTrigger* 的 *Name* 、 *ID* 或 **InputObject** 参数来标识从中删除触发器的计划作业。
使用 *TriggerID* 参数来标识要删除的作业触发器。
默认情况下， **Remove-JobTrigger** 将删除计划作业的所有作业触发器。

**Remove-JobTrigger** 是 PSScheduledJob 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：删除所有作业触发器

```
PS C:\> Remove-JobTrigger -Name "Test*"
```

此命令从计划作业中删除名称以 "Test" 开头的所有作业触发器。

### 示例 2：删除选定的作业触发器

```
PS C:\> Remove-JobTrigger -Name "BackupArchive" -TriggerID 3
```

此命令仅从 BackupArchive 计划作业中删除第三个触发器 (ID = 3)。

### 示例 3：从所有计划作业中删除 AtStartup 作业触发器

```
PS C:\> function Delete-AtStartup
{
    Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.Frequency -eq "AtStartup"} | ForEach-Object { Remove-JobTrigger -InputObject $_.JobDefinition -TriggerID $_.ID}
}
```

此函数从本地计算机上的所有作业中删除所有 AtStartup 作业触发器。
若要使用函数，请在会话中运行函数，然后键入 `Delete-AtStartup` 。

Delete-AtStartup 函数包含单个命令。
此命令使用 Get-ScheduledJob cmdlet 获取本地计算机上的计划作业。
管道运算符 (|) 将计划作业发送到 Get-JobTrigger cmdlet，此 cmdlet 从每个计划作业中获取所有作业触发器。
管道运算符将作业触发器发送到 Where-Object cmdlet，该 cmdlet 选择作业触发器的 Frequency 属性值等于 AtStartup 的作业触发器。

**Get-jobtrigger** 对象具有 **JobDefinition** 属性，该属性包含其触发的计划作业。
该命令的剩余部分将使用这一有价值的功能。

管道运算符将 AtStartup 作业触发器发送到 ForEach-Object cmdlet，后者在每个 AtStartup 触发器上运行 **Remove-JobTrigger** 命令。
在作业触发器的 JobDefinition 属性中， **Remove-JobTrigger** 的 *InputObject* 参数值是计划作业。
在作业触发器的 ID 属性中， *TriggerID* 参数的值是标识符。

### 示例 4：从远程计划作业中删除作业触发器

```
PS C:\> Invoke-Command -ComputerName "Server01" { Remove-JobTrigger -ID 38 -TriggerID 1 }
```

此命令从 Server01 计算机上的 Inventory 作业中删除第一个作业触发器。

该命令使用 get-jobtrigger **cmdlet 在** Server01 计算机上运行 **Remove-JobTrigger** cmdlet。
**Get-jobtrigger** Cmdlet 使用 *ID* 参数来标识清单计划作业，并使用 *TriggerID* 参数来指定第一个触发器。
当多个计划作业具有相同或类似的名称时， *ID* 参数特别有用。

## PARAMETERS

### -Id
指定计划作业的标识号。
**Remove-JobTrigger** 可从指定的计划作业中删除作业触发器。

若要获取本地计算机或远程计算机上的计划作业的标识号，请使用 Get-ScheduledJob cmdlet。

```yaml
Type: System.Int32[]
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
还可以通过管道将 **ScheduledJob** 对象传递给 **Remove-JobTrigger** 。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
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
**Remove-JobTrigger** 可从指定的计划作业中删除作业触发器。
支持通配符。

若要获取本地计算机或远程计算机上的计划作业的名称，请使用 Get-ScheduledJob cmdlet。

```yaml
Type: System.String[]
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TriggerId
只删除指定的作业触发器。
默认情况下， **Remove-JobTrigger** 可从计划作业中删除所有触发器。
在计划作业有多个作业触发器时使用此参数。

输入计划作业中一个或多个作业触发器的触发器 ID。
如果指定多个计划作业，则 **get-jobtrigger** 将从所有计划作业中删除具有指定 ID 的作业触发器。

```yaml
Type: System.Int32[]
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

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
你可以通过管道将计划作业传递给 **Remove-JobTrigger** cmdlet。

## 输出

### 无
该 cmdlet 不生成任何输出。

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
