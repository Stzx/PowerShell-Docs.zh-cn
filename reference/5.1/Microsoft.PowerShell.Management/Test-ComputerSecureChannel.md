---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-computersecurechannel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ComputerSecureChannel
ms.openlocfilehash: 20ea76e725a8ab53d7090078dc819a6297a639ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198016"
---
# Test-ComputerSecureChannel

## 摘要
测试并修复本地计算机与其域之间的安全通道。

## SYNTAX

```
Test-ComputerSecureChannel [-Repair] [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**Test-ComputerSecureChannel** cmdlet 通过检查本地计算机与其域之间的通道信任关系的状态，来验证通道是否正常工作。
如果连接失败，可以使用 *Repair* 参数尝试还原。

如果通道正常工作，则 **Test-ComputerSecureChannel** 将返回 $True；否则，返回 $False。
此结果使你可以在函数和脚本的条件语句中使用该 cmdlet。
若要获取更详细的测试结果，请使用 *Verbose* 参数。

此 cmdlet 的工作原理与 NetDom.exe 非常类似。
NetDom 和 **test-computersecurechannel** 都使用 **NetLogon** 服务来执行操作。

## 示例

### 示例 1：测试本地计算机与其域之间的通道

```
PS C:\> Test-ComputerSecureChannel
True
```

此命令测试本地计算机与它所加入的域之间的通道。

### 示例 2：测试本地计算机和域控制器之间的通道

```
PS C:\> Test-ComputerSecureChannel -Server "DCName.fabrikam.com"
True
```

此命令指定要进行测试的首选域控制器。

### 示例 3：重置本地计算机与其域之间的通道

```
PS C:\> Test-ComputerSecureChannel -Repair
True
```

此命令重置本地计算机与其域之间的通道。

### 示例 4：显示有关测试的详细信息

```
PS C:\> Test-ComputerSecureChannel -verbose
VERBOSE: Performing operation "Test-ComputerSecureChannel" on Target "SERVER01".
True
VERBOSE: "The secure channel between 'SERVER01' and 'net.fabrikam.com' is alive and working correctly."
```

此命令使用 *Verbose* 通用参数来请求有关操作的详细消息。
有关 Verbose  的详细信息，请参阅 about_CommonParameters。

### 示例 5：运行脚本前测试连接

```
PS C:\> Set-Alias tcsc Test-ComputerSecureChannel
if (!(tcsc))
{Write-Host "Connection failed. Reconnect and retry."}
else { &(.\Get-Servers.ps1) }
```

此示例演示如何使用 **Test-ComputerSecureChannel** 在运行需要连接的脚本之前测试连接。

第一个命令使用 Set-Alias cmdlet 为该 cmdlet 名称创建一个别名。
这可节省空间并避免键入错误。

**If** 语句将在运行脚本前检查 **Test-ComputerSecureChannel** 返回的值。

## PARAMETERS

### -Credential
指定有权执行此操作的用户帐户。
键入用户名，如 User01 或 Domain01\User01；或输入一个 **PSCredential** 对象，如 Get-Credential cmdlet 返回的对象。
默认情况下，该 cmdlet 使用当前用户的凭据。

Credential  参数设计用于使用 Repair  参数来修复计算机与域之间的通道的命令。

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

### -Repair
指示此 cmdlet 删除由 NetLogon 服务建立的通道，然后再重建该通道。
使用此参数可尝试恢复未通过测试的连接。

若要使用此参数，则当前用户必须是本地计算机上管理员组的成员。

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

### -Server
指定要运行该命令的域控制器。
如果未指定此参数，则此 cmdlet 将选择默认域控制器来执行操作。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

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

### System.Boolean
如果连接正常工作，则该 cmdlet 将返回 $True；否则，返回 $False。

## 注释

* 若要在 Windows Vista 以及更高版本的 Windows 操作系统上运行 **Test-ComputerSecureChannel** 命令，请使用“以管理员身份运行”选项打开 Windows PowerShell。
* **Test-ComputerSecureChannel** 通过使用 **I_NetLogonControl2** 函数来实现，该函数可控制 Netlogon 服务的各个方面。

## 相关链接

[Checkpoint-Computer](Checkpoint-Computer.md)

[Reset-ComputerMachinePassword](Reset-ComputerMachinePassword.md)

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
