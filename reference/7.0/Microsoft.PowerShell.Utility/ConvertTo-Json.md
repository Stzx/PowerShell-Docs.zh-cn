---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: bd68ee4175a5e5a3e3e544e745113255a6f7a865
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93196954"
---
# <span data-ttu-id="ec867-103">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="ec867-103">ConvertTo-Json</span></span>

## <span data-ttu-id="ec867-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ec867-104">SYNOPSIS</span></span>
<span data-ttu-id="ec867-105">将对象转换为 JSON 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="ec867-105">Converts an object to a JSON-formatted string.</span></span>

## <span data-ttu-id="ec867-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ec867-106">SYNTAX</span></span>

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
[-EnumsAsStrings] [-AsArray] [-EscapeHandling <StringEscapeHandling>]
[<CommonParameters>]
```

## <span data-ttu-id="ec867-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ec867-107">DESCRIPTION</span></span>

<span data-ttu-id="ec867-108">`ConvertTo-Json`Cmdlet 将任何 .net 对象转换为 JavaScript 对象表示法 (JSON) 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="ec867-108">The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="ec867-109">这些属性将转换为字段名称，字段名称将转换为属性值，并将删除这些方法。</span><span class="sxs-lookup"><span data-stu-id="ec867-109">The properties are converted to field names, the field values are converted to property values, and the methods are removed.</span></span>

<span data-ttu-id="ec867-110">然后，可以使用 `ConvertFrom-Json` cmdlet 将 json 格式的字符串转换为 json 对象，该对象可在 PowerShell 中轻松管理。</span><span class="sxs-lookup"><span data-stu-id="ec867-110">You can then use the `ConvertFrom-Json` cmdlet to convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell.</span></span>

<span data-ttu-id="ec867-111">许多网站使用 JSON（而不是 XML）来序列化用于在服务器和基于 Web 的应用之间进行通信的数据。</span><span class="sxs-lookup"><span data-stu-id="ec867-111">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="ec867-112">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ec867-112">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="ec867-113">示例</span><span class="sxs-lookup"><span data-stu-id="ec867-113">EXAMPLES</span></span>

### <span data-ttu-id="ec867-114">示例 1</span><span class="sxs-lookup"><span data-stu-id="ec867-114">Example 1</span></span>

```powershell
(Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
  "MinSupportedDateTime": "0001-01-01T00:00:00",
  "MaxSupportedDateTime": "9999-12-31T23:59:59.9999999",
  "AlgorithmType": 1,
  "CalendarType": 1,
  "Eras": [
    1
  ],
  "TwoDigitYearMax": 2029,
  "IsReadOnly": true
}
```

<span data-ttu-id="ec867-115">此命令使用 `ConvertTo-Json` cmdlet 将 GregorianCalendar 对象转换为 JSON 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="ec867-115">This command uses the `ConvertTo-Json` cmdlet to convert a GregorianCalendar object to a JSON-formatted string.</span></span>

### <span data-ttu-id="ec867-116">示例 2</span><span class="sxs-lookup"><span data-stu-id="ec867-116">Example 2</span></span>

```powershell
Get-Date | ConvertTo-Json; Get-Date | ConvertTo-Json -AsArray
```

```Output
{
  "value": "2018-10-12T23:07:18.8450248-05:00",
  "DisplayHint": 2,
  "DateTime": "October 12, 2018 11:07:18 PM"
}
[
  {
    "value": "2018-10-12T23:07:18.8480668-05:00",
    "DisplayHint": 2,
    "DateTime": "October 12, 2018 11:07:18 PM"
  }
]
```

<span data-ttu-id="ec867-117">此示例显示 cmdlet 的输出， `ConvertTo-Json` 以及不带 **AsArray** 开关参数的和。</span><span class="sxs-lookup"><span data-stu-id="ec867-117">This example shows the output from `ConvertTo-Json` cmdlet with and without the **AsArray** switch parameter.</span></span> <span data-ttu-id="ec867-118">您可以看到输出的第二部分包装在数组方括号中。</span><span class="sxs-lookup"><span data-stu-id="ec867-118">You can see the second portion of the output is wrapped in array brackets.</span></span>

### <span data-ttu-id="ec867-119">示例 3</span><span class="sxs-lookup"><span data-stu-id="ec867-119">Example 3</span></span>

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

<span data-ttu-id="ec867-120">此命令显示使用的 **压缩** 参数的效果 `ConvertTo-Json` 。</span><span class="sxs-lookup"><span data-stu-id="ec867-120">This command shows the effect of using the **Compress** parameter of `ConvertTo-Json`.</span></span> <span data-ttu-id="ec867-121">压缩仅影响字符串的外观，而不会影响其有效性。</span><span class="sxs-lookup"><span data-stu-id="ec867-121">The compression affects only the appearance of the string, not its validity.</span></span>

### <span data-ttu-id="ec867-122">示例 4</span><span class="sxs-lookup"><span data-stu-id="ec867-122">Example 4</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
  "DisplayHint": 2,
  "DateTime": "October 12, 2018 10:55:32 PM",
  "Date": "2018-10-12T00:00:00-05:00",
  "Day": 12,
  "DayOfWeek": 5,
  "DayOfYear": 285,
  "Hour": 22,
  "Kind": 2,
  "Millisecond": 639,
  "Minute": 55,
  "Month": 10,
  "Second": 32,
  "Ticks": 636749817326397744,
  "TimeOfDay": {
    "Ticks": 825326397744,
    "Days": 0,
    "Hours": 22,
    "Milliseconds": 639,
    "Minutes": 55,
    "Seconds": 32,
    "TotalDays": 0.95523888627777775,
    "TotalHours": 22.925733270666665,
    "TotalMilliseconds": 82532639.774400011,
    "TotalMinutes": 1375.54399624,
    "TotalSeconds": 82532.6397744
  },
  "Year": 2018
}
```

