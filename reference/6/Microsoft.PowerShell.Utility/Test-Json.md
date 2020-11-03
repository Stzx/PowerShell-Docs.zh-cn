---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: 618e00d8db5eadfa8658203ef435a23cfea25be3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198481"
---
# Test-Json

## 摘要
测试字符串是否为有效的 JSON 文档

## SYNTAX

```
Test-Json [-Json] <string> [[-Schema] <string>] [<CommonParameters>]
```

## DESCRIPTION

`Test-Json`Cmdlet 可测试字符串是否为有效的 JavaScript 对象表示法 (JSON) 文档，还可以根据提供的架构（可选）验证 json 文档。

然后，可以将经过验证的字符串与 `ConvertFrom-Json` cmdlet 一起使用，以便将 json 格式的字符串转换为 json 对象，该对象可在 PowerShell 中轻松管理或发送到访问 JSON 输入的其他程序或 web 服务。

许多网站使用 JSON（而不是 XML）来序列化用于在服务器和基于 Web 的应用之间进行通信的数据。

PowerShell 6.1 中引入了此 cmdlet

## 示例

### 示例1：测试对象是否为有效的 JSON

此示例测试输入字符串是否为有效的 JSON 文档。

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### 示例2：根据提供的架构测试对象

此示例使用包含 JSON 架构的字符串，并将其与输入字符串进行比较。

```powershell
$schema = @'
{
  "definitions": {},
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "http://example.com/root.json",
  "type": "object",
  "title": "The Root Schema",
  "required": [
    "name",
    "age"
  ],
  "properties": {
    "name": {
      "$id": "#/properties/name",
      "type": "string",
      "title": "The Name Schema",
      "default": "",
      "examples": [
        "Ashley"
      ],
      "pattern": "^(.*)$"
    },
    "age": {
      "$id": "#/properties/age",
      "type": "integer",
      "title": "The Age Schema",
      "default": 0,
      "examples": [
        25
      ]
    }
  }
}
'@
"{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
```

```Output
Test-Json : IntegerExpected: #/age
At line:1 char:37
+ "{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
+                                     ~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (:) [Test-Json], Exception
+ FullyQualifiedErrorId : InvalidJsonAgainstSchema,Microsoft.PowerShell.Commands.TestJsonCommand
False
```

在此示例中，我们收到一个错误，因为架构需要一个整数作为 **age** ，但我们所测试的 JSON 输入改为使用字符串值。

有关详细信息，请参阅 [JSON 架构](https://json-schema.org/)。

## PARAMETERS

### -Json

指定要测试其有效性的 JSON 字符串。 输入一个包含字符串的变量，或键入可获取字符串的命令或表达式。 还可以通过管道将字符串传递给 `Test-Json` 。

**Json** 参数是必需的。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -架构

指定对 JSON 输入进行验证的架构。 如果通过 `Test-Json` ，将验证 Json 输入是否符合 **Schema** 参数指定的规范，并且 `$True` 仅当输入符合所提供的架构时才返回。

有关详细信息，请参阅 [JSON 架构](https://json-schema.org/)。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.String

可以通过管道将 JSON 字符串传递给 `Test-Json` 。

## 输出

### 布尔

## 注释

`Test-Json`Cmdlet 是使用[NJsonSchema 类](https://github.com/RSuter/NJsonSchema)实现的。

## 相关链接

[JavaScript 和 .NET 中的 JavaScript 对象表示法 (JSON) 简介](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[其他 JSON 架构详细信息](https://json-schema.org/)

[ConvertTo-Json](ConvertTo-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)
