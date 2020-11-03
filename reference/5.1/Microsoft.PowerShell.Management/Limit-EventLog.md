---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/limit-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Limit-EventLog
ms.openlocfilehash: 3ec3214103dc6151e148f7482b0be8b821871e3c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198096"
---
# Limit-EventLog

## 摘要
设置限制事件日志大小及其条目存在时间的事件日志属性。

## SYNTAX

```
Limit-EventLog [-LogName] <String[]> [-ComputerName <String[]>] [-RetentionDays <Int32>]
 [-OverflowAction <OverflowAction>] [-MaximumSize <Int64>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
" **限制-EventLog** " cmdlet 设置典型事件日志的最大大小，每个事件必须保留多长时间，当日志达到其最大值时，会发生什么情况。
你可以使用它来限制本地或远程计算机上的事件日志。

包含 EventLog 名词的 cmdlet (EventLog cmdlet) 仅适用于传统事件日志。
若要从使用 Windows Vista 以及 Windows 更高版本中的 Windows 事件日志技术的日志中获取事件，请使用 Get-WinEvent。

## 示例

### 示例 1：增加事件日志的大小

```
PS C:\> Limit-EventLog -LogName "Windows PowerShell" -MaximumSize 20KB
```

此命令将本地计算机上的 Windows PowerShell 事件日志的最大大小增加到 20480 字节 (20 KB)。

### 示例 2：在指定持续时间内保留事件日志

```
PS C:\> Limit-EventLog -LogName Security -ComputerName "Server01", "Server02" -RetentionDays 7
```

此命令确保计算机 Server01 和 Server02 上的安全日志中的事件至少保留 7 天。

### 示例 3：更改所有事件日志的溢出操作

```
PS C:\> $Logs = Get-EventLog -List | ForEach {$_.log}
PS C:\> Limit-EventLog -OverflowAction OverwriteOlder -LogName $Logs
PS C:\> Get-EventLog -List

Max(K) Retain OverflowAction     Entries  Log
------ ------ --------------     -------  ---
15,168      0 OverwriteOlder       3,412  Application
512         0 OverwriteOlder           0  DFS Replication
512         0 OverwriteOlder          17  DxStudio
10,240      7 OverwriteOlder           0  HardwareEvents
512         0 OverwriteOlder           0  Internet Explorer
512         0 OverwriteOlder           0  Key Management Service
16,384      0 OverwriteOlder           4  ODiag
16,384      0 OverwriteOlder         389  OSession Security
15,168      0 OverwriteOlder      19,360  System
15,360      0 OverwriteOlder      15,828  Windows PowerShell
```

此示例将本地计算机上所有事件日志的溢出操作更改为 OverwriteOlder。

第一条命令获取本地计算机上所有日志的日志名称。
第二条命令设置溢出操作。
第三条命令显示结果。

## PARAMETERS

### -ComputerName
指定远程计算机。
默认为本地计算机。

键入远程计算机的 NetBIOS 名称、Internet 协议 (IP) 地址或完全限定的域名 (FQDN)。
若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。

此参数不依赖于 Windows PowerShell 远程处理。
即使你的计算机未配置为运行远程命令，你也可以使用 **Limit-EventLog** 的 *ComputerName* 参数。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName
指定事件日志。
输入一个或多个事件日志的日志名称（Log 属性的值；而非 LogDisplayName），名称之间用逗号分隔。
不允许使用通配符。
此参数是必需的。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumSize
指定事件日志的最大大小（以字节为单位）。
输入一个介于 64 千字节 (KB) 和 4 千兆字节 (GB) 之间的值。
该值必须能够被 64 KB (65536) 整除。

此参数指定表示传统事件日志的 **MaximumKilobytes** **对象的** "属性" 属性的值。

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowAction
指定事件日志达到其最大大小时会发生什么情况。

此参数的可接受值为：

- DoNotOverwrite：保留现有条目并丢弃新条目。
- OverwriteAsNeeded：每个新条目覆盖最旧条目。
- OverwriteOlder：新事件覆盖早于 **MinimumRetentionDays** 属性指定的值的事件。 如果没有 **MinimumRetentionDays** 属性值指定的任何事件，则将丢弃新的事件。

此参数指定表示传统事件日志的 **OverflowAction** **对象的** "属性" 属性的值。

```yaml
Type: System.Diagnostics.OverflowAction
Parameter Sets: (All)
Aliases: OFA
Accepted values: OverwriteOlder, OverwriteAsNeeded, DoNotOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionDays
指定事件必须保留在事件日志中的最短天数。

此参数指定表示传统事件日志的 **MinimumRetentionDays** **对象的** "属性" 属性的值。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MRD

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
不能通过管道将输入传递给此 cmdlet。

## 输出

### 无
此 cmdlet 将不生成任何输出。

## 注释

* 若要在 Windows Vista 及 Windows 的更高版本上使用此 cmdlet，请使用“以管理员身份运行”选项打开 Windows PowerShell。

  此 cmdlet 可更改表示传统事件日志的 **System.Diagnostics.EventLog** 对象的属性。
若要查看事件日志属性的当前设置，请键入 `Get-EventLog -List`。

*

## 相关链接

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
