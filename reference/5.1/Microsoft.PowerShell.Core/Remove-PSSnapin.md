---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSnapin
ms.openlocfilehash: e74aff3e52c61f41a54664efbab9c0f195b0d409
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197625"
---
# Remove-PSSnapin

## 摘要
从当前会话中删除 Windows PowerShell 管理单元。

## SYNTAX

```
Remove-PSSnapin [-Name] <String[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Add-pssnapin** cmdlet 将从当前会话中删除 Windows PowerShell 管理单元。
你可以使用它来删除已添加到 Windows PowerShell 的管理单元。无法使用此 cmdlet 删除随 Windows PowerShell 一起安装的管理单元。

从当前会话中删除管理单元后，仍将加载管理单元，但该管理单元中的 cmdlet 和提供程序在该会话中将不再可用。

## 示例

### 示例1：删除管理单元

```
PS C:\> remove-pssnapin -Name Microsoft.Exchange
```

此命令从当前会话中删除 **Microsoft. Exchange** 管理单元。
完成该命令后，该管理单元支持的 cmdlet 和提供程序在该会话中将不可用。

### 示例2：使用管道的名称删除管理单元

```
PS C:\> Get-PSSnapIn smp* | Remove-PSSnapIn
```

此命令从当前会话中删除名称以 smp 开头的 Windows PowerShell 管理单元。

该命令使用 **add-pssnapin** cmdlet 来获取表示管理单元的对象。管道运算符 (|) 将结果发送到 **add-pssnapin** cmdlet，这会将其从会话中删除。
此管理单元支持的 cmdlet 和提供程序在该会话中将不再可用。

当你通过管道将对象传递给 **add-pssnapin** 时，对象的名称将与 *name* 参数关联，该参数将接受具有 **name** 属性的管道中的对象。

### 示例3：使用名称删除管理单元

```
PS C:\> Remove-PSSnapin -Name *event*
```

此命令将删除名称中包含 "event" 的所有 Windows PowerShell 管理单元。

## PARAMETERS

### -Name
指定要从当前会话中删除的 Windows PowerShell 管理单元的名称。
允许使用通配符 (*)。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
返回一个表示管理单元的对象。
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

### System.Management.Automation.PSSnapInInfo
可以通过管道将管理单元对象传递给此 cmdlet。

## 输出

### PSSnapInInfo （无）
如果指定 *PassThru* 参数，则此 cmdlet 将生成表示该管理单元的 **PSSnapInInfo** 对象。
默认情况下， **add-pssnapin** 不会生成任何输出。

## 注释

* **Add-pssnapin** 在从会话中删除管理单元之前，不会检查 Windows PowerShell 的版本。 如果无法删除某个管理单元，则会出现一条警告，并且该命令将失败。
* **Add-pssnapin** 仅影响当前会话。 如果你已将 Add-pssnapin 命令添加到你的 Windows PowerShell 配置文件中，则应删除该命令，以从以后的会话中删除管理单元。 有关说明，请键入 `Get-Help about_Profiles` 。

## 相关链接

[Add-PSSnapin](Add-PSSnapin.md)

[Get-PSSnapin](Get-PSSnapin.md)
