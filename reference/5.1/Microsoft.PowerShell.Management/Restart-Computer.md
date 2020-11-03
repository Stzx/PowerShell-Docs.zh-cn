---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 553b61c9669afab325e9feec101d701c2b9a7c83
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93198996"
---
# Restart-Computer

## 摘要
重新启动本地和远程计算机上的操作系统。

## SYNTAX

### DefaultSet (默认值) 

```
Restart-Computer [-DcomAuthentication <AuthenticationLevel>] [-Impersonation <ImpersonationLevel>]
 [-WsmanAuthentication <String>] [-Protocol <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AsJobSet

```
Restart-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>]
 [-Impersonation <ImpersonationLevel>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Force] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Restart-Computer`Cmdlet 将重新启动本地和远程计算机上的操作系统。

您可以使用的参数将 `Restart-Computer` 重新启动操作作为后台作业运行，指定身份验证级别和备用凭据，限制同时运行的操作，并强制立即重新启动。

从 Windows PowerShell 3.0 开始，可以等待重新启动完成，然后再运行下一个命令。 指定等待超时和查询间隔，并等待特定服务在重新启动的计算机上可用。 此功能使 `Restart-Computer` 在脚本和函数中使用成为现实。

您可以使用 WS-Management (WSMan) 协议来重新启动计算机，在这种情况下，分布式组件对象模型 (DCOM) 调用被阻止，如企业防火墙。 有关详细信息，请参阅 [WS-Management 协议](/windows/desktop/WinRM/ws-management-protocol)。

只有在命令中使用了 **AsJob** 参数的情况下，此 cmdlet 才需要使用 Windows PowerShell 远程处理功能。

## 示例

### 示例1：重新启动本地计算机

`Restart-Computer` 重新启动本地计算机。

```powershell
Restart-Computer
```

### 示例2：重新启动多台计算机

`Restart-Computer` 可以重新启动远程和本地计算机。 **ComputerName** 参数接受计算机名称的数组。

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### 示例3：重新启动计算机作为后台作业

这些命令 `Restart-Computer` 在两台远程计算机上将命令作为后台作业运行，然后获取结果。

由于 **AsJob** 在本地计算机上创建作业，并自动将结果返回到本地计算机，因此你可以 `Receive-Job` 将其作为本地命令运行。

```powershell
$Job = Restart-Computer -ComputerName "Server01", "Server02" -AsJob
$Job | Receive-Job
```

`Restart-Computer` 使用 **ComputerName** 参数指定 **Server01** 和 **Server02** 。 **AsJob** 参数将命令作为后台作业运行。 作业对象存储在 `$Job` 变量中。 `$Job` 将管道向下发送到 `Receive-Job` 获取结果的 cmdlet。

### 示例4：重新启动远程计算机

`Restart-Computer` 使用自定义模拟和身份验证设置重新启动远程计算机。

```powershell
Restart-Computer -ComputerName Server01 -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

`Restart-Computer` 使用 **ComputerName** 参数指定 **Server01** 。 **模拟** 参数指定 Anonymous 以隐藏请求者的标识。 **DcomAuthentication** 参数将 PacketIntegrity 指定为连接的身份验证级别。

### 示例5：强制重新启动文本文件中列出的计算机

