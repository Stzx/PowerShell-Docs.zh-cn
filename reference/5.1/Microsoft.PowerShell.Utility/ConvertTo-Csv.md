---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: 7d399661e4514c0a39ad00601d554c41c2897ff9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197964"
---
# <span data-ttu-id="ef860-103">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="ef860-103">ConvertTo-Csv</span></span>

## <span data-ttu-id="ef860-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ef860-104">SYNOPSIS</span></span>
<span data-ttu-id="ef860-105">将 .NET 对象转换为一系列逗号分隔值 (CSV) 字符串。</span><span class="sxs-lookup"><span data-stu-id="ef860-105">Converts .NET objects into a series of comma-separated value (CSV) strings.</span></span>

## <span data-ttu-id="ef860-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ef860-106">SYNTAX</span></span>

### <span data-ttu-id="ef860-107">Delimiter（默认值）</span><span class="sxs-lookup"><span data-stu-id="ef860-107">Delimiter (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [[-Delimiter] <char>] [-NoTypeInformation]
 [<CommonParameters>]
```

### <span data-ttu-id="ef860-108">UseCulture</span><span class="sxs-lookup"><span data-stu-id="ef860-108">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [-UseCulture] [-NoTypeInformation] [<CommonParameters>]
```

## <span data-ttu-id="ef860-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ef860-109">DESCRIPTION</span></span>

<span data-ttu-id="ef860-110">`ConvertTo-CSV`Cmdlet 将返回一系列逗号分隔值 (CSV) 字符串，这些字符串表示你提交的对象。</span><span class="sxs-lookup"><span data-stu-id="ef860-110">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="ef860-111">然后，可以使用 `ConvertFrom-Csv` cmdlet 从 CSV 字符串重新创建对象。</span><span class="sxs-lookup"><span data-stu-id="ef860-111">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="ef860-112">从 CSV 转换的对象是包含属性值和没有方法的原始对象的字符串值。</span><span class="sxs-lookup"><span data-stu-id="ef860-112">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="ef860-113">可以使用 `Export-Csv` cmdlet 将对象转换为 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="ef860-113">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="ef860-114">`Export-CSV` 类似于 `ConvertTo-CSV` ，只不过它将 CSV 字符串保存到文件。</span><span class="sxs-lookup"><span data-stu-id="ef860-114">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="ef860-115">`ConvertTo-CSV`Cmdlet 具有参数以指定逗号以外的分隔符，或使用当前区域性作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="ef860-115">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="ef860-116">示例</span><span class="sxs-lookup"><span data-stu-id="ef860-116">EXAMPLES</span></span>

### <span data-ttu-id="ef860-117">示例1：将对象转换为 CSV</span><span class="sxs-lookup"><span data-stu-id="ef860-117">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="ef860-118">此示例将 **进程** 对象转换为 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="ef860-118">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name 'PowerShell' | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"powershell","11","691","2204036739072","175943680","132665344","33312", ...
```

<span data-ttu-id="ef860-119">该 `Get-Process` cmdlet 将获取 **Process** 对象，并使用 **Name** 参数来指定 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="ef860-119">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="ef860-120">进程对象将通过管道向下发送到 `ConvertTo-CSV` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef860-120">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="ef860-121">`ConvertTo-CSV`Cmdlet 可将对象转换为 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="ef860-121">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="ef860-122">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="ef860-122">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="ef860-123">示例2：将 DateTime 对象转换为 CSV</span><span class="sxs-lookup"><span data-stu-id="ef860-123">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="ef860-124">此示例将 **DateTime** 对象转换为 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="ef860-124">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="ef860-125">该 `Get-Date` cmdlet 将获取 **DateTime** 对象并将其保存在 `$Date` 变量中。</span><span class="sxs-lookup"><span data-stu-id="ef860-125">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="ef860-126">`ConvertTo-Csv`Cmdlet 将 **DateTime** 对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="ef860-126">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="ef860-127">**InputObject** 参数使用存储在变量中的 **DateTime** 对象 `$Date` 。</span><span class="sxs-lookup"><span data-stu-id="ef860-127">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="ef860-128">**分隔符** 参数指定用分号分隔字符串值。</span><span class="sxs-lookup"><span data-stu-id="ef860-128">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="ef860-129">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="ef860-129">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="ef860-130">示例3：将 PowerShell 事件日志转换为 CSV</span><span class="sxs-lookup"><span data-stu-id="ef860-130">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="ef860-131">此示例将 PowerShell 的 Windows 事件日志转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="ef860-131">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'Windows PowerShell' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error","403",,"0","4","4",,"36028797018963968","46891","PowerShell", ...
```

