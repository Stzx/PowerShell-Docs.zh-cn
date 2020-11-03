---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ControlPanelItem
ms.openlocfilehash: 51bc04b4de901a611330266b6b0f58471f998432
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198299"
---
# Get-ControlPanelItem

## 摘要
获取控制面板项。

## SYNTAX

### RegularName（默认值）

```
Get-ControlPanelItem [[-Name] <String[]>] [-Category <String[]>] [<CommonParameters>]
```

### CanonicalName

```
Get-ControlPanelItem -CanonicalName <String[]> [-Category <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-ControlPanelItem`Cmdlet 将获取本地计算机上的控制面板项。 你可以将其用于按名称、类别或描述查找控制面板项，即使在没有用户界面的系统上也可以如此。

此 cmdlet 仅获取可在系统上打开的控制面板项。 在没有 "控制面板" 或 "文件资源管理器" 的计算机上，此 cmdlet 仅获取可以在不使用这些组件的情况下打开的控制面板项。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。 它仅适用于 Windows 8 和 Windows Server 2012 及更高版本。

## 示例

### 示例 1：获取所有控制面板项

此命令获取本地计算机上的所有控制面板项。

```powershell
Get-ControlPanelItem
```

```Output
Name                          CanonicalName                 Category                      Description
----                          -------------                 --------                      -----------
Action Center                 Microsoft.ActionCenter        {System and Security}         Review recent messages and...
Administrative Tools          Microsoft.AdministrativeTools {System and Security}         Configure administrative s...
AutoPlay                      Microsoft.AutoPlay            {Hardware}                    Change default settings fo...
BitLocker Drive Encryption    Microsoft.BitLockerDriveEn... {System and Security}         Protect your computer usin...
Color Management              Microsoft.ColorManagement     {All Control Panel Items}     Change advanced color mana...
Credential Manager            Microsoft.CredentialManager   {User Accounts}               Manage your Windows Creden...
Date and Time                 Microsoft.DateAndTime         {Clock, Language, and Region} Set the date, time, and ti...
...
```

### 示例 2：按名称获取控制面板项

此示例获取名称中包含程序或应用程序的控制面板项。

```powershell
Get-ControlPanelItem -Name "*Program*", "*App*"
```

### 示例 3：按类别获取控制面板项

此命令获取其名称中具有安全性的类别中的所有控制面板项。

```powershell
Get-ControlPanelItem -Category "*Security*"
```

### 示例 4：打开控制面板项

此示例在本地计算机上打开 "Windows 防火墙" 控制面板项。

```powershell
Get-ControlPanelItem -Name "Windows Firewall" | Show-ControlPanelItem
```

`Get-ControlPanelItem`Cmdlet 将获取控制面板项。 `Show-ControlPanelItem`Cmdlet 将打开它。

### 示例 5：获取远程计算机上的控制面板项

此示例将获取 Server01 远程计算机上的 BitLocker 驱动器加密控制面板项。
`Invoke-Command`Cmdlet 以 `Get-ControlPanelItem` 远程方式运行 cmdlet。

```powershell
Invoke-Command -ComputerName "Server01" {Get-ControlPanelItem -Name "BitLocker*" }
```

### 示例 6：搜索控制面板项的描述

此示例将搜索 "控制面板" 项的 " **说明** " 属性，以仅获取包含名称 **设备** 的那些项。

```powershell
Get-ControlPanelItem | Where-Object {$_.Description -like "*Device*"}
```

```Output
Name                    CanonicalName                 Category    Description
----                    -------------                 --------    -----------
AutoPlay                Microsoft.AutoPlay            {Hardware}  Change default settings fo...
Devices and Printers    Microsoft.DevicesAndPrinters  {Hardware}  View and manage devices, p...
Sound                   Microsoft.Sound               {Hardware}  Configure your audio devic...
```

`Get-ControlPanelItem`Cmdlet 将获取所有控制面板项。 `Where-Object`Cmdlet 按 **Description** 属性的值筛选这些项。

## PARAMETERS

### -CanonicalName

按照此 cmdlet 获取的规范名称或名称模式，将控制面板项指定为字符串数组。 允许使用通配符。 如果输入多个名称，则此 cmdlet 将获取与任何名称匹配的控制面板项，如同名称列表中的项由 "or" 运算符分隔时。

默认情况下，此 cmdlet 将获取系统中的所有控制面板项。

```yaml
Type: System.String[]
Parameter Sets: CanonicalName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Category

指定为字符串数组，此 cmdlet 获取的指定类别中的控制面板项的类别。 输入一个类别名称或名称模式。 允许使用通配符。 如果输入多个名称，则此 cmdlet 将获取与任何名称匹配的控制面板项，如同名称列表中的项由 "or" 运算符分隔时。 默认情况下，此 cmdlet 将获取系统中的所有控制面板项。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

以字符串数组的形式指定此 cmdlet 获取的控制面板的名称或名称模式。
允许使用通配符。 还可以通过管道将名称或名称模式传递给此 cmdlet。

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.String

可以通过管道将名称或名称模式传递给此 cmdlet。

## 输出

### Microsoft.PowerShell.Commands.ControlPanelItem

此 cmdlet 将获取本地计算机上的控制面板项。

## 注释

## 相关链接

[Show-ControlPanelItem](Show-ControlPanelItem.md)
