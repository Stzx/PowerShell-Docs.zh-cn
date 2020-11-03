---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: 79cf0d9a8107cbf843eba5c58e4b4e9ad30ad285
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197368"
---
# <span data-ttu-id="84870-103">Test-Json</span><span class="sxs-lookup"><span data-stu-id="84870-103">Test-Json</span></span>

## <span data-ttu-id="84870-104">摘要</span><span class="sxs-lookup"><span data-stu-id="84870-104">SYNOPSIS</span></span>
<span data-ttu-id="84870-105">测试字符串是否为有效的 JSON 文档</span><span class="sxs-lookup"><span data-stu-id="84870-105">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="84870-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="84870-106">SYNTAX</span></span>

### <span data-ttu-id="84870-107">__AllParameterSets (默认) </span><span class="sxs-lookup"><span data-stu-id="84870-107">__AllParameterSets (Default)</span></span>
```
Test-Json [-Json] <String> [<CommonParameters>]
```

### <span data-ttu-id="84870-108">SchemaString</span><span class="sxs-lookup"><span data-stu-id="84870-108">SchemaString</span></span>
```
Test-Json [-Json] <String> [[-Schema] <String>] [<CommonParameters>]
```

### <span data-ttu-id="84870-109">架构文件</span><span class="sxs-lookup"><span data-stu-id="84870-109">SchemaFile</span></span>
```
Test-Json [-Json] <String> [-SchemaFile <String>] [<CommonParameters>]
```

## <span data-ttu-id="84870-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="84870-110">DESCRIPTION</span></span>

<span data-ttu-id="84870-111">`Test-Json`Cmdlet 可测试字符串是否为有效的 JavaScript 对象表示法 (JSON) 文档，还可以根据提供的架构（可选）验证 json 文档。</span><span class="sxs-lookup"><span data-stu-id="84870-111">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="84870-112">然后，可以将经过验证的字符串与 `ConvertFrom-Json` cmdlet 一起使用，以便将 json 格式的字符串转换为 json 对象，该对象可在 PowerShell 中轻松管理或发送到访问 JSON 输入的其他程序或 web 服务。</span><span class="sxs-lookup"><span data-stu-id="84870-112">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="84870-113">许多网站使用 JSON（而不是 XML）来序列化用于在服务器和基于 Web 的应用之间进行通信的数据。</span><span class="sxs-lookup"><span data-stu-id="84870-113">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="84870-114">PowerShell 6.1 中引入了此 cmdlet</span><span class="sxs-lookup"><span data-stu-id="84870-114">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="84870-115">示例</span><span class="sxs-lookup"><span data-stu-id="84870-115">EXAMPLES</span></span>

### <span data-ttu-id="84870-116">示例1：测试对象是否为有效的 JSON</span><span class="sxs-lookup"><span data-stu-id="84870-116">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="84870-117">此示例测试输入字符串是否为有效的 JSON 文档。</span><span class="sxs-lookup"><span data-stu-id="84870-117">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="84870-118">示例2：根据提供的架构测试对象</span><span class="sxs-lookup"><span data-stu-id="84870-118">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="84870-119">此示例使用包含 JSON 架构的字符串，并将其与输入字符串进行比较。</span><span class="sxs-lookup"><span data-stu-id="84870-119">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

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

