---
external help file: Stop-DscConfiguration.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/19/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/stop-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-DscConfiguration
ms.openlocfilehash: 93c8585ae948dfa360a2ae8e2563670de8fd6e93
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197830"
---
# Stop-DscConfiguration

## 摘要
停止正在运行的配置作业。

## SYNTAX

### 全部

```
Stop-DscConfiguration [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Stop-DscConfiguration`Cmdlet 可停止正在运行的配置作业。 使用通用信息模型 (CIM) 会话指定应用此 cmdlet 的计算机。 如果没有正在运行的配置作业，则此 cmdlet 将返回一条警告消息。

`Stop-DscConfiguration` 仅可作为 Microsoft 支持部门库中的 [WINDOWS RT 8.1、Windows 8.1 和 Windows Server 2012 R2 的2014年11月更新汇总](https://support.microsoft.com/kb/3000850) 的一部分。 使用此 cmdlet 之前，请查看[Windows PowerShell 5.0 的新增功能](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)中的信息

## 示例

### 示例 1：停止配置作业

在此示例中，使用 cmdlet 创建 CIM 会话 `New-CimSession` 。 **CimSession** 对象用于停止正在运行的配置作业。

```powershell
$Session = New-CimSession -ComputerName Server01 -Credential ACCOUNTS\User01
Stop-DscConfiguration -CimSession $Session
```

`New-CimSession` 使用 **ComputerName** 参数指定 Server01 计算机。 **Credential** 参数指定用户帐户。 **CimSession** 对象存储在 `$Session` 变量中。 运行该命令时，系统将提示你输入用户帐户的密码。

`Stop-DscConfiguration` 使用 **CimSession** 参数和存储在中的对象 `$Session` 停止配置作业。

## PARAMETERS

### -AsJob

指示此 cmdlet 将命令作为后台作业运行。 有关 PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 和 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)。

若要使用 **AsJob** 参数，必须为本地计算机和远程计算机配置远程处理。 在 Windows Vista 和更高版本的 Windows 操作系统上，你必须通过 "以 **管理员身份运行** " 选项打开 PowerShell。 有关详细信息，请参阅 [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

在远程会话中或在远程计算机上运行 cmdlet。 输入计算机名或会话对象，如或的输出 `New-CimSession` `Get-CimSession` 。

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

`Stop-DscConfiguration` 不支持 **Confirm** 参数。 如果使用 **Confirm** 参数，则会显示错误。

对于支持 **确认** 的 PowerShell cmdlet，使用参数会提示你在运行命令前进行验证。

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

### -Force

强制运行命令而不要求用户确认。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

指定可为运行 cmdlet 而确立的操作的最大数量。

如果省略此参数或输入的值 `0` ，则 PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算最佳限制。 该限制仅适用于当前 cmdlet，不适用于会话或计算机。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

显示运行该 cmdlet 时会发生什么情况。 cmdlet 未运行。

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

### 无

## 输出

### 无

## 注释

## 相关链接

[Get-CimSession](../CimCmdlets/Get-CimSession.md)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[New-CimSession](../CimCmdlets/New-CimSession.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)

[Update-DscConfiguration](Update-DscConfiguration.md)

[Windows PowerShell Desired State Configuration 概述](/powershell/scripting/dsc/overview/overview)
