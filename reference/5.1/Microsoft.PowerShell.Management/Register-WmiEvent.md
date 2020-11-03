---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 07/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/register-wmievent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-WmiEvent
ms.openlocfilehash: be29ce6376dea7686c0c063cc5528fbc7d840a9d
ms.sourcegitcommit: 41b072f0b6046d619b0e7f758982783fb648a3d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2020
ms.locfileid: "93199192"
---
# Register-WmiEvent

## 摘要
订阅 Windows Management Instrumentation (WMI) 事件。

## SYNTAX

### class（默认值）

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Class] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### query

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Query] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION

`Register-WmiEvent`Cmdlet 订阅本地计算机或远程计算机上的 Windows Management Instrumentation (WMI) 事件。

当引发订阅的 WMI 事件时，会将该事件添加到本地会话的事件队列中，即使该事件是在远程计算机上发生的也是如此。 若要获取事件队列中的事件，请使用 `Get-Event` cmdlet。

您可以使用的参数 `Register-WmiEvent` 订阅远程计算机上的事件，并指定可帮助您在队列中标识事件的事件的属性值。 你还可以使用 **Action** 参数指定在引发订阅事件时要执行的操作。

订阅事件时，会向会话中添加一个事件订阅服务器。 若要获取会话中的事件订阅程序，请使用 `Get-EventSubscriber` cmdlet。 若要取消订阅，请使用 `Unregister-Event` cmdlet，该 cmdlet 将从会话中删除事件订阅程序。

新通用信息模型 (CIM) cmdlet，引入了 Windows PowerShell 3.0，执行与 WMI cmdlet 相同的任务。 CIM cmdlet 符合 WS-Management (WSMan) 标准以及 CIM 标准，这使 cmdlet 能够使用相同的技术来管理运行 Windows 操作系统的计算机和运行其他操作系统的计算机。 请 `Register-WmiEvent` 考虑使用 [CimIndicationEvent](../cimcmdlets/register-cimindicationevent.md) cmdlet，而不是使用。

## 示例

### 示例1：订阅类生成的事件

此命令订阅由 **Win32_ProcessStartTrace** 类生成的事件。 只要进程启动，此类就会引发一个事件。

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
```

### 示例2：订阅进程的创建事件

此命令使用一个查询订阅 Win32_process 实例创建事件。

```powershell
$wmiParameters = @{
  Query = "select * from __instancecreationevent within 5 where targetinstance isa 'win32_process'"
  SourceIdentifier = "WMIProcess"
  MessageData = "Test 01"
  TimeOut = 500
}
Register-WmiEvent @wmiParameters
```

### 示例3：使用操作来响应事件

此示例说明如何使用操作来响应事件。 在这种情况下，当进程启动时， `Start-Process` 当前会话中的所有命令都将写入 XML 文件。

```powershell
$action = { Get-History | where { $_.commandline -like "*start-process*" } | export-cliXml "commandHistory.clixml" }
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

```Output
Id    Name            State      HasMoreData   Location  Command
--    ----            -----      -----------   --------  -------
1     ProcessStarted  NotStarted False                   get-history | where {...
```

使用 **Action** 参数时，将 `Register-WmiEvent` 返回表示事件操作的后台作业。 可以使用 **作业** cmdlet （如 `Get-Job` 和 `Receive-Job` ）来管理事件作业。

有关详细信息，请参阅 about_Jobs。

### 示例4：注册远程计算机上的事件

此示例注册远程计算机 Server01 上的事件。

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "Start" -Computername Server01
Get-Event -SourceIdentifier "Start"
```

WMI 将这些事件返回到本地计算机并将其存储在当前会话的事件队列中。 若要检索这些事件，请运行本地 `Get-Event` 命令。

## PARAMETERS

### -Action

指定用于处理事件的命令。 **操作** 参数中的命令在引发事件时运行，而不是将事件发送到事件队列。 将命令括在大括号中， (`{}`) 创建脚本块。

**Action** 的值可以包括 `$Event` 、 `$EventSubscriber` 、 `$Sender` 、 `$EventArgs` 和 `$Args` 自动变量，这些变量向 **操作** 脚本块提供有关事件的信息。 有关详细信息，请参阅 about_Automatic_Variables。

指定操作时， `Register-WmiEvent` 将返回表示该操作的事件作业对象。 你可以使用包含 **job 名词 (作业 cmdlet** **) 的 cmdlet** 来管理事件作业。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 101
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Class

指定要订阅的事件。 请输入用于生成这些事件的 WMI 类。 每个命令中都需要 **类** 或 **查询** 参数。

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

指定在其上运行命令的计算机的名称。 默认为本地计算机。

键入计算机的 NetBIOS 名称、IP 地址或完全限定的域名。 若要指定本地计算机，请键入计算机名、点 (`.`) 或 localhost。

此参数不依赖于 Windows PowerShell 远程处理。 即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

指定有权执行此操作的用户帐户。 默认为当前用户。

键入用户名（如 User01 或 Domain01\User01）或输入 PSCredential 对象，例如由 cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。 键入用户名时，此 cmdlet 会提示输入密码。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Forward

指示此 cmdlet 将此订阅的事件发送到本地计算机上的会话。
如果要在远程计算机或远程会话中注册事件，可使用此参数。

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

### -MaxTriggerCount

指定最大触发器计数。

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

### -MessageData

指定将与此事件订阅关联的任何额外数据。 此参数的值出现在与此订阅关联的所有事件的 **MessageData** 属性中。

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

指定 WMI 类的命名空间。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

指定 WMI 查询语言 (WQL) 标识 WMI 事件类的查询，例如： `select * from __InstanceDeletionEvent` 。

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

指定你为订阅选择的名称。 你选择的名称必须在当前会话中唯一。 默认值为 Windows PowerShell 指定的 GUID。

此参数的值显示在订阅服务器对象以及与此订阅关联的所有事件对象的 **SourceIdentifier** 属性值中。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportEvent

指示此 cmdlet 隐藏事件订阅。 在当前订阅是更复杂的事件注册机制的一部分并且不应单独发现时，可使用此参数。

若要查看或取消使用 **SupportEvent** 参数创建的订阅，请指定和 Cmdlet 的 **Force** 参数 `Get-EventSubscriber` `Unregister-Event` 。

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

### -Timeout

指定 Windows PowerShell 等待此命令完成的时间。

默认值为 0（零），表示没有超时，这将导致 Windows PowerShell 无限期地等待。

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: TimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

不能通过管道将对象传递给此 cmdlet。

## 输出

### 无

此 cmdlet 将不生成任何输出。

## 注释

若要在 Windows Vista 或更高版本的 Windows 操作系统中使用此 cmdlet，请使用 "以管理员身份运行" 选项启动 Windows PowerShell。

事件、事件订阅和事件队列仅存在于当前会话中。 如果关闭当前会话，将丢弃事件队列并取消事件订阅。

## 相关链接
