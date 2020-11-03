---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroup
ms.openlocfilehash: 6a2f921972fef1794581b301df6e7439e56c7f47
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198099"
---
# Remove-LocalGroup

## 摘要
删除本地安全组。

## SYNTAX

### InputObject

```
Remove-LocalGroup [-InputObject] <LocalGroup[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### 默认

```
Remove-LocalGroup [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SecurityIdentifier

```
Remove-LocalGroup [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**LocalGroup** cmdlet 将删除本地安全组。
此 cmdlet 仅删除本地组。
它不会删除属于该组的用户帐户、计算机帐户或组帐户。
不能恢复已删除的组。

如果删除某个组，然后再创建一个具有相同组名的组，则必须为新组设置新的权限。
新组不会继承分配给组的权限。

> [!NOTE]
> LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。

## 示例

### 示例1：删除安全组

```
PS C:\> Remove-LocalGroup -Name "SecurityGroup04"
```

此命令删除名为 SecurityGroup04 的组。

## PARAMETERS

### -InputObject
指定此 cmdlet 删除的安全组的数组。
若要获取组，请使用 Get-LocalGroup cmdlet。

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
指定此 cmdlet 删除的安全组的名称数组。

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SID
指定此 cmdlet 删除 (安全组的 Sid) 的安全 Id 的数组。

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### SecurityAccountsManager. LocalGroup、SecurityIdentifier 和的数据库的安全层。
可以通过管道将安全组、字符串或 SID 传递给此 cmdlet。

## 输出

### 无
此 cmdlet 将不生成任何输出。

## 注释

* 此 cmdlet 不能删除以下默认组：

- 管理员
- 备份操作员
- Cryptographic Operators
- Distributed COM Users
- 事件日志读者
- 来宾
- Hyper-V 管理员
- IIS_IUSRS
- Network Configuration Operators
- 性能日志用户
- 性能监视器用户
- Power Users
- Remote Desktop Users
- 远程管理用户
- 复制程序
- 用户
- WinRMRemoteWMIUsers__

* **PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。 可能的源如下所示：

- Local
- Active Directory
- Azure Active Directory 组
- Microsoft 帐户

只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。 对于早期版本，属性为空白。

## 相关链接

[Get-LocalGroup](Get-LocalGroup.md)

[New-LocalGroup](New-LocalGroup.md)

[Rename-LocalGroup](Rename-LocalGroup.md)

[Set-LocalGroup](Set-LocalGroup.md)
