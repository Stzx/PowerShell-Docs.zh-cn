---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ScheduledJob
ms.openlocfilehash: a7ea520d7d0365fd0de8c9d0bb767981b68467c6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197799"
---
# Disable-ScheduledJob

## 摘要
禁用计划作业。

## SYNTAX

### Definition（默认值）

```
Disable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefinitionId

```
Disable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefinitionName

```
Disable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Disable-ScheduledJob** cmdlet 可临时禁用计划作业。
该禁用操作会保留所有作业属性且不禁用作业触发器，但它会在触发计划作业后阻止这些作业自动启动。
可使用 Start-Job cmdlet 启动禁用计划作业，或可将禁用计划作业用作模板。

若要禁用某个计划作业， **Disable-ScheduledJob** cmdlet 会将该计划作业的 **Enabled** 属性设置为 False ($false)。
若要重新启用计划作业，请使用 Enable-ScheduledJob cmdlet。

**Disable-ScheduledJob** 是 **PSScheduledJob** 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：禁用计划作业

```
PS C:\> Disable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
```

此命令禁用本地计算机上的具有 ID 2 的计划作业。
此输出显示了该命令的作用。

### 示例 2：禁用所有计划作业

```
PS C:\> Get-ScheduledJob | Disable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        False
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     False
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       False
```

此命令禁用本地计算机上的所有计划作业。
将使用 Get-ScheduledJob cmdlet 获取所有计划作业，并使用 **Disable-ScheduledJob** cmdlet 将其禁用。

可使用 Enable-ScheduledJob cmdlet 重新启用计划作业，并使用 Start-Job cmdlet 运行禁用计划作业。

**Disable-ScheduledJob** 不会在禁用已禁用的计划作业时生成警告或错误，因此可以无条件地禁用所有计划作业。

### 示例 3：禁用选定的计划作业

```
PS C:\> Get-ScheduledJob | Where-Object {!$_.Credential} | Disable-ScheduledJob
```

此命令禁用不包含凭据的计划作业。
对于不具有凭据的作业，可使用创建它们的用户的权限进行运行。

此命令使用 Get-ScheduledJob cmdlet 获取计算机上的所有计划作业。
管道运算符将计划作业发送到 Where-Object cmdlet，此 cmdlet 可选择没有凭据的计划作业。
此命令使用 not (!) 运算符并引用计划作业的 Credential 属性。
另一个管道运算符将选定的计划作业发送到 **Disable-ScheduledJob** cmdlet，此 cmdlet 可禁用这些作业。

### 示例 4：禁用远程计算机上的计划作业

```
PS C:\> Invoke-Command -ComputerName Srv01, Srv10 -ScriptBlock {Disable-ScheduledJob -Name TestJob}
```

此命令禁用 Srv01 和 Srv10 这两台远程计算机上的 TestJob 计划作业。

此命令使用 Invoke-Command cmdlet 在 Srv01 和 Srv10 计算机上运行 **Disable-ScheduledJob** 命令。
此命令使用 *Disable-ScheduledJob* 的 **Name** 参数，以在每台计算机上选择 TestJob 计划作业。

### 示例 5：通过计划作业的全局 ID 对其进行禁用

```
The first command demonstrates one way of finding the GlobalID of a scheduled job. The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Format-Table cmdlet, which displays the Name, GlobalID, and Command properties of each job in a table.
PS C:\> Get-ScheduledJob | Format-Table -Property Name, GlobalID, Command -Autosize
Name             GlobalId                             Command
----             --------                             -------
ArchiveProjects1 a26a0b3d-b4e6-44d3-8b95-8706ef621f7c C:\Scripts\Archive-DxProjects.ps1
Inventory        3ac37e5d-84c0-4a8f-9661-7e88ebb8f914 \\Srv01\Scripts\Get-FullInventory.ps1
Backup-Scripts   4d0cc6be-c082-48d1-baec-1bd8278f3c81  Copy-Item C:\CurrentScripts\*.ps1 -Destination C:\BackupScripts
Test-HelpFiles   d77020ca-f20d-42be-86c8-fc64df97db90 .\Test-HelpFiles.ps1
Test-HelpFiles   2f1606d2-c6cf-4bef-8b1c-ae36a9cc9934 .\Test-DomainHelpFiles.ps1

The second command uses the  Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Where-Object cmdlet, which selects the scheduled job with the specified global ID. Another pipeline operator sends the job to the **Disable-ScheduledJob** cmdlet, which disables it.
PS C:\> Get-ScheduledJob | Where-Object {$_.GlobalID = d77020ca-f20d-42be-86c8-fc64df97db90} | Disable-ScheduledJob
```

此示例显示了如何通过使用计划作业的全局标识符对其进行禁用。
计划作业的 GlobalID 属性值是唯一标识符 (GUID)。
当需要使用精度时（例如，禁用多台计算机上的计划作业时），可使用 GlobalID 值。

## PARAMETERS

### -Id
禁用具有指定标识号 (ID) 的计划作业。
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
指定要禁用的计划作业。
请输入包含 **ScheduledJobDefinition** 对象的变量，或者键入获取 **ScheduledJobDefinition** 对象的命令或表达式，例如 Get-ScheduledJob 命令。
还可以通过管道将 **ScheduledJobDefinition** 对象传递给 **Disable-ScheduledJob** 。

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
禁用具有指定名称的计划作业。
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
你可以通过管道将计划作业传递给 **Disable-ScheduledJob** 。

## 输出

### 无或 Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
如果你使用 **Passthru** 参数，则 **Disable-ScheduledJob** 将返回已禁用的计划作业。
否则，此 cmdlet 将不生成任何输出。

## 注释

* **Disable-ScheduledJob** 不会在禁用已禁用的计划作业时生成警告或错误。

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
