---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-EventLog
ms.openlocfilehash: 4cf29146727c9a54715459a2d56e47a27c5bacc0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198069"
---
# Remove-EventLog

## 摘要
删除事件日志或注销事件源。

## SYNTAX

### Default（默认值）

```
Remove-EventLog [[-ComputerName] <String[]>] [-LogName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### 源

```
Remove-EventLog [[-ComputerName] <String[]>] [-Source <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**删除-EventLog** cmdlet 从本地或远程计算机中删除事件日志文件，并将该日志的所有事件源注销。
你还可以使用此 cmdlet 注销事件源，而无需删除任何事件日志。

包含 **eventlog** 名词的 Cmdlet （ **eventlog** cmdlet）仅适用于经典事件日志。
若要从使用 windows Vista 和更高版本的 windows 操作系统中的 Windows 事件日志技术的日志中获取事件，请使用 Get-winevent。

警告：此 cmdlet 可以删除操作系统事件日志，这可能会导致应用程序失败和意外的系统行为。

## 示例

### 示例1：从本地计算机中删除事件日志

```
PS C:\> Remove-EventLog -LogName "MyLog"
```

此命令从本地计算机中删除 MyLog 事件日志并注销其事件源。

### 示例2：从多台计算机中删除事件日志

```
PS C:\> Remove-EventLog -LogName "MyLog", "TestLog" -ComputerName "Server01", "Server02", "localhost"
```

此命令从本地计算机和 Server01 和 Server02 远程计算机中删除 MyLog 和 TestLog 事件日志。
该命令也将注销这些日志的事件源。

### 示例3：删除事件源

```
PS C:\> Remove-EventLog -Source "MyApp"
```

此命令从本地计算机上的日志中删除 MyApp 事件源。
命令完成后，MyApp 程序将无法写入任何事件日志。

### 示例4：删除事件日志并确认操作

```
The first command lists the event logs on the local computer.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
15,168      7 OverwriteAsNeeded          12 ZapLog

The second command deletes the ZapLog event log.
PS C:\> Remove-EventLog -LogName "ZapLog"

The third command lists the event logs again. The ZapLog event log no longer appears in the list.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
```

这些命令显示了如何列出计算机上的事件日志，并验证是否已成功 **删除 EventLog** 命令。

### 示例5：删除事件源并确认操作

```
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'" | foreach {$_.sources}
MyApp
TestApp
PS C:\> Remove-Eventlog -Source "MyApp"
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'"} | foreach {$_.sources}
TestApp
```

这些命令使用 Get-WmiObject cmdlet 列出本地计算机上的事件源。
可以使用这些命令验证用于删除事件源的命令是否成功。

第一个命令获取本地计算机上 TestLog event 日志的事件源。
MyApp 就是其中一个事件源。

第二个命令使用 **Remove-EventLog** 的 *Source* 参数删除 MyApp 事件源。

第三个命令与第一个命令相同。
它显示 MyApp 事件源已删除。

## PARAMETERS

### -ComputerName
指定远程计算机。
默认为本地计算机。

键入远程计算机的 NetBIOS 名称、IP 地址或完全限定的域名。
若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。

此参数不依赖于 Windows PowerShell 远程处理。
即使你的计算机未配置为运行远程命令，你也可以使用 " **删除-EventLog** " 的 *ComputerName* 参数。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName
指定事件日志。
输入一个或多个事件日志的日志名称，用逗号分隔。
日志名称是 **log** 属性的值，而不是 *LogDisplayName* ，不允许使用通配符。
此参数是必需的。

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
指定此 cmdlet 取消注册的事件源。
输入源名称，而不是可执行文件名称，用逗号分隔。

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: SRC

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
此 cmdlet 不返回任何输出。

## 注释

* 若要在 Windows Vista 和更高版本的 Windows 操作系统上使用 **删除事件日志** ，请使用 "以管理员身份运行" 选项启动 windows PowerShell。

  如果删除了事件日志然后又重新创建该日志，则无法注册相同的事件源。
使用这些事件源将条目写入原始日志的应用程序将无法再写入新日志。

* 当注销特定日志的事件源时，该事件源将无法在其他事件日志中写入条目。

## 相关链接

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
