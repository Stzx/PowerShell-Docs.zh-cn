---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 54ba1d7db60db7b4bb64f3161bba9c1fba124219
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197479"
---
# Test-Connection

## 摘要
将 ICMP 回显请求数据包或 ping 发送到一台或多台计算机。

## SYNTAX

### PingCount (默认值) 

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Count <Int32>] [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### PingContinues

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-Continues] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### DetectionOfMTUSize

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -MTUSizeDetect [-Quiet] [<CommonParameters>]
```

### TraceRoute

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-TimeoutSeconds <Int32>] [-TargetName] <String[]> -Traceroute [-Quiet] [<CommonParameters>]
```

### ConnectionByTCPPort

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -TCPPort <Int32> [-Quiet] [<CommonParameters>]
```

## DESCRIPTION

`Test-Connection`Cmdlet 将 Internet 控制消息协议 () ICMP 发送到一台或多台远程计算机并返回回显响应回复。 可以使用此 cmdlet 来确定是否可以通过 IP 网络联系特定的计算机。

您可以使用的参数 `Test-Connection` 同时指定发送计算机和接收计算机，将该命令作为后台作业运行，设置超时和 ping 数目，以及配置连接和身份验证。

与熟悉的 **ping** 命令不同， `Test-Connection` 返回可以在 PowerShell 中调查的 **TestConnectionCommand + PingReport** 对象。 **Quiet** 参数为每个已测试的连接返回 **system.object** 对象中的 **布尔** 值。 如果测试了多个连接，则返回 **布尔** 值的数组。

## 示例

### 示例1：向远程计算机发送回显请求

此示例将来自本地计算机的回显请求数据包发送到 Server01 计算机。

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
Pinging Server01 [10.59.137.44] with 32 bytes of data:
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Ping complete.

Source     Destination Replies
------     ----------- -------
Server01   Server01    {System.Net.NetworkInformation.PingReply, System.Net.NetworkInformation ...
```

`Test-Connection` 使用 **TargetName** 参数指定 Server01 计算机。 **IPv4** 参数指定测试的协议。

在发送到 **成功** 流的 **TestConnectionCommand + PingReport** 对象时，会将 Ping 输出发送到 **信息流** 。 有关输出流的详细信息，请参阅 [about_Redirection](../microsoft.powershell.core/about/about_redirection.md)。

### 示例2：将回显请求发送到多台计算机

此示例将来自本地计算机的 ping 发送到多台远程计算机。

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### 示例3：从多台计算机向计算机发送回显请求

此示例将来自不同源计算机的 ping 发送到一台远程计算机 Server01。

```powershell
Test-Connection -Source Server02, Server12, localhost -TargetName Server01
```

使用此命令格式可从多个点来测试连接的延迟时间。

### 示例4：使用参数自定义测试命令

此示例使用的参数 `Test-Connection` 自定义命令。 本地计算机将 ping 测试发送到远程计算机。

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

`Test-Connection` 使用 **TargetName** 参数指定 Server01。 **Count** 参数指定三个 ping 发送到 Server01 计算机， **延迟** 为2秒的时间间隔。

当 ping 响应预计需要比平时更长的时间（因为有扩展的跃点数或高流量网络条件）时，可以使用这些选项。

### 示例5：将测试作为后台作业运行

此示例演示如何将 `Test-Connection` 命令作为 PowerShell 后台作业运行。

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content "Servers.txt") }
if ($job.JobStateInfo.State -ne "Running") { $Results = Receive-Job $job }
```

该 `Start-Job` 命令使用 `Test-Connection` cmdlet 对企业中的多台计算机执行 ping 操作。
**TargetName** 参数的值是一个 `Get-Content` 命令，该命令从文件中读取计算机名称的列表 `Servers.txt` 。 该命令使用 `Start-Job` cmdlet 将命令作为后台作业运行，并将作业保存在 `$job` 变量中。

此 `if` 命令会检查该作业是否仍在运行。 如果该作业未运行， `Receive-Job` 将获取结果并将其存储在 `$Results` 变量中。

### 示例6：仅在连接测试成功时创建会话

仅当至少一个发送到计算机的 ping 成功时，此示例才会在 Server01 计算机上创建一个会话。

```powershell
if (Test-Connection -TargetName Server01 -Quiet) {New-PSSession Server01}
```

该 `if` 命令使用 `Test-Connection` Cmdlet 对 Server01 计算机进行 ping 操作。 该命令使用 **Quiet** 参数，该参数将返回一个 **布尔** 值，而不是 **TestConnectionCommand + PingReport** 对象。

`$True`如果四个 ping 中有任何一个成功，则值为。 如果没有任何 ping 成功，则该值为 `$False` 。

如果 `Test-Connection` 命令返回的值 `$True` ，则该命令将使用 `New-PSSession` cmdlet 创建 **PSSession** 。

### 示例7：使用 Traceroute 参数

从 PowerShell 6.0 开始， **Traceroute** 参数会在本地计算机与你指定的远程目标与 **TargetName** 参数之间映射路由。

```powershell
Test-Connection -TargetName www.microsoft.com -Traceroute | ForEach-Object {
  $_ | Format-Table Source, DestinationAddress, DestinationHost
  $_.Replies | ForEach-Object {
      $_ | Format-Table Hop, ReplyRouterAddress
      $_.PingReplies | Format-Table
  }
}
```

```Output
Tracing route to www.microsoft.com [96.6.27.90] over a maximum of 128 hops:
  1   0 ms   0 ms   0 ms   192.168.0.3 [192.168.0.3]
  2   0 ms   0 ms   0 ms   192.168.1.1 [192.168.1.1]
  3   3 ms   29 ms   4 ms   96.6.27.90 [96.6.27.90]