此示例强制立即重新启动文件中列出的计算机 `Domain01.txt` 。 文本文件中的计算机名称存储在变量中。 **Force** 参数强制立即重新启动，而 **ThrottleLimit** 参数限制并发连接数。

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force -ThrottleLimit 10
```

`Get-Content` 使用 **Path** 参数从文本文件获取计算机名称的列表， **Domain01.txt** 。 计算机名称存储在变量中 `$Names` 。 `Get-Credential` 提示输入用户名和密码，并将值存储在变量中 `$Creds` 。 `Restart-Computer` 将 **ComputerName** 和 **Credential** 参数与其变量一起使用。 **Force** 参数将导致立即重新启动每台计算机。 **ThrottleLimit** 参数将该命令限制为10个并发连接。

### 示例6：重新启动远程计算机并等待 PowerShell

`Restart-Computer` 重新启动远程计算机，然后最多等待5分钟 (300 秒) ，以便 PowerShell 在重新启动的计算机上变为可用状态，然后再继续。

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

`Restart-Computer` 使用 **ComputerName** 参数指定 **Server01** 。 **Wait** 参数等待重新启动完成。 的 **指定 PowerShell** 可以在远程计算机上运行命令。 **Timeout** 参数指定5分钟等待。 **Delay** 参数每两秒钟查询一次远程计算机，以确定它是否已重新启动。

### 示例7：使用 WSMan 协议重新启动计算机

`Restart-Computer` 使用 WSMan 协议而不是默认的 DCOM 来重新启动远程计算机。 Kerberos 身份验证确定当前用户是否有权重新启动远程计算机。

这些设置适用于企业，其中基于 DCOM 的重新启动失败，因为阻止了 DCOM。 例如，使用防火墙。

```powershell
Restart-Computer -ComputerName Server01 -Protocol WSMan -WsmanAuthentication Kerberos
```

`Restart-Computer` 使用 **ComputerName** 参数指定远程计算机 **Server01** 。
**Protocol** 参数指定使用 WSMan 协议。 **WsmanAuthentication** 参数将身份验证方法指定为 **Kerberos** 。

## PARAMETERS

### -AsJob

指示 `Restart-Computer` 作为后台作业运行。

若要使用此参数，必须为本地和远程计算机配置远程处理。 在 Windows Vista 和更高版本的 Windows 操作系统上，必须使用 "以 **管理员身份运行** " 选项打开 PowerShell。 有关详细信息，请参阅 [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)。

指定 AsJob  参数时，该命令立即返回代表后台作业的对象。 当作业完成时，你可以继续在此会话中工作。 作业在本地计算机上创建，并且来自远程计算机的结果将自动返回本地计算机。 若要管理作业，可以使用 **Job** cmdlet。 若要获取作业结果，请使用 `Receive-Job` cmdlet。

有关 Windows PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 和 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

指定一个计算机名称或以逗号分隔的计算机名称数组。 `Restart-Computer` 接受管道或变量中的 **ComputerName** 对象。

键入远程计算机的 NetBIOS 名称、IP 地址或完全限定的域名。 若要指定本地计算机，请键入计算机名、点 `.` 或 localhost。

此参数不依赖于 PowerShell 远程处理。 即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。

如果未指定 **ComputerName** 参数，则 `Restart-Computer` 重新启动本地计算机。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Credential

指定有权执行此操作的用户帐户。 默认为当前用户。

键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。 如果键入用户名，系统会提示输入密码。

凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。

> [!NOTE]
> 有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -DcomAuthentication

指定用于 WMI 连接的身份验证级别。 `Restart-Computer` 使用 WMI。

有效值是：

- **Call** ：调用级 COM 身份验证
- **Connect** ：连接级 COM 身份验证
- **默认** ： Windows 身份验证
- **无** ：无 COM 身份验证
- **Packet** ：数据包级 COM 身份验证。
- **PacketIntegrity** ：数据包完整性级 COM 身份验证
- **PacketPrivacy** ：数据包隐私级 COM 身份验证。
- **保持不变** ：身份验证级别与前一个命令相同。

有关详细信息，请参阅 [AuthenticationLevel 枚举](/dotnet/api/system.management.authenticationlevel)。

此参数是在 Windows PowerShell 3.0 中引入的。

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Delay

指定查询的频率（以秒为单位）。 PowerShell 查询由 **For** 参数指定的服务，以确定该服务是否在计算机重新启动之后可用。

此参数仅适用于 **Wait** **和参数** 。

已在 Windows PowerShell 3.0 中引入了此参数。

如果未指定 **Delay** 参数， `Restart-Computer` 将使用5秒钟的延迟。

```yaml
Type: System.Int16
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -对于

指定 PowerShell 的行为，因为它会等待指定的服务或功能在计算机重新启动后变得可用。 此参数仅对 **Wait** 参数有效。

此参数的可接受值为：

- **默认** ：等待 PowerShell 重新启动。
- **Powershell** ：可在计算机上的 powershell 远程会话中运行命令。
- **WMI** ：接收对计算机 Win32_ComputerSystem 查询的答复。
- **WinRM** ：可以使用 ws-management 建立与计算机的远程会话。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: DefaultSet
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

