---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 3/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventLog
ms.openlocfilehash: ab1a97dc3c78bbfdcc239fd573ef3b1f839e2b21
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198297"
---
# Get-EventLog

## 摘要
获取在本地计算机或远程计算机上的事件日志或事件日志列表中的事件。

## SYNTAX

### LogName（默认值）

```
Get-EventLog [-LogName] <String> [-ComputerName <String[]>] [-Newest <Int32>] [-After <DateTime>]
 [-Before <DateTime>] [-UserName <String[]>] [[-InstanceId] <Int64[]>] [-Index <Int32[]>]
 [-EntryType <String[]>] [-Source <String[]>] [-Message <String>] [-AsBaseObject]
 [<CommonParameters>]
```

### 列出

```
Get-EventLog [-ComputerName <String[]>] [-List] [-AsString] [<CommonParameters>]
```

## DESCRIPTION

`Get-EventLog`Cmdlet 将从本地和远程计算机获取事件和事件日志。 默认情况下， `Get-EventLog` 从本地计算机获取日志。 若要从远程计算机获取日志，请使用 **ComputerName** 参数。

您可以使用 `Get-EventLog` 参数和属性值来搜索事件。 Cmdlet 将获取与指定的属性值匹配的事件。

包含名词的 PowerShell cmdlet `EventLog` 仅适用于 Windows 经典事件日志，例如应用程序、系统或安全性。 若要在 Windows Vista 和更高版本的 Windows 版本中获取使用 Windows 事件日志技术的日志，请使用 `Get-WinEvent` 。

> [!NOTE]
> `Get-EventLog` 使用已弃用的 Win32 API。 结果可能不准确。 请改用 `Get-WinEvent` cmdlet。

## 示例

### 示例1：获取本地计算机上的事件日志

此示例显示了本地计算机上可用事件日志的列表。 Log 列中的名称与 **LogName** 参数一起使用，以指定搜索事件的日志。

```powershell
Get-EventLog -List
```

```Output
Max(K)   Retain   OverflowAction      Entries  Log
------   ------   --------------      -------  ---
15,168        0   OverwriteAsNeeded   20,792   Application
15,168        0   OverwriteAsNeeded   12,559   System
15,360        0   OverwriteAsNeeded   11,173   Windows PowerShell
```

`Get-EventLog`Cmdlet 使用 **List** 参数显示可用的日志。

### 示例2：获取本地计算机上的事件日志中的最新条目

此示例获取系统事件日志中的最新条目。

```powershell
Get-EventLog -LogName System -Newest 5
```

```Output
Index   Time          EntryType    Source              InstanceID   Message
-----   ----          ---------    ------              ----------   -------
13820   Jan 17 19:16  Error        DCOM                     10016   The description for Event...
13819   Jan 17 19:08  Error        DCOM                     10016   The description for Event...
13818   Jan 17 19:06  Information  Service Control...  1073748864   The start type of the Back...
13817   Jan 17 19:05  Error        DCOM                     10016   The description for Event...
13815   Jan 17 19:03  Information  Microsoft-Windows...        35   The time service is now sync...
```

`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统事件日志。 **最新** 参数返回五个最新事件。

### 示例3：查找事件日志中特定数量的条目的所有源

此示例显示了如何查找系统事件日志中最新的1000条目中包含的所有源。

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$Events | Group-Object -Property Source -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count   Name
-----   ----
  110   DCOM
   65   Service Control Manager
   51   Microsoft-Windows-Kern...
   14   EventLog
   14   BTHUSB
   13   Win32k
```

`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统日志。 **最新** 参数选择1000个最近事件。 事件对象存储在 `$Events` 变量中。 `$Events`对象通过管道向下发送到 `Group-Object` cmdlet。
`Group-Object` 使用 **Property** 参数按源将对象分组，并对每个源的对象的数目进行计数。 **NoElement** 参数从输出中删除组成员。
`Sort-Object`Cmdlet 使用 **Property** 参数按每个源名称的计数进行排序。
**降序** 参数按从最高到最低的顺序对列表进行排序。

### 示例4：获取特定事件日志中的错误事件

此示例获取系统事件日志中的错误事件。

```powershell
Get-EventLog -LogName System -EntryType Error
```

```Output
Index Time          EntryType   Source  InstanceID Message
----- ----          ---------   ------  ---------- -------
13296 Jan 16 13:53  Error       DCOM    10016 The description for Event ID '10016' in Source...
13291 Jan 16 13:51  Error       DCOM    10016 The description for Event ID '10016' in Source...
13245 Jan 16 11:45  Error       DCOM    10016 The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error       DCOM    10016 The description for Event ID '10016' in Source...
```

`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统日志。 **EntryType** 参数将筛选事件，以便仅显示错误事件。

