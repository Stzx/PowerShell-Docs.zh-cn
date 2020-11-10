---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: e1bab9250269dadf0d899f9e172e8a4a8387271d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388121"
---
# ConvertFrom-Json

## 摘要
将 JSON 格式的字符串转换为自定义对象。

## SYNTAX

```
ConvertFrom-Json [-InputObject] <String> [<CommonParameters>]
```

## DESCRIPTION

`ConvertFrom-Json`Cmdlet 将 JavaScript 对象表示法 (json) 格式的字符串转换为自定义 **PSCustomObject** 对象，该对象具有 JSON 字符串中每个字段的属性。 JSON 通常可供网站使用，以提供对象的文本表示形式。 JSON 标准不禁止使用 **PSCustomObject** 禁止使用。 例如，如果 JSON 字符串包含重复的键，则此 cmdlet 仅使用最后一个密钥。 请参阅下面的其他示例。

若要从任何对象生成 JSON 字符串，请使用 `ConvertTo-Json` cmdlet。

此 cmdlet 是在 PowerShell 3.0 中引入的。

> [!NOTE]
> 此 cmdlet 不支持包含注释的 JSON。

## 示例

### 示例1：将 DateTime 对象转换为 JSON 对象

此命令使用 `ConvertTo-Json` 和 `ConvertFrom-Json` Cmdlet 将 **DateTime** 对象从 cmdlet 转换为 JSON 对象，然后将其转换 `Get-Date` 为 **PSCustomObject** 。

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : Friday, January 13, 2012 8:06:31 PM
Date        : 1/13/2012 8:00:00 AM
Day         : 13
DayOfWeek   : 5
DayOfYear   : 13
Hour        : 20
Kind        : 2
Millisecond : 400
Minute      : 6
Month       : 1
Second      : 31
Ticks       : 634620819914009002
TimeOfDay   : @{Ticks=723914009002; Days=0; Hours=20; Milliseconds=400; Minutes=6; Seconds=31; TotalDays=0.83786343634490734; TotalHours=20.108722472277776; TotalMilliseconds=72391400.900200009; TotalMinutes=1206.5233483366667;TotalSeconds=72391.4009002}
Year        : 2012
```

该示例使用 `Select-Object` cmdlet 来获取 **DateTime** 对象的所有属性。 它使用 `ConvertTo-Json` cmdlet 将 **DateTime** 对象转换为设置为 json 对象格式的字符串，并使用 `ConvertFrom-Json` cmdlet 将 JSON 格式的字符串转换为 **PSCustomObject** 对象。

### 示例2：从 web 服务获取 JSON 字符串，并将其转换为 PowerShell 对象

此命令使用 `Invoke-WebRequest` cmdlet 从 web 服务获取 json 字符串，然后使用 `ConvertFrom-Json` CMDLET 将 json 内容转换为可在 PowerShell 中管理的对象。

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

你还可以使用 `Invoke-RestMethod` cmdlet，它会自动将 JSON 内容转换为对象。

### 示例3：将 JSON 字符串转换为自定义对象

此示例演示如何使用 `ConvertFrom-Json` cmdlet 将 JSON 文件转换为 PowerShell 自定义对象。

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

该命令使用 Get-Content cmdlet 获取 JSON 文件中的字符串。 然后，它使用管道运算符将分隔的字符串发送到 `ConvertFrom-Json` cmdlet，该 cmdlet 会将其转换为自定义对象。

## PARAMETERS

### -InputObject

指定要转换为 JSON 对象的 JSON 字符串。 输入一个包含字符串的变量，或键入可获取字符串的命令或表达式。 还可以通过管道将字符串传递给 `ConvertFrom-Json` 。

**InputObject** 参数是必需的，但其值可以是空字符串。 当输入对象为空字符串时，不 `ConvertFrom-Json` 会生成任何输出。 **InputObject** 值不能为 `$null` 。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.String

可以通过管道将 JSON 字符串传递给 `ConvertFrom-Json` 。

## 输出

### PSCustomObject

## 注释

`ConvertFrom-Json`Cmdlet 是使用[JavaScriptSerializer 类](/dotnet/api/system.web.script.serialization.javascriptserializer)实现的。

## 相关链接

[JavaScript 和 .NET 中的 JavaScript 对象表示法 (JSON) 简介](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[ConvertTo-Json](ConvertTo-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)