强制立即重新启动计算机。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Impersonation

指定此 cmdlet 用来调用 WMI 的模拟级别。 `Restart-Computer` 使用 WMI。
此参数的可接受值为：

- **默认值** ：默认模拟。 不管名称如何，这并不是默认值。
- **Anonymous** ：隐藏调用方的标识。
- **标识** ：允许对象查询调用方的凭据。
- **模拟** ：允许对象使用调用方的凭据。

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

指定重新启动计算机要使用的协议。 有效值为 **WSMan** 和 **DCOM** 。

此参数是在 Windows PowerShell 3.0 中引入的。

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

指定为运行此命令可建立的并发连接的最大数目。
节流限制仅适用于当前命令，而不适用于会话或计算机。

如果未指定 **ThrottleLimit** 参数或使用值0，则 `Restart-Computer` 最多使用32并发连接。

```yaml
Type: System.Int32
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeout

指定等待的持续时间，以秒为单位。 超时到期后，将 `Restart-Computer` 返回到命令提示符，即使计算机未重启也是如此。

**Timeout** 参数仅对 **Wait** 参数有效。 **Timeout** 替代 **等待** 参数的无限等待期。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.Int32
Parameter Sets: DefaultSet
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

`Restart-Computer` 取消 PowerShell 提示符并阻止管道，直到计算机重新启动。 您可以在脚本中使用此参数来重新启动计算机，然后在重新启动完成后继续处理。

**等待** 参数会无限期地等待计算机重新启动。 你可以使用 **超时** 调整计时，并使用和 **延迟****参数，以** 等待特定服务在重新启动的计算机上变为可用。

当你重新启动本地计算机时， **等待** 参数无效。 如果 **ComputerName** 参数的值包含远程计算机和本地计算机的名称，则会 `Restart-Computer` 在本地计算机上生成 **等待等待** 的非终止错误，但会等待远程计算机重新启动。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WsmanAuthentication

指定用于对用户的凭据进行身份验证的机制。 已在 Windows PowerShell 3.0 中引入了此参数。

此参数可接受的值为： **Basic** 、 **CredSSP** 、 **Default** 、 **Digest** 、 **Kerberos** 和 **Negotiate** 。

有关详细信息，请参阅 [system.management.automation.runspaces.authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)。

> [!WARNING]
> 凭据安全服务提供程序 (CredSSP) 身份验证，在此身份验证中，用户凭据传递到远程计算机进行身份验证时，需要对多个资源（例如访问远程网络共享）进行身份验证的命令。 此机制增加了远程操作的安全风险。 如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

在运行之前提示你进行确认 `Restart-Computer` 。

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

显示运行时将发生的情况 `Restart-Computer` 。 `Restart-Computer`Cmdlet 不会运行。

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

### System.String

`Restart-Computer` 接受管道或变量中的计算机名称。

在 Windows PowerShell 2.0 中， **ComputerName** 参数仅按属性名称通过管道获取输入。 在 Windows PowerShell 3.0 和更高版本中， **ComputerName** 参数按值从管道中获取输入。

## 输出

### System.management.automation.remotingjob （无）

如果指定 **AsJob** 参数，则 `Restart-Computer` 返回一个作业对象。 否则，不会生成任何输出。

## 注释

- `Restart-Computer` 仅在运行 Windows 的计算机上工作，并且需要 WinRM 和 WMI 关闭系统，包括本地系统。
- `Restart-Computer`使用 Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem)类的[Win32Shutdown 方法](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem)。  此方法需要为用于重新启动计算机的用户帐户启用 **SeShutdownPrivilege** 特权。

在 Windows PowerShell 2.0 中， **AsJob** 参数在重启或停止远程计算机时不能可靠地工作。 在 Windows PowerShell 3.0 中，为解决此问题，该实现方式有所更改。

## 相关链接

[关于 Windows 远程管理](/windows/desktop/WinRM/about-windows-remote-management)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[WS-Management 协议](/windows/desktop/WinRM/ws-management-protocol)