### 示例5：从具有 InstanceId 和源值的事件日志获取事件

此示例从系统日志获取特定 InstanceId 和源的事件。

```powershell
Get-EventLog -LogName System -InstanceId 10016 -Source DCOM
```

```Output
Index Time          EntryType  Source  InstanceID  Message
----- ----          ---------  ------  ----------  -------
13245 Jan 16 11:45  Error      DCOM         10016  The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error      DCOM         10016  The description for Event ID '10016' in Source...
13219 Jan 16 10:00  Error      DCOM         10016  The description for Event ID '10016' in Source...
```

`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统日志。 **InstanceID** 参数选择具有指定实例 ID 的事件。 **Source** 参数指定事件属性。

### 示例6：从多台计算机获取事件

此命令从三台计算机上的系统事件日志中获取事件： Server01、Server02 和 Server03。

```powershell
Get-EventLog -LogName System -ComputerName Server01, Server02, Server03
```

`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统日志。 **ComputerName** 参数使用以逗号分隔的字符串来列出要从中获取事件日志的计算机。

### 示例7：获取消息中包含特定单词的所有事件

此命令获取系统事件日志中的所有事件，这些事件包含事件消息中的特定字词。 您指定的 **消息** 参数的值可能包含在消息的内容中，而不会显示在 PowerShell 控制台上。

```powershell
Get-EventLog -LogName System -Message *description*
```

```Output
Index Time          EntryType   Source       InstanceID   Message
----- ----          ---------   ------       ----------   -------
13821 Jan 17 19:17  Error       DCOM              10016   The description for Event ID '10016'...
13820 Jan 17 19:16  Error       DCOM              10016   The description for Event ID '10016'...
13819 Jan 17 19:08  Error       DCOM              10016   The description for Event ID '10016'...
```

`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统事件日志。 **Message** 参数指定要在每个事件的消息字段中搜索的字。

### 示例8：显示事件的属性值

此示例演示如何显示事件的所有属性和值。

```powershell
$A = Get-EventLog -LogName System -Newest 1
$A | Select-Object -Property *
```

```Output
EventID            : 10016
MachineName        : localhost
Data               : {}
Index              : 13821
Category           : (0)
CategoryNumber     : 0
EntryType          : Error
Message            : The description for Event ID '10016' in Source 'DCOM'...
Source             : DCOM
ReplacementStrings : {Local,...}
InstanceId         : 10016
TimeGenerated      : 1/17/2019 19:17:23
TimeWritten        : 1/17/2019 19:17:23
UserName           : username
Site               :
Container          :
```

`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统事件日志。 **最新** 的参数选择最新的事件对象。 对象存储在 `$A` 变量中。 变量中的对象通过 `$A` 管道向下发送到 `Select-Object` cmdlet。
`Select-Object` 使用带有星号的 **属性** 参数 (`*`) 选择该对象的所有属性。

### 示例9：使用源和事件 ID 从事件日志中获取事件

此示例获取指定源和事件 ID 的事件。

```powershell
Get-EventLog -LogName Application -Source Outlook | Where-Object {$_.EventID -eq 63} |
              Select-Object -Property Source, EventID, InstanceId, Message
```

```Output
Source   EventID   InstanceId   Message
------   -------   ----------   -------
Outlook       63   1073741887   The Exchange web service request succeeded.
Outlook       63   1073741887   Outlook detected a change notification.
Outlook       63   1073741887   The Exchange web service request succeeded.
```

`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定应用程序事件日志。 **Source** 参数指定应用程序名称 Outlook。 对象通过管道向下发送到 `Where-Object` cmdlet。 对于管道中的每个对象，该 `Where-Object` cmdlet 都使用变量将 `$_.EventID` 事件 ID 属性与指定值进行比较。 对象通过管道向下发送到 `Select-Object` cmdlet。 `Select-Object` 使用 **Property** 参数来选择要在 PowerShell 控制台中显示的属性。

### 示例10：按属性获取事件和分组

```powershell
Get-EventLog -LogName System -UserName NT* | Group-Object -Property UserName -NoElement |
              Select-Object -Property Count, Name
```

```Output
Count  Name
-----  ----
6031   NT AUTHORITY\SYSTEM
  42   NT AUTHORITY\LOCAL SERVICE
   4   NT AUTHORITY\NETWORK SERVICE
```

`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统日志。 **UserName** 参数包含星号 (`*`) 通配符来指定一部分的用户名。 事件对象将通过管道向下发送到 `Group-Object` cmdlet。 `Group-Object` 使用 **property** 参数来指定 **UserName** 属性用于对对象进行分组，并计算每个用户名的对象数。 **NoElement** 参数从输出中删除组成员。 对象通过管道向下发送到 `Select-Object` cmdlet。
`Select-Object` 使用 **Property** 参数来选择要在 PowerShell 控制台中显示的属性。

