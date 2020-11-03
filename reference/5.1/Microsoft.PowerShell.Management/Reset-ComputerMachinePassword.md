---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/reset-computermachinepassword?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ComputerMachinePassword
ms.openlocfilehash: 1484bc83b9503ce43420b833a1b78b3c4215d98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198052"
---
# Reset-ComputerMachinePassword

## 摘要
重置计算机的计算机帐户密码。

## SYNTAX

```
Reset-ComputerMachinePassword [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**Reset-computermachinepassword** cmdlet 将更改计算机用于向域中的域控制器进行身份验证的计算机帐户密码。
你可以使用它重置本地计算机的密码。

## 示例

### 示例1：重置本地计算机的密码

```
PS C:\> Reset-ComputerMachinePassword
```

此命令重置本地计算机的计算机密码。
该命令使用当前用户的凭据运行。

### 示例2：使用指定的域控制器重置本地计算机的密码

```
PS C:\> Reset-ComputerMachinePassword -Server "DC01" -Credential Domain01\Admin01
```

此命令使用 DC01 域控制器重置本地计算机的计算机密码。
它使用 *Credential* 参数指定有权在域中重置计算机密码的用户帐户。

### 示例3：重置远程计算机上的密码

```
$cred = Get-Credential
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Reset-ComputerMachinePassword -Credential $using:cred}
```

此命令使用 Invoke-Command cmdlet 在 Server01 远程计算机上运行 **reset-computermachinepassword** 命令。

有关 Windows PowerShell 中远程命令的详细信息，请参阅 about_Remote 和 **调用-命令** 。

## PARAMETERS

### -Credential
指定有权执行此操作的用户帐户。
默认为当前用户。

键入用户名（如 User01 或 Domain01\User01）或输入 PSCredential 对象，例如 Get-Credential cmdlet 生成的一个 **PSCredential** 对象。
键入用户名时，此 cmdlet 会提示输入密码。

已在 Windows PowerShell 3.0 中引入了此参数。

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

### -Server
指定此 cmdlet 设置计算机帐户密码时使用的域控制器的名称。

此参数是可选的。
如果省略此参数，则将选择域控制器来处理该命令。

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

### 无
此 cmdlet 将不生成任何输出。

## 注释

## 相关链接

## 相关链接