<span data-ttu-id="ec867-123">此示例使用 `ConvertTo-Json` cmdlet 将 **system.object** 对象从 `Get-Date` cmdlet 转换为 JSON 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="ec867-123">This example uses the `ConvertTo-Json` cmdlet to convert a **System.DateTime** object from the `Get-Date` cmdlet to a JSON-formatted string.</span></span> <span data-ttu-id="ec867-124">该命令使用 `Select-Object` cmdlet 来获取 `*` **DateTime** 对象属性的所有 () 。</span><span class="sxs-lookup"><span data-stu-id="ec867-124">The command uses the `Select-Object` cmdlet to get all (`*`) of the properties of the **DateTime** object.</span></span> <span data-ttu-id="ec867-125">输出显示返回的 JSON 字符串 `ConvertTo-Json` 。</span><span class="sxs-lookup"><span data-stu-id="ec867-125">The output shows the JSON string that `ConvertTo-Json` returned.</span></span>

### <span data-ttu-id="ec867-126">示例 5</span><span class="sxs-lookup"><span data-stu-id="ec867-126">Example 5</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : October 12, 2018 10:55:52 PM
Date        : 2018-10-12 12:00:00 AM
Day         : 12
DayOfWeek   : 5
DayOfYear   : 285
Hour        : 22
Kind        : 2
Millisecond : 768
Minute      : 55
Month       : 10
Second      : 52
Ticks       : 636749817527683372
TimeOfDay   : @{Ticks=825527683372; Days=0; Hours=22; Milliseconds=768; Minutes=55; Seconds=52;
              TotalDays=0.95547185575463; TotalHours=22.9313245381111; TotalMilliseconds=82552768.3372;
              TotalMinutes=1375.87947228667; TotalSeconds=82552.7683372}
Year        : 2018
```

<span data-ttu-id="ec867-127">此示例演示如何使用 `ConvertTo-Json` 和 `ConvertFrom-Json` cmdlet 将对象转换为 json 字符串和 json 对象。</span><span class="sxs-lookup"><span data-stu-id="ec867-127">This example shows how to use the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert an object to a JSON string and a JSON object.</span></span>

## <span data-ttu-id="ec867-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ec867-128">PARAMETERS</span></span>

### <span data-ttu-id="ec867-129">-AsArray</span><span class="sxs-lookup"><span data-stu-id="ec867-129">-AsArray</span></span>

<span data-ttu-id="ec867-130">将对象输出到数组括号中，即使输入是单个对象也是如此。</span><span class="sxs-lookup"><span data-stu-id="ec867-130">Outputs the object in array brackets, even if the input is a single object.</span></span>

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

### <span data-ttu-id="ec867-131">-Compress</span><span class="sxs-lookup"><span data-stu-id="ec867-131">-Compress</span></span>

<span data-ttu-id="ec867-132">省略输出字符串中的空格和缩进格式。</span><span class="sxs-lookup"><span data-stu-id="ec867-132">Omits white space and indented formatting in the output string.</span></span>

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

### <span data-ttu-id="ec867-133">-Depth</span><span class="sxs-lookup"><span data-stu-id="ec867-133">-Depth</span></span>

<span data-ttu-id="ec867-134">指定 JSON 表示形式中包括多少级别的已包含对象。</span><span class="sxs-lookup"><span data-stu-id="ec867-134">Specifies how many levels of contained objects are included in the JSON representation.</span></span> <span data-ttu-id="ec867-135">默认值为 2。</span><span class="sxs-lookup"><span data-stu-id="ec867-135">The default value is 2.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec867-136">-EnumsAsStrings</span><span class="sxs-lookup"><span data-stu-id="ec867-136">-EnumsAsStrings</span></span>

<span data-ttu-id="ec867-137">提供一个替代序列化选项，该选项将所有枚举转换为其字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="ec867-137">Provides an alternative serialization option that converts all enumerations to their string representation.</span></span>

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

### <span data-ttu-id="ec867-138">-EscapeHandling</span><span class="sxs-lookup"><span data-stu-id="ec867-138">-EscapeHandling</span></span>

<span data-ttu-id="ec867-139">控制在生成的 JSON 输出中转义某些字符的方式。</span><span class="sxs-lookup"><span data-stu-id="ec867-139">Controls how certain characters are escaped in the resulting JSON output.</span></span> <span data-ttu-id="ec867-140">默认情况下，只会转义 (如换行符) 的控制字符。</span><span class="sxs-lookup"><span data-stu-id="ec867-140">By default, only control characters (like newline) are escaped.</span></span>

<span data-ttu-id="ec867-141">可接受的值为：</span><span class="sxs-lookup"><span data-stu-id="ec867-141">Acceptable values are:</span></span>

- <span data-ttu-id="ec867-142">仅对默认的控制字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="ec867-142">Default - Only control characters are escaped.</span></span>
- <span data-ttu-id="ec867-143">EscapeNonAscii-所有非 ASCII 和控制字符都将被转义。</span><span class="sxs-lookup"><span data-stu-id="ec867-143">EscapeNonAscii - All non-ASCII and control characters are escaped.</span></span>
- <span data-ttu-id="ec867-144">EscapeHtml- (`<` 、、 `>` 、 `&` `'` 、 `"`) 和控制字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="ec867-144">EscapeHtml - HTML (`<`, `>`, `&`, `'`, `"`) and control characters are escaped.</span></span>

