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
# <span data-ttu-id="922c9-103">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="922c9-103">ConvertFrom-Json</span></span>

## <span data-ttu-id="922c9-104">摘要</span><span class="sxs-lookup"><span data-stu-id="922c9-104">SYNOPSIS</span></span>
<span data-ttu-id="922c9-105">将 JSON 格式的字符串转换为自定义对象。</span><span class="sxs-lookup"><span data-stu-id="922c9-105">Converts a JSON-formatted string to a custom object.</span></span>

## <span data-ttu-id="922c9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="922c9-106">SYNTAX</span></span>

```
ConvertFrom-Json [-InputObject] <String> [<CommonParameters>]
```

## <span data-ttu-id="922c9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="922c9-107">DESCRIPTION</span></span>

<span data-ttu-id="922c9-108">`ConvertFrom-Json`Cmdlet 将 JavaScript 对象表示法 (json) 格式的字符串转换为自定义 **PSCustomObject** 对象，该对象具有 JSON 字符串中每个字段的属性。</span><span class="sxs-lookup"><span data-stu-id="922c9-108">The `ConvertFrom-Json` cmdlet converts a JavaScript Object Notation (JSON) formatted string to a custom **PSCustomObject** object that has a property for each field in the JSON string.</span></span> <span data-ttu-id="922c9-109">JSON 通常可供网站使用，以提供对象的文本表示形式。</span><span class="sxs-lookup"><span data-stu-id="922c9-109">JSON is commonly used by web sites to provide a textual representation of objects.</span></span> <span data-ttu-id="922c9-110">JSON 标准不禁止使用 **PSCustomObject** 禁止使用。</span><span class="sxs-lookup"><span data-stu-id="922c9-110">The JSON standard does not prohibit usage that is prohibited with a **PSCustomObject**.</span></span> <span data-ttu-id="922c9-111">例如，如果 JSON 字符串包含重复的键，则此 cmdlet 仅使用最后一个密钥。</span><span class="sxs-lookup"><span data-stu-id="922c9-111">For example, if the JSON string contains duplicate keys, only the last key is used by this cmdlet.</span></span> <span data-ttu-id="922c9-112">请参阅下面的其他示例。</span><span class="sxs-lookup"><span data-stu-id="922c9-112">See other examples below.</span></span>

<span data-ttu-id="922c9-113">若要从任何对象生成 JSON 字符串，请使用 `ConvertTo-Json` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="922c9-113">To generate a JSON string from any object, use the `ConvertTo-Json` cmdlet.</span></span>

<span data-ttu-id="922c9-114">此 cmdlet 是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="922c9-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="922c9-115">此 cmdlet 不支持包含注释的 JSON。</span><span class="sxs-lookup"><span data-stu-id="922c9-115">This cmdlet doesn't support JSON with comments.</span></span>

## <span data-ttu-id="922c9-116">示例</span><span class="sxs-lookup"><span data-stu-id="922c9-116">EXAMPLES</span></span>

### <span data-ttu-id="922c9-117">示例1：将 DateTime 对象转换为 JSON 对象</span><span class="sxs-lookup"><span data-stu-id="922c9-117">Example 1: Convert a DateTime object to a JSON object</span></span>

<span data-ttu-id="922c9-118">此命令使用 `ConvertTo-Json` 和 `ConvertFrom-Json` Cmdlet 将 **DateTime** 对象从 cmdlet 转换为 JSON 对象，然后将其转换 `Get-Date` 为 **PSCustomObject** 。</span><span class="sxs-lookup"><span data-stu-id="922c9-118">This command uses the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert a **DateTime** object from the `Get-Date` cmdlet to a JSON object then to a **PSCustomObject**.</span></span>

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

<span data-ttu-id="922c9-119">该示例使用 `Select-Object` cmdlet 来获取 **DateTime** 对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="922c9-119">The example uses the `Select-Object` cmdlet to get all of the properties of the **DateTime** object.</span></span> <span data-ttu-id="922c9-120">它使用 `ConvertTo-Json` cmdlet 将 **DateTime** 对象转换为设置为 json 对象格式的字符串，并使用 `ConvertFrom-Json` cmdlet 将 JSON 格式的字符串转换为 **PSCustomObject** 对象。</span><span class="sxs-lookup"><span data-stu-id="922c9-120">It uses the `ConvertTo-Json` cmdlet to convert the **DateTime** object to a string formatted as a JSON object and the `ConvertFrom-Json` cmdlet to convert the JSON-formatted string to a **PSCustomObject** object.</span></span>

### <span data-ttu-id="922c9-121">示例2：从 web 服务获取 JSON 字符串，并将其转换为 PowerShell 对象</span><span class="sxs-lookup"><span data-stu-id="922c9-121">Example 2: Get JSON strings from a web service and convert them to PowerShell objects</span></span>

<span data-ttu-id="922c9-122">此命令使用 `Invoke-WebRequest` cmdlet 从 web 服务获取 json 字符串，然后使用 `ConvertFrom-Json` CMDLET 将 json 内容转换为可在 PowerShell 中管理的对象。</span><span class="sxs-lookup"><span data-stu-id="922c9-122">This command uses the `Invoke-WebRequest` cmdlet to get JSON strings from a web service and then it uses the `ConvertFrom-Json` cmdlet to convert JSON content to objects that can be managed in PowerShell.</span></span>

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

