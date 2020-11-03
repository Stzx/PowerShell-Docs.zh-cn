---
external help file: Remove-DscConfigurationDocument.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DscConfigurationDocument
ms.openlocfilehash: d3e9b15dfeea94921503247adc08b291eed9d7d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198255"
---
# Remove-DscConfigurationDocument

## 摘要
从 DSC 配置存储中删除配置文档。

## SYNTAX

```
Remove-DscConfigurationDocument -Stage <Stage> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
`Remove-DscConfigurationDocument`Cmdlet 从 Windows PowerShell Desired State configuration (DSC) 配置存储中删除配置文档 ( 的 mof 文件) 。
在配置过程中，该 `Start-DscConfiguration` cmdlet 会将一个 mof 文件复制到目标计算机上的一个文件夹中。
此 cmdlet 会删除该配置文档，并执行其他清理。

此 cmdlet 仅在 [WINDOWS RT 8.1、Windows 8.1 和 Windows Server 2012 R2 的2014年11月的更新汇总](https://support.microsoft.com/kb/3000850) 中提供，Microsoft 支持部门库中。

## 示例

### 示例 1：删除当前配置文档

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Remove-DscConfigurationDocument -Stage Current -CimSession $Session
```

第一个命令通过使用 **New-CimSession** cmdlet 创建 CIM 会话，然后将 **CimSession** 对象存储在 $Session 变量中。
该命令会提示你输入密码。
要了解详情，请键入 `Get-Help New-CimSession`。

第二个命令针对 $Session 中存储的 **CimSession** 中指定的计算机删除当前配置文档。

## PARAMETERS

### -AsJob
指示此 cmdlet 将命令作为后台作业运行。

如果指定 AsJob  参数，该命令将返回表示作业的对象，然后显示命令提示符。
作业完成前，可以继续在此会话中工作。
作业在本地计算机上创建，并且来自远程计算机的结果将自动返回本地计算机。
若要管理作业，请使用 Job cmdlet。
若要获取作业结果，请使用 Receive-Job cmdlet。

若要使用此参数，必须为本地计算机和远程计算机配置远程处理，并且在 Windows Vista 以及更高版本的 Windows 操作系统上，还必须使用“以管理员身份运行”选项打开 Windows PowerShell。
有关详细信息，请参阅 [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)。

有关 Windows PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 和 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)。

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

### -CimSession
在远程会话中或在远程计算机上运行 cmdlet。
输入计算机名或会话对象，例如 **CimSession** 或 **CimSession** cmdlet 的输出。

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

### -Force
指示此 cmdlet 在删除配置文档之前停止正在运行的配置作业。
强制运行命令而不要求用户确认。

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

### -Stage
指定要删除的配置文档。
可以指定多个文档。
此参数的可接受值为：

- Current。
删除描述系统当前状态的配置文档。
- Pending。
删除描述系统挂起状态的配置文档。
- Previous。
删除描述系统上一个状态的配置文档。

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoveDscConfigurationDocument.Stage
Parameter Sets: (All)
Aliases:
Accepted values: Current, Pending, Previous

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
指定可为运行 cmdlet 而确立的操作的最大数量。
如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。
该限制仅适用于当前 cmdlet，不适用于会话或计算机。

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

### 无

## 输出

### 无

## 注释

## 相关链接

[Windows PowerShell Desired State Configuration 概述](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)