Trace complete.

Source      DestinationAddress DestinationHost   Replies
------      ------------------ ---------------   -------
SERVER01    96.6.27.90         www.microsoft.com {, , }

Hop ReplyRouterAddress
--- ------------------
  1 192.168.0.3

    Status Address      RoundtripTime Options Buffer
    ------ -------      ------------- ------- ------
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  2 192.168.1.1

    Status Address     RoundtripTime Options Buffer
    ------ -------     ------------- ------- ------
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  3 96.6.27.90

 Status Address    RoundtripTime Options                                   Buffer
 ------ -------    ------------- -------                                   ------
Success 96.6.27.90             3 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             2 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             4 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
```

该 `Test-Connection` 命令使用 **Traceroute** 参数。 结果（是 `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` 对象）将通过管道传递给 `ForEach-Object` cmdlet。 `ForEach-Object` 创建包含的 `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` 对象和后续对象的结构化的输出 `[System.Net.NetworkInformation.PingReply]` 。

## PARAMETERS

### -BufferSize

指定使用此命令发送的缓冲区的大小，以字节为单位。 默认值为 32。

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -Count

指定要发送的回显请求数。 默认值为 4。

```yaml
Type: System.Int32
Parameter Sets: PingCount
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### -Delay

指定两次 ping 操作之间的间隔时间，以秒为单位。

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DontFragment

此参数设置 IP 标头中的 " **不分段** " 标志。 可以将此参数与 **BufferSize** 参数一起使用来测试路径 MTU 大小。 有关路径 MTU 的详细信息，请参阅维基百科中的 [PATH Mtu 发现](https://wikipedia.org/wiki/Path_MTU_Discovery) 文章。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4

强制 cmdlet 使用 IPv4 协议进行测试。

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

### -IPv6

强制 cmdlet 使用 IPv6 协议进行测试。

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

### -MaxHops

设置可发送 ICMP 请求消息的最大跃点数。 默认值由操作系统控制。 Windows 10 的默认值为128跃点。

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ping

使 cmdlet 执行 ping 测试，这是默认操作。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: Ping test
Accept pipeline input: False
Accept wildcard characters: False
```

### -Quiet

**Quiet** 参数返回 **system.object** 对象中的 **布尔** 值。 使用此参数将取消所有错误。

所测试的每个连接都将返回一个 **布尔** 值。 如果 **TargetName** 参数指定了多台计算机，则返回 **布尔** 值的数组。

如果 **任何** ping 成功， `$True` 则返回。

如果 **所有** ping `$False` 操作都失败，则返回。

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

### -ResolveDestination

导致 cmdlet 尝试解析目标的 DNS 名称。

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

### -Source

指定发出 ping 请求的计算机的名称。 请输入以逗号分隔的计算机名称的列表。 默认为本地计算机。

```yaml
Type: System.String
Parameter Sets: PingCount, PingContinues, TraceRoute, ConnectionByTCPPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetName

指定要测试的计算机。 请键入计算机名称或者以 IPv4 或 IPv6 格式键入 IP 地址。 不允许使用通配符。 此参数是必需的。 **ComputerName** 是此参数的别名。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ComputerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TCPPort

指定要在 TCP 连接测试中使用的目标上的 TCP 端口号。 Cmdlet 将尝试与目标上的指定端口建立 TCP 连接。

```yaml
Type: System.Int32
Parameter Sets: ConnectionByTCPPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSeconds

设置测试的超时值。 如果在超时过期之前未收到响应，则测试失败。 默认值为 5 秒。

此参数是在 PowerShell 6.0 中引入的。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5 seconds
Accept pipeline input: False
Accept wildcard characters: False
```

### -Traceroute

导致 cmdlet 执行 traceroute 测试。 使用此参数时，该 cmdlet 将返回一个 `TestConnectionCommand+TraceRouteResult` 对象。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TraceRoute
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -继续

使 cmdlet 持续发送 ping 请求。 此参数不能与 **Count** 参数一起使用。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MTUSizeDetect

此参数用于发现路径 MTU 大小。 Cmdlet 将返回 **PingReply # MTUSize** 对象，其中包含目标的路径 MTU 大小。 有关路径 MTU 的详细信息，请参阅维基百科中的 [PATH Mtu 发现](https://wikipedia.org/wiki/Path_MTU_Discovery) 文章。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetectionOfMTUSize
Aliases:

Required: True
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

### TestConnectionCommand + PingReport、TestConnectionCommand + TraceRouteResult、Boolean、PingReply # MTUSize

如果指定 **Quiet** 参数，则它将返回一个 **布尔** 值。 如果测试了多个连接，则返回 **布尔** 值的数组。 否则， `Test-Connection` 将为每个 ping 返回一个 **TestConnectionCommand + PingReport** 对象。

## 注释

## 相关链接

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
