---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: 9831249a9f1ffcc65fc275e44da04fde9348ae71
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388053"
---
# <span data-ttu-id="17f6b-103">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="17f6b-103">ConvertTo-Json</span></span>

## <span data-ttu-id="17f6b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="17f6b-104">SYNOPSIS</span></span>
<span data-ttu-id="17f6b-105">将对象转换为 JSON 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="17f6b-105">Converts an object to a JSON-formatted string.</span></span>

## <span data-ttu-id="17f6b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="17f6b-106">SYNTAX</span></span>

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
 [<CommonParameters>]
```

## <span data-ttu-id="17f6b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="17f6b-107">DESCRIPTION</span></span>

<span data-ttu-id="17f6b-108">`ConvertTo-Json`Cmdlet 将任何 .net 对象转换为 JavaScript 对象表示法 (JSON) 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="17f6b-108">The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="17f6b-109">这些属性将转换为字段名称，字段名称将转换为属性值，并将删除这些方法。</span><span class="sxs-lookup"><span data-stu-id="17f6b-109">The properties are converted to field names, the field values are converted to property values, and the methods are removed.</span></span>

<span data-ttu-id="17f6b-110">然后，可以使用 `ConvertFrom-Json` cmdlet 将 json 格式的字符串转换为 json 对象，该对象可在 PowerShell 中轻松管理。</span><span class="sxs-lookup"><span data-stu-id="17f6b-110">You can then use the `ConvertFrom-Json` cmdlet to convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell.</span></span>

<span data-ttu-id="17f6b-111">许多网站使用 JSON（而不是 XML）来序列化用于在服务器和基于 Web 的应用之间进行通信的数据。</span><span class="sxs-lookup"><span data-stu-id="17f6b-111">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="17f6b-112">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="17f6b-112">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="17f6b-113">示例</span><span class="sxs-lookup"><span data-stu-id="17f6b-113">EXAMPLES</span></span>

### <span data-ttu-id="17f6b-114">示例 1</span><span class="sxs-lookup"><span data-stu-id="17f6b-114">Example 1</span></span>

```powershell
(Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
    "MinSupportedDateTime":  "\/Date(-62135596800000)\/",
    "MaxSupportedDateTime":  "\/Date(253402300799999)\/",
    "AlgorithmType":  1,
    "CalendarType":  1,
    "Eras":  [
                 1
             ],
    "TwoDigitYearMax":  2029,
    "IsReadOnly":  false
}
```

<span data-ttu-id="17f6b-115">此命令使用 `ConvertTo-Json` cmdlet 将 GregorianCalendar 对象转换为 JSON 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="17f6b-115">This command uses the `ConvertTo-Json` cmdlet to convert a GregorianCalendar object to a JSON-formatted string.</span></span>

### <span data-ttu-id="17f6b-116">示例 2</span><span class="sxs-lookup"><span data-stu-id="17f6b-116">Example 2</span></span>

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

<span data-ttu-id="17f6b-117">此命令显示使用的 **压缩** 参数的效果 `ConvertTo-Json` 。</span><span class="sxs-lookup"><span data-stu-id="17f6b-117">This command shows the effect of using the **Compress** parameter of `ConvertTo-Json`.</span></span> <span data-ttu-id="17f6b-118">压缩仅影响字符串的外观，而不会影响其有效性。</span><span class="sxs-lookup"><span data-stu-id="17f6b-118">The compression affects only the appearance of the string, not its validity.</span></span>

### <span data-ttu-id="17f6b-119">示例 3</span><span class="sxs-lookup"><span data-stu-id="17f6b-119">Example 3</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
    "DisplayHint":  2,
    "DateTime":  "Friday, January 13, 2012 8:06:16 PM",
    "Date":  "\/Date(1326441600000)\/",
    "Day":  13,
    "DayOfWeek":  5,
    "DayOfYear":  13,
    "Hour":  20,
    "Kind":  2,
    "Millisecond":  221,
    "Minute":  6,
    "Month":  1,
    "Second":  16,
    "Ticks":  634620819762218083,
    "TimeOfDay":  {
                      "Ticks":  723762218083,
                      "Days":  0,
                      "Hours":  20,
                      "Milliseconds":  221,
                      "Minutes":  6,
                      "Seconds":  16,
                      "TotalDays":  0.83768775241087956,
                      "TotalHours":  20.104506057861109,
                      "TotalMilliseconds":  72376221.8083,
                      "TotalMinutes":  1206.2703634716668,
                      "TotalSeconds":  72376.22180829999
                  },
    "Year":  2012
}
```

<span data-ttu-id="17f6b-120">此示例使用 `ConvertTo-Json` cmdlet 将 **system.object** 对象从 `Get-Date` cmdlet 转换为 JSON 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="17f6b-120">This example uses the `ConvertTo-Json` cmdlet to convert a **System.DateTime** object from the `Get-Date` cmdlet to a JSON-formatted string.</span></span> <span data-ttu-id="17f6b-121">该命令使用 `Select-Object` cmdlet 来获取 `*` **DateTime** 对象属性的所有 () 。</span><span class="sxs-lookup"><span data-stu-id="17f6b-121">The command uses the `Select-Object` cmdlet to get all (`*`) of the properties of the **DateTime** object.</span></span> <span data-ttu-id="17f6b-122">输出显示返回的 JSON 字符串 `ConvertTo-Json` 。</span><span class="sxs-lookup"><span data-stu-id="17f6b-122">The output shows the JSON string that `ConvertTo-Json` returned.</span></span>

