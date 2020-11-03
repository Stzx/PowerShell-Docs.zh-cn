---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Computer
ms.openlocfilehash: 89e43220a8d5ac675ea232db09cf3edec2ca2b97
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198070"
---
# Remove-Computer

## 摘要
从本机计算机的域中删除本地计算机。

## SYNTAX

### Local（默认值）

```
Remove-Computer [[-UnjoinDomainCredential] <PSCredential>] [-Restart] [-Force] [-PassThru]
 [-WorkgroupName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Remote

```
Remove-Computer -UnjoinDomainCredential <PSCredential> [-LocalCredential <PSCredential>] [-Restart]
 [-ComputerName <String[]>] [-Force] [-PassThru] [-WorkgroupName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Remove-Computer`Cmdlet 从其当前域中删除本地计算机和远程计算机。

从域中删除计算机时，也会 `Remove-Computer` 禁用该计算机的域帐户。 必须提供显式凭据才能从其域中脱离计算机，即使是当前用户的凭据也是如此。 必须重新启动计算机才能使更改生效。 此外，在从域中删除计算机时，你必须将其移出工作组。 使用 **WorkgroupName** 参数来指定工作组。

若要将计算机从工作组移至域，从一个工作组移至另一个工作组或者从一个域移至另一个域，请使用 `Add-Computer` cmdlet。

若要获取此命令的结果，请使用 **Verbose** 和 **PassThru** 参数。 若要取消用户提示，请使用 **Force** 参数。

`Remove-Computer` 从域中删除本地计算机和远程计算机。 它包含以下参数：指定替代凭据的凭据参数，以便连接到远程计算机以及从域中退出； **Restart** 参数，以便重新启动受影响的计算机；以及 **WorkgroupName** 参数，以便指定计算机要添加到的工作组的名称。

## 示例

### 示例1：从其域中删除本地计算机

此示例将从它所加入的域中删除本地计算机。

```powershell
Remove-Computer -UnjoinDomaincredential Domain01\Admin01 -PassThru -Verbose -Restart
```

**UnjoinDomainCredential** 参数提供域管理员的凭据。 **PassThru** 和 **Verbose** 通用参数显示有关命令成功或失败的信息。 **Restart** 参数重新启动计算机以完成删除操作。

如果未指定工作组名称，则会将计算机从其域中删除后移到名为的工作组。

### 示例2：将多台计算机移动到旧工作组

此示例从其域中删除在文件中列出的所有计算机 `OldServers.txt` ，并将它们移到 **旧** 工作组中。

```powershell
Remove-Computer -ComputerName (Get-Content OldServers.txt) -LocalCredential Domain01\Admin01 -UnJoinDomainCredential Domain01\Admin01 -WorkgroupName "Legacy" -Force -Restart
```

**LocalCredential** 参数提供有权连接到远程计算机的用户的凭据。 **UnjoinDomainCredential** 参数提供有权从其域中删除计算机的用户的凭据。 **Force** 参数取消每台计算机的确认提示。 从其域中删除每台计算机后， **Restart** 参数将重新启动每台计算机。

### 示例3：在不确认的情况下从工作组中删除计算机

此示例将从其域中删除远程计算机、Server01 和本地计算机，并将其添加到 **本地** 工作组。

```powershell
Remove-Computer -ComputerName "Server01", "localhost" -UnjoinDomainCredential Domain01\Admin01 -WorkgroupName "Local" -Restart -Force
```

**Force** 参数取消每台计算机的确认提示。 **Restart** 参数重新启动计算机以使更改生效。

## PARAMETERS

### -ComputerName

指定要从其域中删除的计算机。 默认为本地计算机。

键入远程计算机的 FQDN)  (的 NetBIOS 名称、IP 地址或完全限定的域名。 若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。

此参数不依赖于 PowerShell 远程处理。 **ComputerName** `Remove-Computer` 即使你的计算机未配置为运行远程命令，你也可以使用 ComputerName 参数。

此参数是在 PowerShell 3.0 中引入的。

```yaml
Type: System.String[]
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force

取消用户提示。 默认情况下， `Remove-Computer` 会提示你在删除每台计算机前进行确认。

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

### -LocalCredential

指定有权连接到 **ComputerName** 参数指定的计算机的用户帐户。 默认为当前用户。

键入用户名（如 `User01` 或 `Domain01\User01` ），或输入 PSCredential 对象，例如由 cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。 如果键入用户名，该 cmdlet 会提示输入密码。 若要指定有权将计算机从其当前域中删除的用户帐户，请使用 **UnjoinDomainCredential** 参数。

此参数是在 PowerShell 3.0 中引入的。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

返回命令的结果。 否则，此 cmdlet 将不生成任何输出。

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

### -Restart

指示此 cmdlet 重启要删除的计算机。 若要更改生效，通常需要重新启动。

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

### -UnjoinDomainCredential

指定有权将计算机从其当前域中删除的用户帐户。
按照此参数所提供内容，从域中删除远程计算机需要使用显式凭据，即使值为当前用户的凭据也是如此。

键入用户名（如 User01 或 Domain01\User01），或输入 PSCredential 对象，例如生成的一个 **PSCredential** 对象 `Get-Credential` 。 键入用户名时，此 cmdlet 会提示输入密码。

若要指定有权连接到远程计算机的用户帐户，请使用 **LocalCredential** 参数。

此参数是在 PowerShell 3.0 中引入的。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Local, Remote
Aliases: Credential

Required: False (Local), True (Remote)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkgroupName

指定在将计算机从其域中删除后要添加到的工作组的名称。 默认值为 " **WORKGROUP** "。 在从域中删除计算机后，必须将其添加到工作组。

此参数是在 PowerShell 3.0 中引入的。

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

### System.String

可以通过管道将计算机名称传递给 thiscmdlet。

## 输出

### Microsoft.PowerShell.Commands.ComputerChangeInfo

当使用 **PassThru** 参数时，将 `Remove-Computer` 返回 **ComputerChangeInfo** 对象。
否则，此 cmdlet 将不生成任何输出。

## 注释

此 cmdlet 不会从工作组删除计算机。

## 相关链接

[Add-Computer](Add-Computer.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Stop-Computer](Stop-Computer.md)

[Test-Connection](Test-Connection.md)
