---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ScheduledJob
ms.openlocfilehash: 757402a348a6b694d2f2aee53053a1b7615dbb53
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197792"
---
# Enable-ScheduledJob

## 摘要
启用计划作业。

## SYNTAX

### Definition（默认值）

```
Enable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefinitionId

```
Enable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefinitionName

```
Enable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Get-scheduledjob** cmdlet 可重新启用已禁用的计划作业，例如通过使用 Disable-ScheduledJob cmdlet 禁用的作业。
触发作业后，它们将自动运行。

若要启用某个计划作业， **get-scheduledjob** cmdlet 会将该计划作业的 Enabled 属性设置为 $True。

**Enabled-get-scheduledjob** 是 Windows PowerShell 中包含的 **PSScheduledJob** 模块中的作业计划 cmdlet 集合之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例1：启用计划作业

```
PS C:\> Enable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
```

此命令启动本地计算机上的具有 ID 2 的计划作业。
此输出显示了该命令的作用。

### 示例2：启用所有计划作业

```
PS C:\> Get-ScheduledJob | Enable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        True
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     True
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       True
```

此命令启用本地计算机上的所有计划作业。
它使用 Get-ScheduledJob cmdlet 获取所有计划作业，并使用 **get-scheduledjob** cmdlet 来启用它们。

如果启用已启用的计划作业，则 **get-scheduledjob** 不会生成警告或错误，因此你可以在不使用条件的情况下启用所有计划作业。

### 示例3：启用选定的计划作业

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where-Object {$_.RunWithoutNetwork} | ForEach-Object {Enable-ScheduledJob -InputObject $_.JobDefinition}
```

此命令启用不需要网络连接的计划作业。

此命令使用 Get-ScheduledJob cmdlet 获取计算机上的所有计划作业。
管道运算符将计划作业发送到 Get-ScheduledJobOption cmdlet，该 cmdlet 可获取每个计划作业的作业选项。
每个作业选项对象都具有一个 JobDefinition 属性，该属性包含关联的计划作业。
JobDefinition 属性用于完成此命令。

该命令使用管道运算符 (|) 将作业选项发送到 Where-Object cmdlet，后者将选择计划作业选项对象，其中 **RunWithoutNetwork** 属性的值为 True ($true) 。
另一个管道运算符将选定的计划作业选项对象发送到 ForEach-Object cmdlet，该 cmdlet 在计划作业的每个作业选项对象的 JobDefinition 属性值中运行 **get-scheduledjob** 命令。

### 示例4：启用远程计算机上的计划作业

```
PS C:\> Invoke-Command -ComputerName "Srv01,Srv10" -ScriptBlock {Enable-ScheduledJob -Name "Inventory"}
```

此命令启用两台远程计算机（Srv01 和 Srv10）上其名称中含有“test”的计划作业。

该命令使用 Invoke-Command cmdlet 在 Srv01 和 Srv10 计算机上运行 **get-scheduledjob** 命令。
此命令使用 *Enable-ScheduledJob* 的 **Name** 参数，以在每台计算机上启用 Inventory 计划作业。

## PARAMETERS

### -Id
启用具有指定标识号 (ID) 的计划作业。
输入计划作业的 ID。

```yaml
Type: System.Int32
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
指定要启用的计划作业。
输入包含 **ScheduledJobDefinition** 对象的变量，或者键入获取 **ScheduledJobDefinition** 对象的命令或表达式，如 Get-ScheduledJob 命令。
还可以通过管道将 **ScheduledJobDefinition** 对象传递给 **get-scheduledjob** 。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
启用具有指定名称的计划作业。
输入计划作业的名称。
支持通配符。

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
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
可以通过管道将计划作业传递给 **get-scheduledjob** 。

## 输出

### 无或 Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
如果你使用 **Passthru** 参数，则 **Enable-ScheduledJob** 将返回已启用的计划作业。
否则，此 cmdlet 将不生成任何输出。

## 注释

* 如果你使用 **get-scheduledjob** 来启用已启用的计划作业，则它不会生成警告或错误。

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
