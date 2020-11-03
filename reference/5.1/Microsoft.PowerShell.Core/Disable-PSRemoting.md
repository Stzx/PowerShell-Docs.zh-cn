---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 3a281786f99b2a46d0aeb9785480f02b35b2b433
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197456"
---
# Disable-PSRemoting

## 摘要
阻止 PowerShell 终结点接收远程连接。

## SYNTAX

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

该 `Disable-PSRemoting` cmdlet 会阻止远程访问本地计算机上的所有 Windows PowerShell 会话终结点配置。 这包括 PowerShell 6 或更高版本创建的任何终结点。

若要重新启用对所有会话配置的远程访问，请使用 `Enable-PSRemoting` cmdlet。 这包括 PowerShell 6 或更高版本创建的任何终结点。 若要启用对选定会话配置的远程访问，请使用 cmdlet 的 **AccessMode** 参数 `Set-PSSessionConfiguration` 。
你还可以使用 `Enable-PSSessionConfiguration` 和 `Disable-PSSessionConfiguration` cmdlet 来启用和禁用所有用户的会话配置。 有关会话配置的详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md)。

> [!NOTE]
> 即使在运行后 `Disable-PSRemoting` ，仍可在本地计算机上进行环回连接。 环回连接是源自并连接到同一台本地计算机的 PowerShell 远程会话。 来自外部源的远程会话将保持阻止。 对于环回连接，必须使用 **EnableNetworkAccess** 参数的隐式凭据。 有关环回连接的详细信息，请参阅 [新的 PSSession](New-PSSession.md)。

若要运行此 cmdlet，请通过 "以 **管理员身份运行** " 选项启动 Windows PowerShell。

## 示例

### 示例1：阻止对所有会话配置的远程访问

此示例阻止远程访问计算机上的所有 PowerShell 会话终结点配置。

```powershell
Disable-PSRemoting
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### 示例2：在没有确认提示的情况下禁止远程访问所有会话配置

此示例阻止远程访问计算机上的所有 PowerShell 会话终结点配置，而不会提示。

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### 示例3：运行此 cmdlet 的效果

此示例演示如何使用 `Disable-PSRemoting` cmdlet。 若要运行此命令序列，请用 "以 **管理员身份运行** " 选项启动 PowerShell。

禁用会话配置后，该 `New-PSSession` cmdlet 会尝试创建到本地计算机的远程会话 (也称为 "环回" ) 。 由于在本地计算机上禁用远程访问，因此该命令将失败。

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error
 message : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

### 示例4：运行此 cmdlet 和 Enable-PSRemoting 的效果

此示例演示了使用和 cmdlet 对会话配置的影响 `Disable-PSRemoting` `Enable-PSRemoting` 。

`Disable-PSRemoting` 用于禁止远程访问所有 PowerShell 会话终结点配置。 **Force** 参数取消了所有用户提示。 `Get-PSSessionConfiguration`和 `Format-Table` cmdlet 显示计算机上的会话配置。

此输出显示，具有网络令牌的所有远程用户均被拒绝访问终结点配置。 允许本地计算机上的管理员组访问终结点配置，只要它们本地连接 (也称为环回) 并使用隐式凭据。

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow BUILTIN\Administrators AccessAllowed
microsoft.powershell32        BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   BUILTIN\Administrators AccessAllowed
```

`Enable-PSRemoting`Cmdlet 可重新启用对计算机上所有 PowerShell 会话终结点配置的远程访问。 **Force** 参数取消所有用户提示，并在不提示的情况下重新启动 WinRM 服务。 新的输出显示已从所有会话配置中删除 **AccessDenied** 安全描述符。

### 示例5：具有已禁用会话终结点配置的环回连接

此示例演示如何禁用终结点配置，并演示如何成功连接到已禁用的终结点。 `Disable-PSRemoting` 禁用所有 PowerShell 会话终结点配置。

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message : Access is
denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [New-PSSession], PSRemotin
   gTransportException
    + FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed

```

```powershell
New-PSSession -ComputerName localhost -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

第一次使用 `New-PSSession` 尝试创建到本地计算机的远程会话。 这种类型的连接会通过网络堆栈，并且不是环回。 因此，尝试连接到已禁用的终结点失败，并出现 " **拒绝访问** " 错误。

