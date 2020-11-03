---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-EventLog
ms.openlocfilehash: e8dbcf1aa4280c0481714a8a9fb24f2e5ef79ffe
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198032"
---
# Show-EventLog

## 摘要
在事件查看器中显示本地或远程计算机的事件日志。

## SYNTAX

```
Show-EventLog [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
**Show-EventLog** cmdlet 在本地计算机上打开事件查看器，并在其中显示本地计算机或远程计算机上的所有经典事件日志。

若要在 Windows Vista 和更高版本的 Windows 操作系统上打开事件查看器，当前用户必须是本地计算机上 Administrators 组的成员。

 ( **eventlog** Cmdlet 包含 **eventlog** 名词的 cmdlet) 仅适用于经典事件日志。
若要从使用 windows Vista 和更高版本的 windows 操作系统中的 Windows 事件日志技术的日志中获取事件，请使用 Get-WinEvent cmdlet。

## 示例

### 示例1：显示本地计算机的事件日志

```
PS C:\> Show-EventLog
```

此命令打开事件查看器并在其中显示本地计算机上的传统事件日志。

### 示例2：显示远程计算机的事件日志

```
PS C:\> Show-EventLog -ComputerName "Server01"
```

此命令打开事件查看器并在其中显示计算机 Server01 上的传统事件日志。

## PARAMETERS

### -ComputerName
指定远程计算机。
**Show-EventLog** 显示来自本地计算机上事件查看器中指定计算机的事件日志。
默认为本地计算机。

键入远程计算机的 NetBIOS 名称、IP 地址或完全限定的域名。

此参数不依赖于 Windows PowerShell 远程处理。
即使你的计算机未配置为运行远程命令，你也可以使用 *ComputerName* 参数。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
Default value: None
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

* Windows PowerShell 命令提示符在事件查看器打开后立即返回。 当事件查看器处于打开状态时，你可以在当前会话中工作。

  因为此 cmdlet 需要用户界面，所以它无法在 Windows Server 的 Server Core 安装上运行。

*

## 相关链接

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Write-EventLog](Write-EventLog.md)