<span data-ttu-id="922c9-123">你还可以使用 `Invoke-RestMethod` cmdlet，它会自动将 JSON 内容转换为对象。</span><span class="sxs-lookup"><span data-stu-id="922c9-123">You can also use the `Invoke-RestMethod` cmdlet, which automatically converts JSON content to objects.</span></span>

### <span data-ttu-id="922c9-124">示例3：将 JSON 字符串转换为自定义对象</span><span class="sxs-lookup"><span data-stu-id="922c9-124">Example 3: Convert a JSON string to a custom object</span></span>

<span data-ttu-id="922c9-125">此示例演示如何使用 `ConvertFrom-Json` cmdlet 将 JSON 文件转换为 PowerShell 自定义对象。</span><span class="sxs-lookup"><span data-stu-id="922c9-125">This example shows how to use the `ConvertFrom-Json` cmdlet to convert a JSON file to a PowerShell custom object.</span></span>

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

<span data-ttu-id="922c9-126">该命令使用 Get-Content cmdlet 获取 JSON 文件中的字符串。</span><span class="sxs-lookup"><span data-stu-id="922c9-126">The command uses Get-Content cmdlet to get the strings in a JSON file.</span></span> <span data-ttu-id="922c9-127">然后，它使用管道运算符将分隔的字符串发送到 `ConvertFrom-Json` cmdlet，该 cmdlet 会将其转换为自定义对象。</span><span class="sxs-lookup"><span data-stu-id="922c9-127">Then it uses the pipeline operator to send the delimited string to the `ConvertFrom-Json` cmdlet, which converts it to a custom object.</span></span>

## <span data-ttu-id="922c9-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="922c9-128">PARAMETERS</span></span>

### <span data-ttu-id="922c9-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="922c9-129">-InputObject</span></span>

<span data-ttu-id="922c9-130">指定要转换为 JSON 对象的 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="922c9-130">Specifies the JSON strings to convert to JSON objects.</span></span> <span data-ttu-id="922c9-131">输入一个包含字符串的变量，或键入可获取字符串的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="922c9-131">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="922c9-132">还可以通过管道将字符串传递给 `ConvertFrom-Json` 。</span><span class="sxs-lookup"><span data-stu-id="922c9-132">You can also pipe a string to `ConvertFrom-Json`.</span></span>

<span data-ttu-id="922c9-133">**InputObject** 参数是必需的，但其值可以是空字符串。</span><span class="sxs-lookup"><span data-stu-id="922c9-133">The **InputObject** parameter is required, but its value can be an empty string.</span></span> <span data-ttu-id="922c9-134">当输入对象为空字符串时，不 `ConvertFrom-Json` 会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="922c9-134">When the input object is an empty string, `ConvertFrom-Json` does not generate any output.</span></span> <span data-ttu-id="922c9-135">**InputObject** 值不能为 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="922c9-135">The **InputObject** value cannot be `$null`.</span></span>

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

### <span data-ttu-id="922c9-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="922c9-136">CommonParameters</span></span>

<span data-ttu-id="922c9-137">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="922c9-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="922c9-138">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="922c9-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="922c9-139">输入</span><span class="sxs-lookup"><span data-stu-id="922c9-139">INPUTS</span></span>

### <span data-ttu-id="922c9-140">System.String</span><span class="sxs-lookup"><span data-stu-id="922c9-140">System.String</span></span>

<span data-ttu-id="922c9-141">可以通过管道将 JSON 字符串传递给 `ConvertFrom-Json` 。</span><span class="sxs-lookup"><span data-stu-id="922c9-141">You can pipe a JSON string to `ConvertFrom-Json`.</span></span>

## <span data-ttu-id="922c9-142">输出</span><span class="sxs-lookup"><span data-stu-id="922c9-142">OUTPUTS</span></span>

### <span data-ttu-id="922c9-143">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="922c9-143">PSCustomObject</span></span>

## <span data-ttu-id="922c9-144">注释</span><span class="sxs-lookup"><span data-stu-id="922c9-144">NOTES</span></span>

<span data-ttu-id="922c9-145">`ConvertFrom-Json`Cmdlet 是使用[JavaScriptSerializer 类](/dotnet/api/system.web.script.serialization.javascriptserializer)实现的。</span><span class="sxs-lookup"><span data-stu-id="922c9-145">The `ConvertFrom-Json` cmdlet is implemented using the [JavaScriptSerializer class](/dotnet/api/system.web.script.serialization.javascriptserializer).</span></span>

## <span data-ttu-id="922c9-146">相关链接</span><span class="sxs-lookup"><span data-stu-id="922c9-146">RELATED LINKS</span></span>

<span data-ttu-id="922c9-147">[JavaScript 和 .NET 中的 JavaScript 对象表示法 (JSON) 简介](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="922c9-147">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="922c9-148">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="922c9-148">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="922c9-149">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="922c9-149">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="922c9-150">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="922c9-150">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
