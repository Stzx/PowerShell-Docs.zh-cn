---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/unregister-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-ScheduledJob
ms.openlocfilehash: 0c0b55513bcfdcebdcd5d8a6f17968a4a45e2839
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197773"
---
# Unregister-ScheduledJob

## 摘要
删除本地计算机上的计划作业。

## SYNTAX

### Definition（默认值）

```
Unregister-ScheduledJob [-InputObject] <ScheduledJobDefinition[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefinitionId

```
Unregister-ScheduledJob [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefinitionName

```
Unregister-ScheduledJob [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Unregister-ScheduledJob** cmdlet 可删除本地计算机中的计划作业。

当删除或注销计划作业时， **get-scheduledjob** 会在 $home \appdata\local\microsoft\windows\powershell\scheduledjobs 目录) 中删除计划作业 (的目录，该目录包含用于定义计划作业、作业执行历史记录和所有作业结果的 XML 文件。
此操作还将删除任务计划程序中的作业。

**Unregister-ScheduledJob** 仅删除使用 Register-ScheduledJob cmdlet 创建的计划作业。
它不会删除在任务计划程序中创建的计划作业。

你可以使用 **get-scheduledjob** 的参数，按 ID 或名称或从 Get-ScheduledJob 中的管道计划作业来删除 **get-scheduledjob** 。

**Unregister-ScheduledJob** 是 PSScheduledJob 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：删除计划作业

```
PS C:\> Unregister-ScheduledJob TestJob
```

此命令删除本地计算机上的 TestJob 计划作业。

### 示例 2：删除所有计划作业

```
PS C:\> Get-ScheduledJob | Unregister-ScheduledJob -Force
PS C:\> Unregister-ScheduledJob -Name "*" -Force
```

此示例显示删除本地计算机上所有计划作业的两个不同命令。

第一个命令使用 Get-ScheduledJob cmdlet 获取本地计算机上的所有计划作业。
管道运算符 (|) 将计划作业发送到 **Unregister-ScheduleJob** ，它将删除这些作业。

第二个命令使用具有所有 (*) 的值的 *Unregister-ScheduledJob* 的 **Name** 参数来删除所有计划作业。

这两个命令都使用 *Force* 参数，该参数可删除计划作业，即使该作业的实例正在运行也是如此。

### 示例 3：删除远程计算机上的计划作业

```
PS C:\> Invoke-Command -ComputerName "Server01" { Unregister-ScheduledJob -Name "Test*"}
```

此命令将删除 Server01 远程计算机上以 Test 开头的名称的计划作业。
此命令使用 Invoke-Command cmdlet 在 Server02 计算机上运行 **Unregister-ScheduledJob** 命令。

## PARAMETERS

### -Force
删除计划作业，即使该作业的实例正在运行也是如此。
默认情况下， **Unregister-ScheduledJob** 不会中断正在运行的作业。

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

### -Id
删除具有指定标识号 (ID) 的计划作业。
在计算机上输入计划作业的 ID。

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
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
还可以通过管道将 **ScheduledJob** 对象传递给 **Unregister-JobTrigger** 。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
删除具有指定名称的计划作业。
在计算机上输入一个或多个计划作业的名称。
支持通配符。

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

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
你可以通过管道将计划作业传递给 Unregister-ScheduledJob

## 输出

### 无
此 cmdlet 将不生成任何输出。

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
