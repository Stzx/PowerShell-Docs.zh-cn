---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Computer
ms.openlocfilehash: c1527c04d795206b8de968daf62456837627a098
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198335"
---
# Add-Computer

## 摘要
将本地计算机添加到域或工作组中。

## SYNTAX

### 域 (默认值) 

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>]
 [-UnjoinDomainCredential <PSCredential>] -Credential <PSCredential> [-DomainName] <String> [-OUPath <String>]
 [-Server <String>] [-Unsecure] [-Options <JoinOptions>] [-Restart] [-PassThru] [-NewName <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### 工作组

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>] [-Credential <PSCredential>]
 [-WorkgroupName] <String> [-Restart] [-PassThru] [-NewName <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Add-Computer`Cmdlet 将本地计算机或远程计算机添加到域或工作组中，或将它们从一个域移到另一个域。
它还为添加到域中的无帐户计算机创建域帐户。

可以使用此 cmdlet 的参数来指定组织单位 (OU) 和域控制器，或执行不安全的加入。

若要获取此命令的结果，请使用 **Verbose** 和 **PassThru** 参数。

## 示例

### 示例1：将本地计算机添加到域中，然后重新启动计算机

```powershell
Add-Computer -DomainName Domain01 -Restart
```

此命令将本地计算机添加到 Domain01 域，然后重新启动计算机以使更改生效。

### 示例2：将本地计算机添加到工作组

```powershell
Add-Computer -WorkgroupName WORKGROUP-A
```

此命令将本地计算机添加到 Workgroup-A 工作组中。

### 示例3：将本地计算机添加到域

```powershell
Add-Computer -DomainName Domain01 -Server Domain01\DC01 -PassThru -Verbose
```

此命令使用 Domain01\DC01 域控制器将本地计算机添加到 Domain01 域中。

该命令使用 **PassThru** 和 **Verbose** 参数来获取有关命令结果的详细信息。

### 示例4：使用 OUPath 参数将本地计算机添加到域

```powershell
Add-Computer -DomainName Domain02 -OUPath "OU=testOU,DC=domain,DC=Domain,DC=com"
```

此命令将本地计算机添加到 Domain02 域中。
它使用 OUPath 参数为新帐户指定组织单位。

### 示例5：使用凭据将本地计算机添加到域

```powershell
Add-Computer -ComputerName Server01 -LocalCredential Server01\Admin01 -DomainName Domain02 -Credential Domain02\Admin02 -Restart -Force
```

此命令将 Server01 计算机添加到 Domain02 域中。
它使用 **LocalCredential** 参数指定有权连接到 Server01 计算机的用户帐户。
它使用 **Credential** 参数指定有权将计算机加入到域中的用户帐户。
它使用 **Restart** 参数在加入操作完成后重新启动计算机，并使用 **Force** 参数取消用户确认消息。

### 示例6：将一组计算机移到新域

```powershell
Add-Computer -ComputerName Server01, Server02, localhost -DomainName Domain02 -LocalCredential Domain01\User01 -UnjoinDomainCredential Domain01\Admin01 -Credential Domain02\Admin01 -Restart
```

此命令将 Server01 和 Server02 计算机以及本地计算机从 Domain01 移至 Domain02。

它使用 **LocalCredential** 参数指定有权连接到这三台受影响的计算机的用户帐户。
它使用 **UnjoinDomainCredential** 参数指定有权将计算机退出 Domain01 域的用户帐户，并使用 **Credential** 参数指定有权将计算机加入到 Domain02 域的用户帐户。
它使用 **Restart** 参数在移动操作完成后重新启动所有三台计算机。

### 示例7：将计算机移到新域并更改计算机的名称

```powershell
Add-Computer -ComputerName Server01 -DomainName Domain02 -NewName Server044 -Credential Domain02\Admin01 -Restart
```

此命令将 Server01 计算机移至 Domain02 并将计算机名称更改为 Server044。

该命令使用当前用户的凭据连接到 Server01 计算机并将其从其当前域中退出。
它使用 **Credential** 参数指定有权将计算机加入到 Domain02 域的用户帐户。

### 示例8：将文件中列出的计算机添加到新域

```powershell
Add-Computer -ComputerName (Get-Content Servers.txt) -DomainName Domain02 -Credential Domain02\Admin02 -Options Win9xUpgrade  -Restart
```

此命令将 Servers.txt 文件中列出的计算机添加到 Domain02 域。
它使用 **Options** 参数来指定 **Win9xUpgrade** 选项。
**Restart** 参数将在加入操作完成后重新启动所有新添加的计算机。

### 示例9：使用预定义的计算机凭据将计算机添加到域

此第一个命令应由管理员从已加入域的计算机运行 `Domain03` ：

```powershell
New-ADComputer -Name "Server02" -AccountPassword (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)

# Then this command is run from `Server02` which is not yet domain-joined:

$joinCred = New-Object pscredential -ArgumentList ([pscustomobject]@{
    UserName = $null
    Password = (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)[0]
})
Add-Computer -Domain "Domain03" -Options UnsecuredJoin,PasswordPass -Credential $joinCred
```

此命令组合使用现有的已加入域的计算机在域中创建一个具有预定义名称和临时联接密码的新计算机帐户。
然后，单独使用具有预定义名称的计算机仅使用计算机名称和临时联接密码加入域。
预定义的密码仅用于支持联接操作，并且在计算机完成联接后被替换为普通计算机帐户过程的一部分。

## PARAMETERS

### -ComputerName

指定要添加到域或工作组中的计算机。
默认为本地计算机。

键入每台远程计算机的 NetBIOS 名称、Internet 协议 (IP) 地址或完全限定的域名。
若要指定本地计算机，请键入该计算机名称、句点 (.) 或“localhost”。

此参数不依赖于 Windows PowerShell 远程处理。
**ComputerName** `Add-Computer` 即使你的计算机未配置为运行远程命令，你也可以使用 ComputerName 参数。

此参数是在 Windows PowerShell 3.0 中引入的。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Credential

指定有权将计算机加入新域的用户帐户。
默认为当前用户。

键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。
如果键入用户名，则将提示你输入密码。

若要指定有权将计算机从其当前域中删除的用户帐户，请使用 **UnjoinDomainCredential** 参数。
若要指定有权连接到远程计算机的用户帐户，请使用 **LocalCredential** 参数。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain, Workgroup
Aliases: DomainCredential

Required: True (Domain), False (Workgroup)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName

指定要向其中添加计算机的域。
在将计算机添加到域时需要使用此参数。

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DN, Domain

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

取消用户确认提示。
如果没有此参数， `Add-Computer` 则要求你确认是否添加了每台计算机。

此参数是在 Windows PowerShell 3.0 中引入的。

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

### -LocalCredential

指定有权连接到由 **ComputerName** 参数指定的计算机的用户帐户。
默认为当前用户。

键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。
如果键入用户名，则将提示你输入密码。

若要指定有权将计算机添加到新域的用户帐户，请使用 **Credential** 参数。
若要指定有权将计算机从其当前域中删除的用户帐户，请使用 **UnjoinDomainCredential** 参数。

此参数是在 Windows PowerShell 3.0 中引入的。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName

在新域中指定计算机的新名称。
此参数仅在一台计算机被添加或移动时有效。

此参数是在 Windows PowerShell 3.0 中引入的。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Options

指定用于 **添加计算机** 加入操作的高级选项。
在逗号分隔的字符串中输入一个或多个值。

此参数的可接受值为：

- **帐户** ：创建域帐户。 将计算机添加到域时， **添加计算机** cmdlet 会自动创建一个域帐户。 提供此选项是为了提供完整性。

- **Win9XUpgrade** ：指示加入操作是 Windows 操作系统升级的一部分。

- **UnsecuredJoin** ：执行不安全的联接。 若要请求不安全的联接，请使用不 *安全* 的参数或此选项。 如果要传递计算机密码，则必须将此选项与选项结合使用 `PasswordPass` 。

- **PasswordPass** ：在执行不安全的联接后，将计算机密码设置为 *Credential* (DomainCredential) 参数的值。 此选项还表示 *Credential* (DomainCredential) 参数的值为计算机密码，而不是用户密码。 仅当指定了选项时，此选项才有效 `UnsecuredJoin` 。 使用此选项时，为参数提供的凭据 `-Credential` *必须* 为 null 用户名。

- **JoinWithNewName** ：将新域中的计算机名称重命名为 *NewName* 参数指定的名称。 在使用 *NewName* 参数时，此选项将自动设置。 此选项设计为与 Rename-Computer cmdlet 一起使用。 如果使用 **重命名计算机** cmdlet 重命名计算机，但不重新启动计算机以使更改生效，则可以使用此参数将计算机加入到具有其新名称的域中。

- **JoinReadOnly** ：使用现有计算机帐户将计算机加入到只读域控制器。 必须将计算机帐户添加到密码复制策略的允许列表中，并且必须在加入操作之前将帐户密码复制到只读域控制器。

- **InstallInvoke** ：设置 **JoinDomainOrWorkgroup** 方法的 **FJoinOptions** 参数的 create (0x2) 并删除 (0x4) 标志。 有关 **JoinDomainOrWorkgroup** 方法的详细信息，请参阅 MSDN library 中的 [Win32_ComputerSystem 类的 JoinDomainOrWorkgroup 方法](https://msdn.microsoft.com/library/aa392154) 。 有关这些选项的详细信息，请参阅 MSDN library 中的 [NetJoinDomain 函数](https://msdn.microsoft.com/library/aa370433) 。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: Microsoft.PowerShell.Commands.JoinOptions
Parameter Sets: Domain
Aliases:
Accepted values: AccountCreate, Win9XUpgrade, UnsecuredJoin, PasswordPass, DeferSPNSet, JoinWithNewName, JoinReadOnly, InstallInvoke

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OUPath

为域帐户指定组织单位 (OU)。
在引号中输入 OU 的完全可分辨名称。
默认值为域中计算机对象的默认 OU。

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: OU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

返回一个代表你所处理的项目的对象。
默认情况下，此 cmdlet 将不产生任何输出。

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

重启已添加到域或工作组中的计算机。
若要更改生效，通常需要重新启动。

此参数是在 Windows PowerShell 3.0 中引入的。

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

### -Server

指定向域中添加计算机的域控制器的名称。
以 DomainName\ComputerName 格式输入该名称。
默认情况下，将不指定域控制器。

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnjoinDomainCredential

指定有权将计算机从其当前域中删除的用户帐户。
默认为当前用户。

键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。
如果键入用户名，则将提示你输入密码。

在将计算机移动到不同的域中时使用此参数。
若要指定有权加入新域的用户帐户，请使用 **Credential** 参数。
若要指定有权连接到远程计算机的用户帐户，请使用 **LocalCredential** 参数。

此参数是在 Windows PowerShell 3.0 中引入的。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -不安全

执行不安全的加入指定域的操作。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkgroupName

指定要将计算机添加到的工作组的名称。
默认值为“WORKGROUP”。

```yaml
Type: System.String
Parameter Sets: Workgroup
Aliases: WGN

Required: True
Position: 0
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

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。

## 输入

### System.String

可以通过管道将计算机名称和新名称传递给 `Add-Computer` Cmdlet。

## 输出

### Microsoft.PowerShell.Commands.ComputerChangeInfo

当使用 **PassThru** 参数时，将 `Add-Computer` 返回 **ComputerChangeInfo** 对象。
否则，此 cmdlet 将不生成任何输出。

## 注释

- 在 Windows PowerShell 2.0 中， **服务器** 参数 `Add-Computer` 失败即使服务器存在也会失败。 在 Windows PowerShell 3.0 中，将更改 **Server** 参数的实现方式，以便它能够稳定运行。

## 相关链接

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Stop-Computer](Stop-Computer.md)

[Test-Connection](Test-Connection.md)
