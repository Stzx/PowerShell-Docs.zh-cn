---
external help file: Microsoft.PowerShell.ScheduledJob.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/add-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-JobTrigger
ms.openlocfilehash: 6066b8f91c99830fefb09a8bea13fac6ddf958e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197804"
---
# Add-JobTrigger

## 摘要
将作业触发器添加到计划作业。

## SYNTAX

### JobDefinition（默认值）

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-InputObject] <ScheduledJobDefinition[]>
 [<CommonParameters>]
```

### JobDefinitionId

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Id] <Int32[]> [<CommonParameters>]
```

### JobDefinitionName

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION
**Add-JobTrigger** cmdlet 可将作业触发器添加到计划作业。
它可用于将多个触发器添加到多个计划作业。

作业触发器按一次性或定期计划或事件发生时启动计划作业。

使用 **Add-JobTrigger** 的 *Trigger* 参数来标识要添加的作业触发器。
使用 **Add-JobTrigger** 的 *Name* 、 *ID* 或 *InputObject* 参数来标识将触发器添加到的计划作业。

若要创建 *Trigger* 参数的值的作业触发器，请使用 New-JobTrigger cmdlet 或使用哈希表指定作业触发器。

**Add-JobTrigger** 是 **PSScheduledJob** 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：将作业触发器添加到计划作业

```
PS C:\> $Daily = New-JobTrigger -Daily -At 3AMPS
PS C:\> Add-JobTrigger -Trigger $Daily -Name "TestJob"
```

以下命令将每日作业触发器添加到 TestJob 计划作业。

第一个命令使用 New-JobTrigger cmdlet 创建每天凌晨 3:00 启动计划作业的作业触发器。
此命令将作业触发器保存在 $Daily 变量中。

第二个命令使用 **Add-JobTrigger** cmdlet 将 $Startup 变量中的作业触发器添加到 TestJob 计划作业。

### 示例2：将作业触发器添加到多个计划作业

```
PS C:\> Get-ScheduledJob | Add-JobTrigger -Trigger (New-JobTrigger -AtStartup)
```

此命令将一个 AtStartup 作业触发器添加到本地计算机上的所有计划作业。
它使用 Get-ScheduledJob 获取该计算机上的所有计划作业。
它使用管道运算符 (|) 将作业发送到 **Add-JobTrigger** cmdlet，此 cmdlet 将作业触发器添加到每个计划作业。
*Trigger* 参数的值是创建 AtStartup 作业触发器的 New-JobTrigger 命令。

### 示例 3：复制作业触发器

```
PS C:\> $T = Get-JobTrigger -Name "BackupArchives"
PS C:\> Add-JobTrigger -Name "TestBackup,BackupLogs" -Trigger $T
```

以下命令从 BackupArchives 计划作业复制作业触发器，然后将它添加到 TestBackup 和 BackupLogs 计划作业。

第一个命令使用 Get-JobTrigger cmdlet 获取 BackupArchives 计划作业的作业触发器。
此命令将该触发器保存在 $t 变量中。

第二个命令使用 **Add-JobTrigger** cmdlet 将 $t 中的作业触发器添加到 TestBackup 和 BackupLogs 计划作业。

## PARAMETERS

### -Id
指定计划作业的标识号。
**Add-JobTrigger** 将作业触发器添加到指定的计划作业。

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
还可以通过管道将 **ScheduledJob** 对象传递给 **Add-JobTrigger** 。

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
**Add-JobTrigger** 将作业触发器添加到指定的计划作业。
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

### -Trigger
指定要添加的作业触发器。
输入一个可指定作业触发器的哈希表或包含 **ScheduledJobTrigger** 对象的变量，或者键入可获取 **ScheduledJobTrigger** 对象的命令或表达式，例如 Get-JobTrigger 命令。
还可以通过管道将 **ScheduledJobTrigger** 对象传递给 **Add-JobTrigger** 。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger、Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
你可以通过管道将作业触发器或计划作业传递给 **Add-JobTrigger** 。

## 输出

### 无
此 cmdlet 不返回任何输出。

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
