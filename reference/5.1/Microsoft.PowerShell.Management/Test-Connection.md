---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: a8d3923db69a20cfada58391944b592cf999e6ef
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198014"
---
# Test-Connection

## 摘要
将 ICMP 回显请求数据包或 ping 发送到一台或多台计算机。

## SYNTAX

### Default（默认值）

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-TimeToLive <Int32>]
 [-Delay <Int32>] [<CommonParameters>]
```

### 源

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Credential <PSCredential>] [-Source] <String[]> [-Impersonation <ImpersonationLevel>]
 [-ThrottleLimit <Int32>] [-TimeToLive <Int32>] [-Delay <Int32>] [<CommonParameters>]
```

### Quiet

```
Test-Connection [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-TimeToLive <Int32>] [-Delay <Int32>] [-Quiet]
 [<CommonParameters>]
```

## DESCRIPTION

`Test-Connection`Cmdlet 将 Internet 控制消息协议 () ICMP 发送到一台或多台远程计算机并返回回显响应回复。 可以使用此 cmdlet 来确定是否可以通过 IP 网络联系特定的计算机。

您可以使用的参数 `Test-Connection` 同时指定发送计算机和接收计算机，将该命令作为后台作业运行，设置超时和 ping 数目，以及配置连接和身份验证。

与熟悉的 **ping** 命令不同， `Test-Connection` 返回可以在 PowerShell 中调查的 **Win32_PingStatus** 对象。 **Quiet** 参数为每个已测试的连接返回 **system.object** 对象中的 **布尔** 值。 如果测试了多个连接，则返回 **布尔** 值的数组。

## 示例

### 示例1：向远程计算机发送回显请求

此示例将来自本地计算机的回显请求数据包发送到 Server01 计算机。

```powershell
Test-Connection -ComputerName Server01
```

```Output
Source        Destination     IPV4Address     IPV6Address  Bytes    Time(ms)
------        -----------     -----------     -----------  -----    --------
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       1
```

`Test-Connection` 使用 **ComputerName** 参数指定 Server01 计算机。

### 示例2：将回显请求发送到多台计算机

此示例将来自本地计算机的 ping 发送到多台远程计算机。

```powershell
Test-Connection -ComputerName Server01, Server02, Server12
```

### 示例3：从多台计算机向计算机发送回显请求

此示例将来自不同源计算机的 ping 发送到一台远程计算机 Server01。

```powershell
Test-Connection -Source Server02, Server12, localhost -ComputerName Server01 -Credential Domain01\Admin01
```

`Test-Connection` 使用 **Credential** 参数指定有权从源计算机发送 ping 请求的用户的凭据。 使用此命令格式可从多个点来测试连接的延迟时间。

### 示例4：使用参数自定义测试命令

此示例使用的参数 `Test-Connection` 自定义命令。 本地计算机将 ping 测试发送到远程计算机。

```powershell
Test-Connection -ComputerName Server01 -Count 3 -Delay 2 -TTL 255 -BufferSize 256 -ThrottleLimit 32
```

`Test-Connection` 使用 **ComputerName** 参数指定 Server01。 **Count** 参数指定三个 ping 发送到 Server01 计算机， **延迟** 为2秒的时间间隔。

当 ping 响应预计需要比平时更长的时间（因为有扩展的跃点数或高流量网络条件）时，可以使用这些选项。

### 示例5：将测试作为后台作业运行

此示例演示如何将 `Test-Connection` 命令作为 PowerShell 后台作业运行。

```powershell
$job = Test-Connection -ComputerName (Get-Content Servers.txt) -AsJob
if ($job.JobStateInfo.State -ne "Running") {$Results = Receive-Job $job}
```

`Test-Connection`命令对企业中的多台计算机执行 ping 操作。 **ComputerName** 参数的值是一个 `Get-Content` 命令，该命令从中读取计算机名称的列表 `Servers.txt file` 。 该命令使用 **AsJob** 参数将命令作为后台作业运行，并将作业保存在 `$job` 变量中。

此 `if` 命令会检查该作业是否仍在运行。 如果该作业未运行， `Receive-Job` 将获取结果并将其存储在 `$Results` 变量中。

### 示例6：使用凭据对远程计算机执行 Ping 操作

此命令使用 `Test-Connection` cmdlet 对远程计算机执行 ping 操作。

```powershell
Test-Connection Server55 -Credential Domain55\User01 -Impersonation Identify
```

该命令使用 **Credential** 参数指定有权对远程计算机执行 ping 操作的用户帐户，以及用于将模拟级别更改为 **标识** 的 **模拟** 参数。

### 示例7：仅在连接测试成功时创建会话

仅当至少一个发送到计算机的 ping 成功时，此示例才会在 Server01 计算机上创建一个会话。

```powershell
if (Test-Connection -ComputerName Server01 -Quiet) {New-PSSession Server01}
```

该 `if` 命令使用 `Test-Connection` Cmdlet 对 Server01 计算机进行 ping 操作。 该命令使用 **Quiet** 参数，该参数将返回一个 **布尔** 值，而不是 **Win32_PingStatus** 的对象。 `$True`如果四个 ping 中有任何 ping 成功，则该值为，否则为 `$False` 。

如果 `Test-Connection` 命令返回的值 `$True` ，则该命令将使用 `New-PSSession` cmdlet 创建 **PSSession** 。

## PARAMETERS

### -AsJob

指示此 cmdlet 作为后台作业运行。