第二次使用时， `New-PSSession` 也会尝试创建到本地计算机的远程会话。
在这种情况下，它会成功，因为它是绕过网络堆栈的环回连接。

当满足以下条件时，将创建环回连接：

- 要连接到的计算机名称为 "localhost"。
- 未传入凭据。 当前登录的用户 (用于连接的隐式凭据) 。
- 使用 **EnableNetworkAccess** 开关参数。

有关环回连接的详细信息，请参阅 [新的 PSSession](New-PSSession.md) 文档。

### 示例6：阻止远程访问具有自定义安全描述符的会话配置

此示例演示 `Disable-PSRemoting` cmdlet 禁用对所有会话配置的远程访问，包括具有自定义安全描述符的会话配置。

`Register-PSSessionConfiguration` 创建 **测试** 会话配置。 **FilePath** 参数指定自定义会话的会话配置文件。 **ShowSecurityDescriptorUI** 参数显示为会话配置设置权限的对话框。 在 "权限" 对话框中，为指定的用户创建自定义的完全访问权限。

`Get-PSSessionConfiguration`和 `Format-Table` cmdlet 显示会话配置及其属性。 此输出显示 **测试** 会话配置允许所指示的用户的交互式访问和特殊权限。

`Disable-PSRemoting` 禁用对所有会话配置的远程访问。

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
DOMAIN01\User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\NETWORK AccessDenied, NTAUTHORITY\INTERACTIVE AccessAllowed,
BUILTIN\Administrators AccessAllowed, DOMAIN01\User01 AccessAllowed


[Server01] Connecting to remote server failed with the following error message : Access is denied. For more information, see the about_Rem
ote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

现在 `Get-PSSessionConfiguration` ，和 `Format-Table` cmdlet 显示将所有网络用户的 **AccessDenied** 安全描述符添加到所有会话配置，包括 **测试** 会话配置。 尽管其他安全描述符不会更改，但 "network_deny_all" 安全描述符优先。 尝试使用 `New-PSSession` 连接到 **测试** 会话配置时，将对此进行说明。

### 示例7：重新启用对选定会话配置的远程访问

此示例演示如何重新启用仅到选定会话配置的远程访问。 禁用所有会话配置后，将重新启用特定会话。

`Set-PSSessionConfiguration`Cmdlet 用于更改 **microsoft。ServerManager** 会话配置。 如果 **AccessMode** 参数的值为 **remote** ，则启用对配置的远程访问。

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name Microsoft.ServerManager -AccessMode Remote -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
```

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

### -WhatIf

显示运行该 cmdlet 时会发生什么情况。 此 cmdlet 未运行。

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

不能通过管道将任何对象传递给此 cmdlet。

## 输出

### 无

此 cmdlet 将不生成任何输出。

## 注释

- 禁用会话配置不会撤消由或 cmdlet 进行的所有更改 `Enable-PSRemoting` `Enable-PSSessionConfiguration` 。 你可能需要手动撤消以下更改。

  1. 停止并禁用 WinRM 服务。
  2. 删除接受任何 IP 地址上的请求的侦听器。
  3. 禁用 WS-Management 通信的防火墙例外。
  4. 将 LocalAccountTokenFilterPolicy 的值还原为 0，这将限制对计算机上 Administrators 组成员的远程访问。

  会话配置是一组定义会话环境的设置。 连接到计算机的每个会话都必须使用一个在该计算机上注册的会话配置。 通过拒绝对所有会话配置的远程访问，你可以有效地阻止远程用户建立连接到计算机的会话。

  在 Windows PowerShell 2.0 中， `Disable-PSRemoting` 将 Deny_All 条目添加到所有会话配置的安全描述符中。 此设置可阻止所有用户创建到本地计算机的用户托管会话。 在 Windows PowerShell 3.0 中， `Disable-PSRemoting` 将 Network_Deny_All 条目添加到所有会话配置的安全描述符中。 此设置可阻止其他计算机上的用户在本地计算机上创建用户管理的会话，但允许本地计算机的用户创建用户托管环回会话。

  在 Windows PowerShell 2.0 中， `Disable-PSRemoting` 是的等效项 `Disable-PSSessionConfiguration -Name *` 。 在 Windows PowerShell 3.0 及更高版本中， `Disable-PSRemoting` 相当于 `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`

## 相关链接

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSRemoting](Enable-PSRemoting.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[WSMan 提供程序](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
