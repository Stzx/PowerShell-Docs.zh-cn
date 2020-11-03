---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalUser
ms.openlocfilehash: 34210145bcddc8d9420552d637a6cd6e5f8e61cc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197402"
---
# Get-LocalUser

## 摘要
获取本地用户帐户。

## SYNTAX

### Default（默认值）

```
Get-LocalUser [[-Name] <String[]>] [<CommonParameters>]
```

### SecurityIdentifier

```
Get-LocalUser [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-LocalUser`Cmdlet 将获取本地用户帐户。 此 cmdlet 将获取默认的内置用户帐户、所创建的本地用户帐户，以及连接到 Microsoft 帐户的本地帐户。

> [!NOTE]
> LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。

## 示例

### 示例1：使用帐户名称获取帐户

此示例将获取名为 AdminContoso02 的用户帐户。

```powershell
Get-LocalUser -Name "AdminContoso02"
```

```Output
Name             Enabled Description
----             ------- -----------
AdminContoso02   True    Description of this account.
```

### 示例2：获取连接到 Microsoft 帐户的帐户

此示例将获取连接到 Microsoft 帐户的用户帐户。 此示例在 Outlook.com 处为帐户的用户名使用占位符值。

```powershell
Get-LocalUser -Name "MicrosoftAccount\username@Outlook.com"
```

```Output
Name                                    Enabled  Description
----                                    -------  -----------
MicrosoftAccount\username@outlook.com  True     Description of this account.
```

### 示例3：获取连接到 Microsoft 帐户的帐户

此示例获取具有指定 SID 的本地用户帐户。

```powershell
Get-LocalUser -SID S-1-5-21-9526073513-1762370368-3942940353-500
```

```Output
Name          Enabled Description
----          ------- -----------
Administrator True    Built-in account for administering the computer/domain
```

## PARAMETERS

### -Name

指定此 cmdlet 获取的用户帐户的名称数组。 您可以使用通配符。

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -SID

指定 (此 cmdlet 获取的用户帐户的 Sid) 安全 Id 的数组。

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.string、SecurityIdentifier。）

可以通过管道将字符串或 SID 传递给此 cmdlet。

## 输出

### SecurityAccountsManager. LocalUser []

此 cmdlet 将返回本地用户帐户。

## 注释

**LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象上的 **PrincipalSource** 属性描述了对象的源。 可能的源如下所示：

- Local
- Active Directory
- Azure Active Directory 组
- Microsoft 帐户

只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。 对于早期版本，属性为空白。

## 相关链接

[Disable-LocalUser](Disable-LocalUser.md)

[Enable-LocalUser](Enable-LocalUser.md)

[New-LocalUser](New-LocalUser.md)

[Remove-LocalUser](Remove-LocalUser.md)

[Rename-LocalUser](Rename-LocalUser.md)

[Set-LocalUser](Set-LocalUser.md)