<span data-ttu-id="ec867-145">此参数是在 PowerShell 6.2 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ec867-145">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: Newtonsoft.Json.StringEscapeHandling
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec867-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ec867-146">-InputObject</span></span>

<span data-ttu-id="ec867-147">指定要转换为 JSON 格式的对象。</span><span class="sxs-lookup"><span data-stu-id="ec867-147">Specifies the objects to convert to JSON format.</span></span> <span data-ttu-id="ec867-148">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="ec867-148">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="ec867-149">还可以通过管道将对象传递给 `ConvertTo-Json` 。</span><span class="sxs-lookup"><span data-stu-id="ec867-149">You can also pipe an object to `ConvertTo-Json`.</span></span>

<span data-ttu-id="ec867-150">**InputObject** 参数是必需的，但其值可以为 null (`$null`) 或空字符串。</span><span class="sxs-lookup"><span data-stu-id="ec867-150">The **InputObject** parameter is required, but its value can be null (`$null`) or an empty string.</span></span>
<span data-ttu-id="ec867-151">当输入对象为时 `$null` ，不 `ConvertTo-Json` 会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="ec867-151">When the input object is `$null`, `ConvertTo-Json` does not generate any output.</span></span> <span data-ttu-id="ec867-152">当输入对象是空字符串时，将 `ConvertTo-Json` 返回一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="ec867-152">When the input object is an empty string, `ConvertTo-Json` returns an empty string.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ec867-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ec867-153">CommonParameters</span></span>

<span data-ttu-id="ec867-154">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ec867-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ec867-155">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="ec867-155">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="ec867-156">输入</span><span class="sxs-lookup"><span data-stu-id="ec867-156">INPUTS</span></span>

### <span data-ttu-id="ec867-157">System.Object</span><span class="sxs-lookup"><span data-stu-id="ec867-157">System.Object</span></span>

<span data-ttu-id="ec867-158">可以通过管道将任何对象传递给 `ConvertTo-Json` 。</span><span class="sxs-lookup"><span data-stu-id="ec867-158">You can pipe any object to `ConvertTo-Json`.</span></span>

## <span data-ttu-id="ec867-159">输出</span><span class="sxs-lookup"><span data-stu-id="ec867-159">OUTPUTS</span></span>

### <span data-ttu-id="ec867-160">System.String</span><span class="sxs-lookup"><span data-stu-id="ec867-160">System.String</span></span>

## <span data-ttu-id="ec867-161">注释</span><span class="sxs-lookup"><span data-stu-id="ec867-161">NOTES</span></span>

<span data-ttu-id="ec867-162">`ConvertTo-Json`Cmdlet 是使用[newtonsoft.json Json.NET](https://www.newtonsoft.com/json)实现的。</span><span class="sxs-lookup"><span data-stu-id="ec867-162">The `ConvertTo-Json` cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

## <span data-ttu-id="ec867-163">相关链接</span><span class="sxs-lookup"><span data-stu-id="ec867-163">RELATED LINKS</span></span>

<span data-ttu-id="ec867-164">[JavaScript 和 .NET 中的 JavaScript 对象表示法 (JSON) 简介](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="ec867-164">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="ec867-165">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="ec867-165">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="ec867-166">Get-Content</span><span class="sxs-lookup"><span data-stu-id="ec867-166">Get-Content</span></span>](../Microsoft.PowerShell.Management/Get-Content.md)

[<span data-ttu-id="ec867-167">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="ec867-167">Get-UICulture</span></span>](Get-UICulture.md)

[<span data-ttu-id="ec867-168">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="ec867-168">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="ec867-169">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="ec867-169">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="ec867-170">NewtonSoft.Js。StringEscapeHandling</span><span class="sxs-lookup"><span data-stu-id="ec867-170">NewtonSoft.Json.StringEscapeHandling</span></span>](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)