若要使用此参数，必须为本地计算机和远程计算机配置远程处理，并且在 Windows Vista 和更高版本的 Windows 操作系统上，必须使用 "以 **管理员身份运行** " 选项打开 PowerShell。 有关详细信息，请参阅 [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md)。

指定 AsJob  参数时，该命令立即返回代表后台作业的对象。 当作业完成时，你可以继续在此会话中工作。 作业在本地计算机上创建，并且来自远程计算机的结果将自动返回本地计算机。 若要获取作业结果，请使用 `Receive-Job` cmdlet。

有关 PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) 和 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md)。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -BufferSize

指定使用此命令发送的缓冲区的大小，以字节为单位。 默认值为 32。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

指定要对其执行 ping 操作的计算机。 请键入计算机名称或者以 IPv4 或 IPv6 格式键入 IP 地址。 不允许使用通配符。 此参数是必需的。

此参数不依赖于 PowerShell 远程处理。 即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。

> [!NOTE]
> **ComputerName** 参数重命名为 PowerShell 6.0 及更高版本中的 **TargetName** 。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, IPAddress, __SERVER, Server, Destination

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Count

指定要发送的回显请求数。 默认值为 4。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

指定有权从源计算机发送 ping 请求的用户帐户。 键入用户名（如 User01 或 Domain01\User01）或输入 PSCredential 对象，例如来自 cmdlet 的一个 **PSCredential** 对象 `Get-Credential` 。

仅当该命令中使用了 **Source** 参数时， **Credential** 参数才有效。 凭据不会影响目标计算机。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Source
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -DcomAuthentication

指定此 cmdlet 用于 WMI 的身份验证级别。
`Test-Connection` 使用 WMI。
此参数的可接受值为：

- **Default** 。 Windows 身份验证
- **无** 。 无 COM 身份验证
- **连接** 。 连接级 COM 身份验证
- **调用** 。 调用级 COM 身份验证
- **数据包** 。 数据包级 COM 身份验证
- **PacketIntegrity** 。 数据包完整性级 COM 身份验证
- **PacketPrivacy** 。 数据包隐私级 COM 身份验证
- **保持不变** 。 与前一个命令相同

默认值为具有枚举值 **4** 的 **数据包** 。 有关此参数的值的详细信息，请参阅 [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel) 枚举。

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet (enumerated value of 4)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Delay

指定两次 ping 操作之间的间隔时间，以秒为单位。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1 (second)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Impersonation

指定此 cmdlet 调用 WMI 时使用的模拟级别。 `Test-Connection` 使用 WMI。

此参数可接受的值如下所示：

- **Default** 。 默认模拟。
- **匿名** 。 隐藏调用方的身份。
- **确定** 。 允许对象查询调用方的凭据。
- **模拟** 。 允许对象使用调用方的凭据。

默认值为 " **模拟** "。

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

指定协议。 此参数可接受的值为 DCOM 和 WSMan。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Quiet

**Quiet** 参数返回 **system.object** 对象中的 **布尔** 值。 使用此参数将取消所有错误。

所测试的每个连接都将返回一个 **布尔** 值。 如果 **ComputerName** 参数指定了多台计算机，则返回 **布尔** 值的数组。

如果 **任何** ping 成功， `$True` 则返回。

如果 **所有** ping `$False` 操作都失败，则返回。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Quiet
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
Type: System.String[]
Parameter Sets: Source
Aliases: FCN, SRC

Required: True
Position: 1
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

指定为运行此命令可建立的并发连接的最大数目。
如果省略此参数或输入 0 值，则使用默认值 32。

节流限制仅适用于当前命令，而不适用于会话或计算机。

```yaml
Type: System.Int32
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeToLive

指定数据包可被转发的最大次数。 对于网关和路由器等中的每个跃点， **TimeToLive** 值减少1。 如果为0，则丢弃数据包并返回错误。
在 **Windows** 中，默认值为 **128** 。 **TimeToLive** 参数的别名是 **TTL** 。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TTL

Required: False
Position: Named
Default value: 128 in Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### -WsmanAuthentication

指定此 cmdlet 使用 WSMan 协议时用于对用户的凭据进行身份验证的机制。
此参数的可接受值为：

- 基本
- CredSSP
- 默认
- 摘要
- Kerberos
- Negotiate。

默认值为 Default。

有关此参数的值的详细信息，请参阅 [System.management.automation.runspaces.authenticationmechanism 枚举](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0)。

注意：在凭据安全服务提供程序 (CredSSP) 身份验证中，用户凭据传递到远程计算机中以进行验证，这种验证用于要求对多个资源（例如访问远程网络共享）进行验证的命令。
此机制增加了远程操作的安全风险。
如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

不能通过管道将输入传递给此 cmdlet。

## 输出

### System.Management.ManagementObject#root\cimv2\Win32_PingStatus、System.Management.Automation.RemotingJob、System.Boolean

如果指定 **AsJob** 参数，则此 cmdlet 将返回一个作业对象。

如果指定 **Quiet** 参数，则它将返回一个 **布尔** 值。 如果测试了多个连接，则返回 **布尔** 值的数组。 否则， `Test-Connection` 将为每个 ping 返回一个 **Win32_PingStatus** 对象。

## 注释

此 cmdlet 使用 **Win32_PingStatus** 类。 `Get-WMIObject Win32_PingStatus`命令等效于 `Test-Connection` 命令。

在 PowerShell 3.0 中引入了 **Source** 参数集。

## 相关链接

[Add-Computer](Add-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