### <span data-ttu-id="17f6b-123">示例 4</span><span class="sxs-lookup"><span data-stu-id="17f6b-123">Example 4</span></span>

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

<span data-ttu-id="17f6b-124">此示例演示如何使用 `ConvertTo-Json` 和 `ConvertFrom-Json` cmdlet 将对象转换为 json 字符串和 json 对象。</span><span class="sxs-lookup"><span data-stu-id="17f6b-124">This example shows how to use the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert an object to a JSON string and a JSON object.</span></span>

## <span data-ttu-id="17f6b-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="17f6b-125">PARAMETERS</span></span>

### <span data-ttu-id="17f6b-126">-Compress</span><span class="sxs-lookup"><span data-stu-id="17f6b-126">-Compress</span></span>

<span data-ttu-id="17f6b-127">省略输出字符串中的空格和缩进格式。</span><span class="sxs-lookup"><span data-stu-id="17f6b-127">Omits white space and indented formatting in the output string.</span></span>

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

### <span data-ttu-id="17f6b-128">-Depth</span><span class="sxs-lookup"><span data-stu-id="17f6b-128">-Depth</span></span>

<span data-ttu-id="17f6b-129">指定 JSON 表示形式中包括多少级别的已包含对象。</span><span class="sxs-lookup"><span data-stu-id="17f6b-129">Specifies how many levels of contained objects are included in the JSON representation.</span></span> <span data-ttu-id="17f6b-130">默认值为 2。</span><span class="sxs-lookup"><span data-stu-id="17f6b-130">The default value is 2.</span></span>

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

### <span data-ttu-id="17f6b-131">-InputObject</span><span class="sxs-lookup"><span data-stu-id="17f6b-131">-InputObject</span></span>

<span data-ttu-id="17f6b-132">指定要转换为 JSON 格式的对象。</span><span class="sxs-lookup"><span data-stu-id="17f6b-132">Specifies the objects to convert to JSON format.</span></span> <span data-ttu-id="17f6b-133">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="17f6b-133">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="17f6b-134">还可以通过管道将对象传递给 `ConvertTo-Json` 。</span><span class="sxs-lookup"><span data-stu-id="17f6b-134">You can also pipe an object to `ConvertTo-Json`.</span></span>

<span data-ttu-id="17f6b-135">**InputObject** 参数是必需的，但其值可以为 null (`$null`) 或空字符串。</span><span class="sxs-lookup"><span data-stu-id="17f6b-135">The **InputObject** parameter is required, but its value can be null (`$null`) or an empty string.</span></span>
<span data-ttu-id="17f6b-136">当输入对象为时 `$null` ，不 `ConvertTo-Json` 会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="17f6b-136">When the input object is `$null`, `ConvertTo-Json` does not generate any output.</span></span> <span data-ttu-id="17f6b-137">当输入对象是空字符串时，将 `ConvertTo-Json` 返回一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="17f6b-137">When the input object is an empty string, `ConvertTo-Json` returns an empty string.</span></span>

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

### <span data-ttu-id="17f6b-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="17f6b-138">CommonParameters</span></span>

<span data-ttu-id="17f6b-139">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="17f6b-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="17f6b-140">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="17f6b-140">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="17f6b-141">输入</span><span class="sxs-lookup"><span data-stu-id="17f6b-141">INPUTS</span></span>

### <span data-ttu-id="17f6b-142">System.Object</span><span class="sxs-lookup"><span data-stu-id="17f6b-142">System.Object</span></span>

<span data-ttu-id="17f6b-143">可以通过管道将任何对象传递给 `ConvertTo-Json` 。</span><span class="sxs-lookup"><span data-stu-id="17f6b-143">You can pipe any object to `ConvertTo-Json`.</span></span>

## <span data-ttu-id="17f6b-144">输出</span><span class="sxs-lookup"><span data-stu-id="17f6b-144">OUTPUTS</span></span>

### <span data-ttu-id="17f6b-145">System.String</span><span class="sxs-lookup"><span data-stu-id="17f6b-145">System.String</span></span>

## <span data-ttu-id="17f6b-146">注释</span><span class="sxs-lookup"><span data-stu-id="17f6b-146">NOTES</span></span>

<span data-ttu-id="17f6b-147">`ConvertTo-Json`Cmdlet 是使用[JavaScriptSerializer 类](/dotnet/api/system.web.script.serialization.javascriptserializer)实现的。</span><span class="sxs-lookup"><span data-stu-id="17f6b-147">The `ConvertTo-Json` cmdlet is implemented using the [JavaScriptSerializer class](/dotnet/api/system.web.script.serialization.javascriptserializer).</span></span>

## <span data-ttu-id="17f6b-148">相关链接</span><span class="sxs-lookup"><span data-stu-id="17f6b-148">RELATED LINKS</span></span>

<span data-ttu-id="17f6b-149">[JavaScript 和 .NET 中的 JavaScript 对象表示法 (JSON) 简介](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="17f6b-149">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="17f6b-150">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="17f6b-150">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="17f6b-151">Get-Content</span><span class="sxs-lookup"><span data-stu-id="17f6b-151">Get-Content</span></span>](../Microsoft.PowerShell.Management/Get-Content.md)

[<span data-ttu-id="17f6b-152">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="17f6b-152">Get-UICulture</span></span>](Get-UICulture.md)

[<span data-ttu-id="17f6b-153">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="17f6b-153">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="17f6b-154">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="17f6b-154">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
