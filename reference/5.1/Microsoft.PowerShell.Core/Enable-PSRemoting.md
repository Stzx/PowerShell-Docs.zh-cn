---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 0c8c386ab376afde3d15fcd29b3f653b3f738f63
ms.sourcegitcommit: 0e0f45d0d8deb8c9088a4f4a32218edde052b686
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "93198940"
---
# Enable-PSRemoting

## 摘要
将计算机配置为接收远程命令。

## SYNTAX

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Enable-PSRemoting`Cmdlet 将计算机配置为接收使用 WS-Management 技术发送的 PowerShell 远程命令。

默认情况下，在 Windows Server 2012 上启用 PowerShell 远程处理。 你可以使用 `Enable-PSRemoting` 在其他受支持的 windows 版本上启用 PowerShell 远程处理，并且在 Windows Server 2012 上重新启用远程处理（如果它已禁用）。

只需在将接收命令的每台计算机上运行一次此命令。 不需要在仅发送命令的计算机上运行它。 由于配置启动侦听器，因此只需在需要的位置运行侦听器。

从 PowerShell 3.0 开始， `Enable-PSRemoting` 当计算机位于公用网络上时，该 cmdlet 可在客户端版本的 Windows 上启用 PowerShell 远程处理。 有关详细信息，请参阅 **SkipNetworkProfileCheck** 参数的说明。

`Enable-PSRemoting`Cmdlet 执行以下操作：

- 运行 [set-wsmanquickconfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) cmdlet，该 cmdlet 将执行以下任务：
  - 启动 WinRM 服务。
  - 将 WinRM 服务上的启动类型设置为自动。
  - 创建一个可接受任何 IP 地址上的请求的侦听器。
  - 启用 WS-Management 通信的防火墙例外。
  - 如果尚未注册，则注册 **Microsoft powershell** 和 **microsoft powershell** 会话配置。
  - 注册64位计算机上的 **microsoft.powershell32** 会话配置（如果尚未注册）。
  - 启用所有会话配置。
  - 将所有会话配置的安全描述符更改为允许远程访问。
- 重新启动 WinRM 服务以使上述更改生效。

若要在 Windows 平台上运行此 cmdlet，请使用 "以管理员身份运行" 选项启动 PowerShell。 此功能不适用于 Linux 或 MacOS 版本的 PowerShell。

> [!CAUTION]
> 在同时具有 PowerShell 3.0 和 PowerShell 2.0 的系统上，不要使用 PowerShell 2.0 来运行 `Enable-PSRemoting` 和 `Disable-PSRemoting` cmdlet。 这些命令可能看起来是成功的，但并未正确配置远程处理。 远程命令和更高版本尝试启用和禁用远程处理可能会失败。

## 示例

### 示例1：将计算机配置为接收远程命令

此命令将计算机配置为接收远程命令。

```powershell
Enable-PSRemoting
```

### 示例2：将计算机配置为在没有确认提示的情况下接收远程命令

此命令将计算机配置为接收远程命令。
**Force** 参数取消用户提示。

```powershell
Enable-PSRemoting -Force
```

### 示例3：允许在客户端上进行远程访问

此示例演示如何允许在客户端版本的 Windows 操作系统上从公共网络进行远程访问。 不同版本的 Windows 的防火墙规则名称可能不同。
使用 `Get-NetFirewallRule` 可查看规则列表。 启用防火墙规则之前，请查看规则中的安全设置，以验证配置是否适合您的环境。

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

默认情况下， `Enable-PSRemoting` 会创建允许从专用网络和域网络进行远程访问的网络规则。 该命令使用 **SkipNetworkProfileCheck** 参数来允许来自相同本地子网中的公用网络的远程访问。 命令指定 **Force** 参数以禁止显示确认消息。

**SkipNetworkProfileCheck** 参数不影响 Windows 操作系统的服务器版本，默认情况下，它允许从同一本地子网中的公共网络进行远程访问。

`Set-NetFirewallRule` **NetSecurity** 模块中的 cmdlet 添加一个防火墙规则，该规则允许从任何远程位置从公用网络进行远程访问。 这包括不同子网中的位置。

> [!NOTE]
> 防火墙规则的名称可能不同，具体取决于 Windows 的版本。 使用 `Get-NetFirewallRule` cmdlet 列出系统上规则的名称。

## PARAMETERS

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

### -Force

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

### -SkipNetworkProfileCheck

指示当计算机位于公用网络上时，此 cmdlet 将在客户端版本的 Windows 操作系统上启用远程处理。 此参数只允许为公用网络启用防火墙规则，该规则只允许远程访问同一本地子网中的计算机。

此参数不会影响 Windows 操作系统的服务器版本，默认情况下，它具有公用网络的本地子网防火墙规则。 如果在服务器版本上禁用了本地子网防火墙规则， `Enable-PSRemoting` 则无论此参数的值是什么，都将其重新启用。

若要删除本地子网限制并从公用网络上的所有位置启用远程访问，请 `Set-NetFirewallRule` 在 **NetSecurity** 模块中使用 cmdlet。

此参数是在 PowerShell 3.0 中引入的。

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

### System.String

此 cmdlet 将返回描述其结果的字符串。

## 注释

在 PowerShell 3.0 中， `Enable-PSRemoting` 为 WS-Management 通信创建以下防火墙例外。

在 Windows 操作系统的服务器版本上， `Enable-PSRemoting` 为允许远程访问的专用和域网络创建防火墙规则，并为公用网络创建防火墙规则，该规则仅允许来自同一本地子网中的计算机的远程访问。

在 Windows 操作系统的客户端版本中， `Enable-PSRemoting` PowerShell 3.0 为允许无限制远程访问的私有和域网络创建防火墙规则。 若要为公用网络创建防火墙规则，以允许来自相同本地子网的远程访问，请使用 **SkipNetworkProfileCheck** 参数。

在 Windows 操作系统的客户端或服务器版本上，若要为公用网络创建防火墙规则，以便删除本地子网限制并允许远程访问，请使用 `Set-NetFirewallRule` NetSecurity 模块中的 cmdlet 来运行以下命令： `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`

在 PowerShell 2.0 中， `Enable-PSRemoting` 为 WS-Management 通信创建以下防火墙例外。

在 Windows 操作系统的服务器版本上，它会为允许远程访问的所有网络创建防火墙规则。

在 Windows 操作系统的客户端版本上， `Enable-PSRemoting` PowerShell 2.0 仅为域和专用网络位置创建防火墙例外。 为了尽量降低安全风险，不 `Enable-PSRemoting` 会在客户端版本的 Windows 上为公用网络创建防火墙规则。 当当前网络位置为 "公共" 时，将 `Enable-PSRemoting` 返回以下消息： "无法检查防火墙的状态"。

从 PowerShell 3.0 开始， `Enable-PSRemoting` 通过将所有会话配置的 " **已启用** " 属性的值设置为来启用所有会话配置 `$True` 。

在 PowerShell 2.0 中， `Enable-PSRemoting` 从会话配置的安全描述符中删除 **Deny_All** 设置。 在 PowerShell 3.0 中， `Enable-PSRemoting` 删除 **Deny_All** 和 **Network_Deny_All** 设置。 这可以远程访问保留供本地使用的会话配置。

## 相关链接

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Disable-PSRemoting](Disable-PSRemoting.md)

[WSMan 提供程序](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Remote](About/about_Remote.md)

[about_Session_Configurations](About/about_Session_Configurations.md)
