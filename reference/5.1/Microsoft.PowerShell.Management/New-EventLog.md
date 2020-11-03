---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-EventLog
ms.openlocfilehash: 61fafc0670a24fd6ca057e4cf0c7179d90446b07
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198085"
---
# New-EventLog

## 摘要
在本地或远程计算机上创建新事件日志和新事件源。

## SYNTAX

```
New-EventLog [-LogName] <string> [-Source] <string[]> [[-ComputerName] <string[]>]
  [-CategoryResourceFile <string>] [-MessageResourceFile <string>] [-ParameterResourceFile <string>]
  [<CommonParameters>]
```

## DESCRIPTION

此 cmdlet 在本地或远程计算机上创建新的传统事件日志。 此外，它还会注册写入新日志或现有日志的事件源。

包含 EventLog 名词的 cmdlet (EventLog cmdlet) 仅适用于传统事件日志。
若要从使用 windows Vista 和更高版本 Windows 中的 Windows 事件日志技术的日志中获取事件，请使用 `Get-WinEvent` 。

## 示例

### 示例 1-创建新的事件日志

此命令在本地计算机上创建 TestLog 事件日志并为该日志注册新源。

```powershell
New-EventLog -source TestApp -LogName TestLog -MessageResourceFile C:\Test\TestApp.dll
```

### 示例 2-向现有日志添加新的事件源

此命令将一个新事件源 NewTestApp 添加到 Server01 远程计算机上的应用程序日志。

```powershell
$file = "C:\Program Files\TestApps\NewTestApp.dll"
New-EventLog -ComputerName Server01 -Source NewTestApp -LogName Application -MessageResourceFile $file -CategoryResourceFile $file
```

该命令要求 NewTestApp.dll 文件位于 Server01 计算机上。

## PARAMETERS

### -CategoryResourceFile

指定某一文件的路径，该文件包含源事件的类别字符串。 此文件也称为“类别消息文件”。

文件必须存在于正在创建事件日志的计算机上。 此参数不会创建或移动文件。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

在指定计算机上创建新事件日志。 默认为本地计算机。

远程计算机的 NetBIOS 名称、IP 地址或完全限定的域名。
若要指定本地计算机，请键入该计算机名称、句点 (.) 或“localhost”。

此参数不依赖于 PowerShell 远程处理。 **ComputerName** `Get-EventLog` 即使你的计算机未配置为运行远程命令，你也可以使用 ComputerName 参数。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 3
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName

指定事件日志的名称。

如果日志不存在，则 `New-EventLog` 创建日志，并将此值用于新事件日志的 **Log** 和 **LogDisplayName** 属性。 如果该日志存在，则 `New-EventLog` 注册事件日志的新源。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageResourceFile

指定某一文件的路径，该文件包含源事件的消息格式设置字符串。
此文件也称为“事件消息文件”。

文件必须存在于正在创建事件日志的计算机上。
此参数不会创建或移动文件。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterResourceFile

指定某一文件的路径，该文件包含用于事件说明中的参数替换的字符串。 此文件也称为“参数消息文件”。

文件必须存在于正在创建事件日志的计算机上。
此参数不会创建或移动文件。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

指定事件日志源（如写入事件日志的应用程序）的名称。 此参数是必需的。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 2
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

### System.Diagnostics.EventLogEntry

## 注释

若要 `New-EventLog` 在 Windows Vista 和更高版本的 windows 上使用，请使用 "以管理员身份运行" 选项打开 PowerShell。

若要在 Windows Vista、Windows XP Professional 或 Windows Server 2003 中创建事件源，则你必须是计算机上 Administrators 组的成员。

创建新事件日志和新事件源时，系统会为新日志注册新源，但只有在新日志中写入首个条目时才会创建该日志。

操作系统将事件日志存储为文件。

创建新的事件日志时，会将关联的文件存储在 `$env:SystemRoot\System32\Config` 指定计算机上的目录中。

文件名是带有 .evt 文件扩展名的 **Log** 属性的前八个字符。

## 相关链接

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