<span data-ttu-id="84870-120">在此示例中，我们收到一个错误，因为架构需要一个整数作为 **age** ，但我们所测试的 JSON 输入改为使用字符串值。</span><span class="sxs-lookup"><span data-stu-id="84870-120">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="84870-121">有关详细信息，请参阅 [JSON 架构](https://json-schema.org/)。</span><span class="sxs-lookup"><span data-stu-id="84870-121">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

### <span data-ttu-id="84870-122">示例3：根据文件中的架构测试对象</span><span class="sxs-lookup"><span data-stu-id="84870-122">Example 3: Test an object against a schema from file</span></span>

<span data-ttu-id="84870-123">JSON 架构可以引用使用 `$ref` 关键字的定义。</span><span class="sxs-lookup"><span data-stu-id="84870-123">JSON schema can reference definitions using `$ref` keyword.</span></span> <span data-ttu-id="84870-124">`$ref`可解析为引用另一个文件的 URI。</span><span class="sxs-lookup"><span data-stu-id="84870-124">The `$ref` can resolve to a URI that references another file.</span></span> <span data-ttu-id="84870-125">`SchemaFile`参数接受 json 架构文件的文本路径，并允许针对此类架构验证 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="84870-125">The `SchemaFile` parameter accepts literal path to the JSON schema file and allows JSON files to be validated against such schemas.</span></span>

<span data-ttu-id="84870-126">在此示例中，我们有 `schema.json` 引用的文件 `definitions.json` 。</span><span class="sxs-lookup"><span data-stu-id="84870-126">In this example we have `schema.json` file which references `definitions.json`.</span></span>

```powershell
PS> Get-Content schema.json

{
  "description":"A person",
  "type":"object",
  "properties":{
    "name":{
      "$ref":"definitions.json#/definitions/name"
    },
    "hobbies":{
      "$ref":"definitions.json#/definitions/hobbies"
    }
  }
}

PS> Get-Content definitions.json

{
  "definitions":{
    "name":{
      "type":"string"
    },
    "hobbies":{
      "type":"array",
      "items":{
        "type":"string"
      }
    }
  }
}

'{"name": "James", "hobbies": [".NET", "Blogging"]}' | Test-Json -SchemaFile 'schema.json'
```

```Output
True
```

<span data-ttu-id="84870-127">有关详细信息，请参阅 [构造复杂架构](https://json-schema.org/understanding-json-schema/structuring.html)。</span><span class="sxs-lookup"><span data-stu-id="84870-127">For more information, see [Structuring a complex schema](https://json-schema.org/understanding-json-schema/structuring.html).</span></span>

## <span data-ttu-id="84870-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="84870-128">PARAMETERS</span></span>

### <span data-ttu-id="84870-129">-Json</span><span class="sxs-lookup"><span data-stu-id="84870-129">-Json</span></span>

<span data-ttu-id="84870-130">指定要测试其有效性的 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="84870-130">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="84870-131">输入一个包含字符串的变量，或键入可获取字符串的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="84870-131">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="84870-132">还可以通过管道将字符串传递给 `Test-Json` 。</span><span class="sxs-lookup"><span data-stu-id="84870-132">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="84870-133">**Json** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="84870-133">The **Json** parameter is required.</span></span>

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

### <span data-ttu-id="84870-134">-架构</span><span class="sxs-lookup"><span data-stu-id="84870-134">-Schema</span></span>

<span data-ttu-id="84870-135">指定对 JSON 输入进行验证的架构。</span><span class="sxs-lookup"><span data-stu-id="84870-135">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="84870-136">如果通过 `Test-Json` ，将验证 Json 输入是否符合 **Schema** 参数指定的规范，并且 `$True` 仅当输入符合所提供的架构时才返回。</span><span class="sxs-lookup"><span data-stu-id="84870-136">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="84870-137">有关详细信息，请参阅 [JSON 架构](https://json-schema.org/)。</span><span class="sxs-lookup"><span data-stu-id="84870-137">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: SchemaString
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="84870-138">-架构文件</span><span class="sxs-lookup"><span data-stu-id="84870-138">-SchemaFile</span></span>

<span data-ttu-id="84870-139">指定用于验证 JSON 输入的架构文件。</span><span class="sxs-lookup"><span data-stu-id="84870-139">Specifies a schema file used to validate the JSON input.</span></span> <span data-ttu-id="84870-140">使用时， `Test-Json` `$True` 仅当 JSON 输入符合 **架构文件** 参数指定的文件中定义的架构时才返回。</span><span class="sxs-lookup"><span data-stu-id="84870-140">When used, the `Test-Json` returns `$True` only if the JSON input conforms to the Schema defined in the file specified by the **SchemaFile** parameter.</span></span>

<span data-ttu-id="84870-141">有关详细信息，请参阅 [JSON 架构](https://json-schema.org/)。</span><span class="sxs-lookup"><span data-stu-id="84870-141">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: SchemaFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="84870-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="84870-142">CommonParameters</span></span>

<span data-ttu-id="84870-143">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="84870-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="84870-144">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="84870-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="84870-145">输入</span><span class="sxs-lookup"><span data-stu-id="84870-145">INPUTS</span></span>

### <span data-ttu-id="84870-146">System.String</span><span class="sxs-lookup"><span data-stu-id="84870-146">System.String</span></span>

<span data-ttu-id="84870-147">可以通过管道将 JSON 字符串传递给 `Test-Json` 。</span><span class="sxs-lookup"><span data-stu-id="84870-147">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="84870-148">输出</span><span class="sxs-lookup"><span data-stu-id="84870-148">OUTPUTS</span></span>

### <span data-ttu-id="84870-149">布尔</span><span class="sxs-lookup"><span data-stu-id="84870-149">Boolean</span></span>

## <span data-ttu-id="84870-150">注释</span><span class="sxs-lookup"><span data-stu-id="84870-150">NOTES</span></span>

<span data-ttu-id="84870-151">`Test-Json`Cmdlet 是使用[NJsonSchema 类](https://github.com/RSuter/NJsonSchema)实现的。</span><span class="sxs-lookup"><span data-stu-id="84870-151">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="84870-152">相关链接</span><span class="sxs-lookup"><span data-stu-id="84870-152">RELATED LINKS</span></span>

<span data-ttu-id="84870-153">[JavaScript 和 .NET 中的 JavaScript 对象表示法 (JSON) 简介](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="84870-153">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="84870-154">其他 JSON 架构详细信息</span><span class="sxs-lookup"><span data-stu-id="84870-154">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="84870-155">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="84870-155">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="84870-156">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="84870-156">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="84870-157">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="84870-157">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
