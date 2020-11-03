---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: 2e3d49700adb8115bf24ae505fbb00c14a774f15
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197276"
---
# <span data-ttu-id="aa892-103">Test-Json</span><span class="sxs-lookup"><span data-stu-id="aa892-103">Test-Json</span></span>

## <span data-ttu-id="aa892-104">摘要</span><span class="sxs-lookup"><span data-stu-id="aa892-104">SYNOPSIS</span></span>
<span data-ttu-id="aa892-105">测试字符串是否为有效的 JSON 文档</span><span class="sxs-lookup"><span data-stu-id="aa892-105">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="aa892-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa892-106">SYNTAX</span></span>

```
Test-Json [-Json] <string> [[-Schema] <string>] [<CommonParameters>]
```

## <span data-ttu-id="aa892-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa892-107">DESCRIPTION</span></span>

<span data-ttu-id="aa892-108">`Test-Json`Cmdlet 可测试字符串是否为有效的 JavaScript 对象表示法 (JSON) 文档，还可以根据提供的架构（可选）验证 json 文档。</span><span class="sxs-lookup"><span data-stu-id="aa892-108">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="aa892-109">然后，可以将经过验证的字符串与 `ConvertFrom-Json` cmdlet 一起使用，以便将 json 格式的字符串转换为 json 对象，该对象可在 PowerShell 中轻松管理或发送到访问 JSON 输入的其他程序或 web 服务。</span><span class="sxs-lookup"><span data-stu-id="aa892-109">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="aa892-110">许多网站使用 JSON（而不是 XML）来序列化用于在服务器和基于 Web 的应用之间进行通信的数据。</span><span class="sxs-lookup"><span data-stu-id="aa892-110">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="aa892-111">PowerShell 6.1 中引入了此 cmdlet</span><span class="sxs-lookup"><span data-stu-id="aa892-111">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="aa892-112">示例</span><span class="sxs-lookup"><span data-stu-id="aa892-112">EXAMPLES</span></span>

### <span data-ttu-id="aa892-113">示例1：测试对象是否为有效的 JSON</span><span class="sxs-lookup"><span data-stu-id="aa892-113">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="aa892-114">此示例测试输入字符串是否为有效的 JSON 文档。</span><span class="sxs-lookup"><span data-stu-id="aa892-114">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="aa892-115">示例2：根据提供的架构测试对象</span><span class="sxs-lookup"><span data-stu-id="aa892-115">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="aa892-116">此示例使用包含 JSON 架构的字符串，并将其与输入字符串进行比较。</span><span class="sxs-lookup"><span data-stu-id="aa892-116">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

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

<span data-ttu-id="aa892-117">在此示例中，我们收到一个错误，因为架构需要一个整数作为 **age** ，但我们所测试的 JSON 输入改为使用字符串值。</span><span class="sxs-lookup"><span data-stu-id="aa892-117">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="aa892-118">有关详细信息，请参阅 [JSON 架构](https://json-schema.org/)。</span><span class="sxs-lookup"><span data-stu-id="aa892-118">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

## <span data-ttu-id="aa892-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa892-119">PARAMETERS</span></span>

### <span data-ttu-id="aa892-120">-Json</span><span class="sxs-lookup"><span data-stu-id="aa892-120">-Json</span></span>

<span data-ttu-id="aa892-121">指定要测试其有效性的 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="aa892-121">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="aa892-122">输入一个包含字符串的变量，或键入可获取字符串的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="aa892-122">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="aa892-123">还可以通过管道将字符串传递给 `Test-Json` 。</span><span class="sxs-lookup"><span data-stu-id="aa892-123">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="aa892-124">**Json** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="aa892-124">The **Json** parameter is required.</span></span>

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

### <span data-ttu-id="aa892-125">-架构</span><span class="sxs-lookup"><span data-stu-id="aa892-125">-Schema</span></span>

<span data-ttu-id="aa892-126">指定对 JSON 输入进行验证的架构。</span><span class="sxs-lookup"><span data-stu-id="aa892-126">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="aa892-127">如果通过 `Test-Json` ，将验证 Json 输入是否符合 **Schema** 参数指定的规范，并且 `$True` 仅当输入符合所提供的架构时才返回。</span><span class="sxs-lookup"><span data-stu-id="aa892-127">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="aa892-128">有关详细信息，请参阅 [JSON 架构](https://json-schema.org/)。</span><span class="sxs-lookup"><span data-stu-id="aa892-128">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

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

### <span data-ttu-id="aa892-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aa892-129">CommonParameters</span></span>

<span data-ttu-id="aa892-130">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="aa892-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa892-131">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="aa892-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aa892-132">输入</span><span class="sxs-lookup"><span data-stu-id="aa892-132">INPUTS</span></span>

### <span data-ttu-id="aa892-133">System.String</span><span class="sxs-lookup"><span data-stu-id="aa892-133">System.String</span></span>

<span data-ttu-id="aa892-134">可以通过管道将 JSON 字符串传递给 `Test-Json` 。</span><span class="sxs-lookup"><span data-stu-id="aa892-134">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="aa892-135">输出</span><span class="sxs-lookup"><span data-stu-id="aa892-135">OUTPUTS</span></span>

### <span data-ttu-id="aa892-136">布尔</span><span class="sxs-lookup"><span data-stu-id="aa892-136">Boolean</span></span>

## <span data-ttu-id="aa892-137">注释</span><span class="sxs-lookup"><span data-stu-id="aa892-137">NOTES</span></span>

<span data-ttu-id="aa892-138">`Test-Json`Cmdlet 是使用[NJsonSchema 类](https://github.com/RSuter/NJsonSchema)实现的。</span><span class="sxs-lookup"><span data-stu-id="aa892-138">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="aa892-139">相关链接</span><span class="sxs-lookup"><span data-stu-id="aa892-139">RELATED LINKS</span></span>

<span data-ttu-id="aa892-140">[JavaScript 和 .NET 中的 JavaScript 对象表示法 (JSON) 简介](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="aa892-140">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="aa892-141">其他 JSON 架构详细信息</span><span class="sxs-lookup"><span data-stu-id="aa892-141">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="aa892-142">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="aa892-142">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="aa892-143">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="aa892-143">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="aa892-144">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="aa892-144">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
