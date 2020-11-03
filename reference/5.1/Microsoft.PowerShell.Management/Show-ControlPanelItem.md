---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-ControlPanelItem
ms.openlocfilehash: 368e385d51437f9ac93b700c929b185dce30a644
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198031"
---
# Show-ControlPanelItem

## 摘要
打开控制面板项。

## SYNTAX

### RegularName（默认值）

```
Show-ControlPanelItem [-Name] <String[]> [<CommonParameters>]
```

### CanonicalName

```
Show-ControlPanelItem -CanonicalName <String[]> [<CommonParameters>]
```

### Get-controlpanelitem

```
Show-ControlPanelItem [[-InputObject] <ControlPanelItem[]>] [<CommonParameters>]
```

## DESCRIPTION

`Show-ControlPanelItem`Cmdlet 将在本地计算机上打开 "控制面板" 项。 可以使用它按名称、类别或描述打开控制面板项，即使在没有用户界面的系统上也是如此。 你可以通过管道将控制面板项从 `Get-ControlPanelItem` cmdlet 发送到 `Show-ControlPanelItem` 。

`Show-ControlPanelItem` 仅搜索可在系统上打开的控制面板项。 在没有 " **控制面板** " 或 " **文件资源管理器** " 的计算机上， `Show-ControlPanelItem` 只会搜索可在不使用这些组件的情况下打开的控制面板项。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的，适用于 Windows 8、Windows Server 2012 和更高版本。

## 示例

### 示例1：显示控制面板项

此示例启动 " **自动播放** " 控制面板项。

```powershell
Show-ControlPanelItem -Name "AutoPlay"
```

### 示例2：通过管道将控制面板项传递给此 cmdlet

此示例在本地计算机上打开 **Windows Defender 防火墙** 控制面板项。
Windows 防火墙控制面板项的名称在 Windows 版本中已更改。 此示例使用通配符模式查找控制面板项。

```powershell
Get-ControlPanelItem -Name "*Firewall" | Show-ControlPanelItem
```

`Get-ControlPanelItem` 获取控制面板项并将 `Show-ControlPanelItem` 其打开。

### 示例 3：使用文件名打开控制面板项

此示例通过使用 " **程序和功能** " 控制面板项的应用程序名称打开该面板项。

```powershell
appwiz.cpl
```

此方法是使用命令的替代方法 `Show-ControlPanelItem` 。

> [!NOTE]
> 在 PowerShell 中，可以省略控制面板文件的 cpl 文件扩展名，因为它包含在环境变量的值中。 `$env:PathExt`

## PARAMETERS

### -CanonicalName

指定使用指定规范名称或名称模式的控制面板项。 允许使用通配符。 如果输入多个名称，则此 cmdlet 将打开与任何名称匹配的控制面板项，就好像名称列表中的项由 **OR** 运算符分隔时。

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

### -InputObject

通过提交控制面板项对象指定要打开的控制面板项。 输入包含控制面板项对象的变量，或键入获取控制面板项对象的命令或表达式，例如 `Get-ControlPanelItem` 。

```yaml
Type: Microsoft.PowerShell.Commands.ControlPanelItem[]
Parameter Sets: ControlPanelItem
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

指定控制面板项的名称。 允许使用通配符。 如果输入多个名称，则此 cmdlet 将打开与任何名称匹配的控制面板项，就好像名称列表中的项由 **OR** 运算符分隔时。

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.string、Get-controlpanelitem 的。

可以通过管道将名称或控制面板项对象传递给此 cmdlet。

## 输出

### 无

此 cmdlet 不返回任何输出。

## 注释

## 相关链接

[Get-ControlPanelItem](Get-ControlPanelItem.md)