<span data-ttu-id="ef860-132">该 `Get-Culture` cmdlet 使用嵌套属性 **TextInfo** 和 **ListSeparator** ，并显示当前区域性的默认列表分隔符。</span><span class="sxs-lookup"><span data-stu-id="ef860-132">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="ef860-133">该 `Get-WinEvent` cmdlet 将获取事件日志对象，并使用 **LogName** 参数来指定日志文件名。</span><span class="sxs-lookup"><span data-stu-id="ef860-133">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="ef860-134">事件日志对象通过管道发送到 `ConvertTo-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef860-134">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="ef860-135">`ConvertTo-Csv`Cmdlet 将事件日志对象转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="ef860-135">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="ef860-136">**UseCulture** 参数使用当前区域性的默认列表分隔符作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="ef860-136">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="ef860-137">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="ef860-137">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

## <span data-ttu-id="ef860-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ef860-138">PARAMETERS</span></span>

### <span data-ttu-id="ef860-139">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="ef860-139">-Delimiter</span></span>

<span data-ttu-id="ef860-140">指定分隔 CSV 字符串中的属性值的分隔符。</span><span class="sxs-lookup"><span data-stu-id="ef860-140">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="ef860-141">默认值为逗号 (`,`) 。</span><span class="sxs-lookup"><span data-stu-id="ef860-141">The default is a comma (`,`).</span></span> <span data-ttu-id="ef860-142">输入一个字符，例如冒号 (`:`) 。</span><span class="sxs-lookup"><span data-stu-id="ef860-142">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="ef860-143">若要指定分号 (`;`) 将其括在单引号内。</span><span class="sxs-lookup"><span data-stu-id="ef860-143">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef860-144">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ef860-144">-InputObject</span></span>

<span data-ttu-id="ef860-145">指定转换为 CSV 字符串的对象。</span><span class="sxs-lookup"><span data-stu-id="ef860-145">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="ef860-146">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="ef860-146">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="ef860-147">还可以通过管道将对象传递给 `ConvertTo-CSV` 。</span><span class="sxs-lookup"><span data-stu-id="ef860-147">You can also pipe objects to `ConvertTo-CSV`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ef860-148">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="ef860-148">-NoTypeInformation</span></span>

<span data-ttu-id="ef860-149">从输出中删除 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="ef860-149">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="ef860-150">此参数已成为 PowerShell 6.0 中的默认参数，包含它是为了向后兼容。</span><span class="sxs-lookup"><span data-stu-id="ef860-150">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef860-151">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="ef860-151">-UseCulture</span></span>

<span data-ttu-id="ef860-152">将当前区域性的列表分隔符用作项分隔符。</span><span class="sxs-lookup"><span data-stu-id="ef860-152">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="ef860-153">若要查找区域性的列表分隔符，请使用以下命令： `(Get-Culture).TextInfo.ListSeparator` 。</span><span class="sxs-lookup"><span data-stu-id="ef860-153">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef860-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ef860-154">CommonParameters</span></span>

<span data-ttu-id="ef860-155">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ef860-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ef860-156">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ef860-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ef860-157">输入</span><span class="sxs-lookup"><span data-stu-id="ef860-157">INPUTS</span></span>

### <span data-ttu-id="ef860-158">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="ef860-158">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="ef860-159">可以通过管道将具有扩展类型系统 (ETS) 适配器的任何对象传递给 `ConvertTo-CSV` 。</span><span class="sxs-lookup"><span data-stu-id="ef860-159">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="ef860-160">输出</span><span class="sxs-lookup"><span data-stu-id="ef860-160">OUTPUTS</span></span>

### <span data-ttu-id="ef860-161">System.String</span><span class="sxs-lookup"><span data-stu-id="ef860-161">System.String</span></span>

<span data-ttu-id="ef860-162">CSV 输出将作为字符串集合返回。</span><span class="sxs-lookup"><span data-stu-id="ef860-162">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="ef860-163">注释</span><span class="sxs-lookup"><span data-stu-id="ef860-163">NOTES</span></span>

<span data-ttu-id="ef860-164">采用 CSV 格式时，通过以逗号分隔的对象属性值列表来表示每个对象。</span><span class="sxs-lookup"><span data-stu-id="ef860-164">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="ef860-165">使用对象的 **ToString ( # B1** 方法将属性值转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="ef860-165">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="ef860-166">字符串由属性值名称表示。</span><span class="sxs-lookup"><span data-stu-id="ef860-166">The strings are represented by the property value name.</span></span> <span data-ttu-id="ef860-167">`ConvertTo-CSV` 不导出对象的方法。</span><span class="sxs-lookup"><span data-stu-id="ef860-167">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="ef860-168">CSV 字符串的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="ef860-168">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="ef860-169">默认情况下，第一个字符串包含后跟对象类型的完全限定名称的 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="ef860-169">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="ef860-170">例如， **#TYPE** "。</span><span class="sxs-lookup"><span data-stu-id="ef860-170">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="ef860-171">如果使用 **NoTypeInformation** ，则第一个字符串包括列标题。</span><span class="sxs-lookup"><span data-stu-id="ef860-171">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="ef860-172">标头以逗号分隔的列表的形式包含第一个对象的属性名称。</span><span class="sxs-lookup"><span data-stu-id="ef860-172">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="ef860-173">其余字符串包含每个对象的属性值的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="ef860-173">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="ef860-174">当您将多个对象提交到时 `ConvertTo-CSV` ，将 `ConvertTo-CSV` 根据您提交的第一个对象的属性对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="ef860-174">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="ef860-175">如果剩余的对象没有指定的属性之一，则该对象的属性值为 Null，由两个连续的逗号表示。</span><span class="sxs-lookup"><span data-stu-id="ef860-175">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="ef860-176">如果剩余的对象具有其他属性，则忽略这些属性值。</span><span class="sxs-lookup"><span data-stu-id="ef860-176">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="ef860-177">相关链接</span><span class="sxs-lookup"><span data-stu-id="ef860-177">RELATED LINKS</span></span>

[<span data-ttu-id="ef860-178">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="ef860-178">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="ef860-179">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="ef860-179">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="ef860-180">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="ef860-180">Import-Csv</span></span>](Import-Csv.md)