### 示例11：获取在特定日期和时间范围内发生的事件

此示例从系统事件日志中获取指定日期和时间范围内的错误事件。 **Before** 和 **After** 参数设置日期和时间范围，但不包括在输出中。

```powershell
$Begin = Get-Date -Date '1/17/2019 08:00:00'
$End = Get-Date -Date '1/17/2019 17:00:00'
Get-EventLog -LogName System -EntryType Error -After $Begin -Before $End
```

```Output
Index Time          EntryType   Source   InstanceID  Message
----- ----          ---------   ------   ----------  -------
13821 Jan 17 13:40  Error       DCOM          10016  The description for Event ID...
13820 Jan 17 13:11  Error       DCOM          10016  The description for Event ID...
...
12372 Jan 17 10:08  Error       DCOM          10016  The description for Event ID...
12371 Jan 17 09:04  Error       DCOM          10016  The description for Event ID...
```

`Get-Date`Cmdlet 使用 **date** 参数来指定日期和时间。 **DateTime** 对象存储在 `$Begin` 和 `$End` 变量中。 `Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统日志。 **EntryType** 参数指定错误事件类型。 日期和时间范围由 **后面** 的参数和 `$Begin` 变量以及 **之前** 的参数和 `$End` 变量设置。

## PARAMETERS

### -After

获取在指定的日期和时间之后发生的事件。 从输出中排除参数日期和时间 **之后** 的。 输入 **DateTime** 对象，例如 cmdlet 返回的值 `Get-Date` 。

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsBaseObject

指示此 cmdlet 为每个事件返回一个标准 **EventLogEntry** 对象。 在没有此参数的情况下， `Get-EventLog` 将返回具有附加的 **不同于 eventlogname** 、 **Source** 和 **InstanceId** 属性的扩展 **PSObject** 对象。

若要查看此参数的效果，请通过管道将事件传递给 `Get-Member` cmdlet，并在结果中检查 **TypeName** 值。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsString

指示此 cmdlet 以字符串而非对象的形式返回输出。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Before

获取在指定日期和时间之前发生的事件。 从输出中排除 **之前** 的参数日期和时间。 输入 **DateTime** 对象，例如 cmdlet 返回的值 `Get-Date` 。

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

此参数指定远程计算机的 NetBIOS 名称、Internet 协议 (IP) 地址或完全限定的域名 (FQDN) 。

如果未指定 **ComputerName** 参数，则 `Get-EventLog` 默认为本地计算机。 参数还接受一个点 (`.`) 来指定本地计算机。

**ComputerName** 参数不依赖于 Windows PowerShell 远程处理。 `Get-EventLog`即使你的计算机未配置为运行远程命令，你也可以使用 With **ComputerName** 参数。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntryType

指定为字符串数组，此 cmdlet 获取的事件的条目类型。

此参数的可接受值为：

- 错误
- 信息
- FailureAudit
- SuccessAudit
- 警告

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Index

指定要从事件日志中获取的索引值。 参数接受以逗号分隔的值字符串。

```yaml
Type: System.Int32[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

指定要从事件日志中获取的实例 Id。 参数接受以逗号分隔的值字符串。

```yaml
Type: System.Int64[]
Parameter Sets: LogName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -List

显示计算机上的事件日志列表。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName

指定一个事件日志的名称。 查找日志名称使用 `Get-EventLog -List` 。 允许使用通配符。 此参数是必需的。

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Message

指定事件消息中的字符串。 可以使用此参数来搜索包含特定单词或短语的消息。 允许使用通配符。

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: MSG

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Newest

从最新事件开始，获取指定的事件数。 例如，事件数是必需的 `-Newest 100` 。 指定返回的最大事件数。

```yaml
Type: System.Int32
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

指定作为字符串数组，写入到此 cmdlet 获取的日志的源。 允许使用通配符。

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ABO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -UserName

指定作为字符串数组，与事件关联的用户名。 输入名称或名称模式，如 `User01` 、 `User*` 或 `Domain01\User*` 。 允许使用通配符。

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

不能通过管道将输入传递给 `Get-EventLog` 。

## 输出

### System.Diagnostics.EventLogEntry. System.Diagnostics.EventLog. System.String

如果指定了 **LogName** 参数，则输出为 **EventLogEntry** 对象的集合。

如果仅指定了 **List** 参数，则输出为 **系统** 对象的集合。

如果同时指定了 **List** 和 **AsString** 参数，则输出为 **system.string** 对象的集合。

## 注释

`Get-EventLog` `Get-WinEvent` Windows PE) Windows 预安装环境 (不支持 cmdlet 和。

## 相关链接

[Clear-EventLog](Clear-EventLog.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
