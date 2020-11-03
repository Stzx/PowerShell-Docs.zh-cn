---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroupMember
ms.openlocfilehash: 200368c5d13bd027302ad824533e6c187906ed0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197403"
---
# Get-LocalGroupMember

## 摘要
获取本地组中的成员。

## SYNTAX

### Default（默认值）

```
Get-LocalGroupMember [[-Member] <String>] [-Name] <String> [<CommonParameters>]
```

### 组

```
Get-LocalGroupMember [-Group] <LocalGroup> [[-Member] <String>] [<CommonParameters>]
```

### SecurityIdentifier

```
Get-LocalGroupMember [[-Member] <String>] [-SID] <SecurityIdentifier> [<CommonParameters>]
```

## DESCRIPTION
**LocalGroupMember** cmdlet 将获取本地组中的成员。

> [!NOTE]
> LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。

## 示例

### 示例1：获取 Administrators 组的所有成员

```
PS C:\> Get-LocalGroupMember -Group "Administrators"
ObjectClass Name                    PrincipalSource
----------- ----                    ---------------
User        CONTOSOPC\Administrator Local
User        CONTOSOPC\LocalAdmin    Local
```

此命令将获取本地 Administrators 组的所有成员。

## PARAMETERS

### -Group
指定此 cmdlet 从中获取成员的安全组。

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -成员
指定此 cmdlet 从安全组获取的用户或组。
可以按名称或安全 ID 指定用户或组 (SID) 。
在 S-R-I-S-s 中指定 SID 字符串。
. .
格式表示）。
您可以使用通配符。
如果未指定此参数，则该 cmdlet 将获取组的所有成员。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
指定此 cmdlet 从中获取成员的安全组的名称。

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SID
指定此 cmdlet 从中获取成员的安全组的安全 ID。

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### SecurityAccountsManager. LocalGroup、SecurityIdentifier 和的数据库的安全层。
可以通过管道将本地组、字符串或 SID 传递给此 cmdlet。

## 输出

### SecurityAccountsManager. LocalPrincipal
此 cmdlet 返回本地主体。

## 注释

* **PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。 可能的源如下所示：

- Local
- Active Directory
- Azure Active Directory 组
- Microsoft 帐户

只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。 对于早期版本，属性为空白。

## 相关链接

[Add-LocalGroupMember](Add-LocalGroupMember.md)

[New-LocalGroup](New-LocalGroup.md)

[Remove-LocalGroupMember](Remove-LocalGroupMember.md)
