---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/add-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-LocalGroupMember
ms.openlocfilehash: 06993c8f6618472f4809e37fbf83d298d13ae515
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197412"
---
# Add-LocalGroupMember

## 摘要
向本地组添加成员。

## SYNTAX

### 组

```
Add-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### 默认

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SecurityIdentifier

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Add-LocalGroupMember`Cmdlet 可将用户或组添加到本地安全组。 分配给组的所有权利和权限都会分配给该组的所有成员。

本地计算机上 Administrators 组的成员在该计算机上具有完全控制权限。 限制 Administrators 组中用户数量。

如果计算机已加入某个域，则可以从该域和受信任的域向本地组添加用户帐户、计算机帐户和组帐户。

> [!NOTE]
> 如果计算机已加入域，并且你尝试添加的本地用户与域的某个成员具有相同的名称，则它将添加域成员。

## 示例

### 示例1：向 Administrators 组添加成员

此命令将多个成员添加到本地管理员组。 新成员包括本地用户帐户、Microsoft 帐户、Azure Active Directory 帐户和域组。 此示例在 Outlook.com 处为帐户的用户名使用占位符值。

```powershell
Add-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

## PARAMETERS

### -Group

指定此 cmdlet 向其中添加成员的安全组。

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -成员

指定此 cmdlet 添加到安全组的用户或组的数组。 可以按名称、安全 ID (SID) 或 **LocalPrincipal** 对象指定用户或组。

```yaml
Type: Microsoft.PowerShell.Commands.LocalPrincipal[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

指定此 cmdlet 向其中添加成员的安全组的名称。

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SID

指定此 cmdlet 向其中添加成员的安全组的安全 ID。

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

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

### SecurityAccountsManager. LocalGroup、SecurityIdentifier 和的数据库的安全层。

可以通过管道将本地主体、字符串或 SID 传递给此 cmdlet。

## 输出

### 无

此 cmdlet 将不生成任何输出。

## 注释

LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。

**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。 可能的源如下所示：

- Local
- Active Directory
- Azure Active Directory 组
- Microsoft 帐户

只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。 对于早期版本，属性为空白。

## 相关链接

[Get-LocalGroupMember](Get-LocalGroupMember.md)

[New-LocalGroup](New-LocalGroup.md)

[Remove-LocalGroupMember](Remove-LocalGroupMember.md)
