---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroup
ms.openlocfilehash: 2cd77c2766840527825b0ccf68abaac3c2ea6c16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197406"
---
# Get-LocalGroup

## 摘要
获取本地安全组。

## SYNTAX

### Default（默认值）

```
Get-LocalGroup [[-Name] <String[]>] [<CommonParameters>]
```

### SecurityIdentifier

```
Get-LocalGroup [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## DESCRIPTION
**LocalGroup** cmdlet 将获取安全帐户管理器中的本地安全组。
此 cmdlet 将获取创建的默认内置组和本地安全组。

> [!NOTE]
> LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。

## 示例

### 示例1：获取 Administrators 组

```
PS C:\> Get-LocalGroup -Name "Administrators"
Name           Description
----           -----------
Administrators Administrators have complete and unrestricted access to the computer/domain
```

此命令获取本地管理员组。
该命令显示控制台中组的属性。

## PARAMETERS

### -Name
指定此 cmdlet 获取的安全组的名称数组。
您可以使用通配符。

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SID
指定 (此 cmdlet 获取的安全组的 Sid) 安全 Id 的数组。

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

### SecurityAccountsManager. LocalGroup。
此 cmdlet 将返回本地组。

## 注释

* **PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。 可能的源如下所示：

- Local
- Active Directory
- Azure Active Directory 组
- Microsoft 帐户

只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。 对于早期版本，属性为空白。

## 相关链接

[New-LocalGroup](New-LocalGroup.md)

[Remove-LocalGroup](Remove-LocalGroup.md)

[Rename-LocalGroup](Rename-LocalGroup.md)

[Set-LocalGroup](Set-LocalGroup.md)
