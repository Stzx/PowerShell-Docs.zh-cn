---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: be590368539f396f0aac694e9565674393543f2c
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913196"
---
# <span data-ttu-id="31c39-102">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="31c39-102">ConvertTo-Csv</span></span>

## <span data-ttu-id="31c39-103">摘要</span><span class="sxs-lookup"><span data-stu-id="31c39-103">SYNOPSIS</span></span>
<span data-ttu-id="31c39-104">将 .NET 对象转换为一系列逗号分隔值 (CSV) 字符串。</span><span class="sxs-lookup"><span data-stu-id="31c39-104">Converts .NET objects into a series of comma-separated value (CSV) strings.</span></span>

## <span data-ttu-id="31c39-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="31c39-105">SYNTAX</span></span>

### <span data-ttu-id="31c39-106">Delimiter（默认值）</span><span class="sxs-lookup"><span data-stu-id="31c39-106">Delimiter (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [[-Delimiter] <char>] [-NoTypeInformation]
 [<CommonParameters>]
```

### <span data-ttu-id="31c39-107">UseCulture</span><span class="sxs-lookup"><span data-stu-id="31c39-107">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [-UseCulture] [-NoTypeInformation] [<CommonParameters>]
```

## <span data-ttu-id="31c39-108">说明</span><span class="sxs-lookup"><span data-stu-id="31c39-108">DESCRIPTION</span></span>

<span data-ttu-id="31c39-109">`ConvertTo-CSV`Cmdlet 将返回一系列逗号分隔值 (CSV) 字符串，这些字符串表示你提交的对象。</span><span class="sxs-lookup"><span data-stu-id="31c39-109">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="31c39-110">然后，可以使用 `ConvertFrom-Csv` cmdlet 从 CSV 字符串重新创建对象。</span><span class="sxs-lookup"><span data-stu-id="31c39-110">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="31c39-111">从 CSV 转换的对象是包含属性值和没有方法的原始对象的字符串值。</span><span class="sxs-lookup"><span data-stu-id="31c39-111">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="31c39-112">可以使用 `Export-Csv` cmdlet 将对象转换为 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="31c39-112">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="31c39-113">`Export-CSV` 类似于 `ConvertTo-CSV` ，只不过它将 CSV 字符串保存到文件。</span><span class="sxs-lookup"><span data-stu-id="31c39-113">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="31c39-114">`ConvertTo-CSV`Cmdlet 具有参数以指定逗号以外的分隔符，或使用当前区域性作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="31c39-114">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="31c39-115">示例</span><span class="sxs-lookup"><span data-stu-id="31c39-115">EXAMPLES</span></span>

### <span data-ttu-id="31c39-116">示例1：将对象转换为 CSV</span><span class="sxs-lookup"><span data-stu-id="31c39-116">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="31c39-117">此示例将 **进程** 对象转换为 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="31c39-117">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name 'PowerShell' | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"powershell","11","691","2204036739072","175943680","132665344","33312", ...
```

<span data-ttu-id="31c39-118">该 `Get-Process` cmdlet 将获取 **Process** 对象，并使用 **Name** 参数来指定 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="31c39-118">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="31c39-119">进程对象将通过管道向下发送到 `ConvertTo-CSV` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="31c39-119">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="31c39-120">`ConvertTo-CSV`Cmdlet 可将对象转换为 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="31c39-120">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="31c39-121">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="31c39-121">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="31c39-122">示例2：将 DateTime 对象转换为 CSV</span><span class="sxs-lookup"><span data-stu-id="31c39-122">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="31c39-123">此示例将 **DateTime** 对象转换为 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="31c39-123">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="31c39-124">该 `Get-Date` cmdlet 将获取 **DateTime** 对象并将其保存在 `$Date` 变量中。</span><span class="sxs-lookup"><span data-stu-id="31c39-124">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="31c39-125">`ConvertTo-Csv`Cmdlet 将 **DateTime** 对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="31c39-125">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="31c39-126">**InputObject** 参数使用存储在变量中的 **DateTime** 对象 `$Date` 。</span><span class="sxs-lookup"><span data-stu-id="31c39-126">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="31c39-127">**分隔符** 参数指定用分号分隔字符串值。</span><span class="sxs-lookup"><span data-stu-id="31c39-127">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="31c39-128">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="31c39-128">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="31c39-129">示例3：将 PowerShell 事件日志转换为 CSV</span><span class="sxs-lookup"><span data-stu-id="31c39-129">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="31c39-130">此示例将 PowerShell 的 Windows 事件日志转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="31c39-130">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'Windows PowerShell' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error","403",,"0","4","4",,"36028797018963968","46891","PowerShell", ...
```

<span data-ttu-id="31c39-131">该 `Get-Culture` cmdlet 使用嵌套属性 **TextInfo** 和 **ListSeparator** ，并显示当前区域性的默认列表分隔符。</span><span class="sxs-lookup"><span data-stu-id="31c39-131">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="31c39-132">该 `Get-WinEvent` cmdlet 将获取事件日志对象，并使用 **LogName** 参数来指定日志文件名。</span><span class="sxs-lookup"><span data-stu-id="31c39-132">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="31c39-133">事件日志对象通过管道发送到 `ConvertTo-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="31c39-133">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="31c39-134">`ConvertTo-Csv`Cmdlet 将事件日志对象转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="31c39-134">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="31c39-135">**UseCulture** 参数使用当前区域性的默认列表分隔符作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="31c39-135">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="31c39-136">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="31c39-136">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

## <span data-ttu-id="31c39-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="31c39-137">PARAMETERS</span></span>

### <span data-ttu-id="31c39-138">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="31c39-138">-Delimiter</span></span>

<span data-ttu-id="31c39-139">指定分隔 CSV 字符串中的属性值的分隔符。</span><span class="sxs-lookup"><span data-stu-id="31c39-139">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="31c39-140">默认值为逗号 (`,`) 。</span><span class="sxs-lookup"><span data-stu-id="31c39-140">The default is a comma (`,`).</span></span> <span data-ttu-id="31c39-141">输入一个字符，例如冒号 (`:`) 。</span><span class="sxs-lookup"><span data-stu-id="31c39-141">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="31c39-142">若要指定分号 (`;`) 将其括在单引号内。</span><span class="sxs-lookup"><span data-stu-id="31c39-142">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

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

### <span data-ttu-id="31c39-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="31c39-143">-InputObject</span></span>

<span data-ttu-id="31c39-144">指定转换为 CSV 字符串的对象。</span><span class="sxs-lookup"><span data-stu-id="31c39-144">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="31c39-145">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="31c39-145">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="31c39-146">还可以通过管道将对象传递给 `ConvertTo-CSV` 。</span><span class="sxs-lookup"><span data-stu-id="31c39-146">You can also pipe objects to `ConvertTo-CSV`.</span></span>

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

### <span data-ttu-id="31c39-147">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="31c39-147">-NoTypeInformation</span></span>

<span data-ttu-id="31c39-148">从输出中删除 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="31c39-148">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="31c39-149">此参数已成为 PowerShell 6.0 中的默认参数，包含它是为了向后兼容。</span><span class="sxs-lookup"><span data-stu-id="31c39-149">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="31c39-150">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="31c39-150">-UseCulture</span></span>

<span data-ttu-id="31c39-151">将当前区域性的列表分隔符用作项分隔符。</span><span class="sxs-lookup"><span data-stu-id="31c39-151">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="31c39-152">若要查找区域性的列表分隔符，请使用以下命令： `(Get-Culture).TextInfo.ListSeparator` 。</span><span class="sxs-lookup"><span data-stu-id="31c39-152">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="31c39-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="31c39-153">CommonParameters</span></span>

<span data-ttu-id="31c39-154">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="31c39-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="31c39-155">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="31c39-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="31c39-156">输入</span><span class="sxs-lookup"><span data-stu-id="31c39-156">INPUTS</span></span>

### <span data-ttu-id="31c39-157">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="31c39-157">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="31c39-158">可以通过管道将具有扩展类型系统 (ETS) 适配器的任何对象传递给 `ConvertTo-CSV` 。</span><span class="sxs-lookup"><span data-stu-id="31c39-158">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="31c39-159">输出</span><span class="sxs-lookup"><span data-stu-id="31c39-159">OUTPUTS</span></span>

### <span data-ttu-id="31c39-160">System.String</span><span class="sxs-lookup"><span data-stu-id="31c39-160">System.String</span></span>

<span data-ttu-id="31c39-161">CSV 输出将作为字符串集合返回。</span><span class="sxs-lookup"><span data-stu-id="31c39-161">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="31c39-162">注释</span><span class="sxs-lookup"><span data-stu-id="31c39-162">NOTES</span></span>

<span data-ttu-id="31c39-163">采用 CSV 格式时，通过以逗号分隔的对象属性值列表来表示每个对象。</span><span class="sxs-lookup"><span data-stu-id="31c39-163">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="31c39-164">使用对象的 **ToString ( # B1** 方法将属性值转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="31c39-164">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="31c39-165">字符串由属性值名称表示。</span><span class="sxs-lookup"><span data-stu-id="31c39-165">The strings are represented by the property value name.</span></span> <span data-ttu-id="31c39-166">`ConvertTo-CSV` 不导出对象的方法。</span><span class="sxs-lookup"><span data-stu-id="31c39-166">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="31c39-167">CSV 字符串的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="31c39-167">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="31c39-168">默认情况下，第一个字符串包含后跟对象类型的完全限定名称的 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="31c39-168">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="31c39-169">例如， **#TYPE**"。</span><span class="sxs-lookup"><span data-stu-id="31c39-169">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="31c39-170">如果使用 **NoTypeInformation** ，则第一个字符串包括列标题。</span><span class="sxs-lookup"><span data-stu-id="31c39-170">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="31c39-171">标头以逗号分隔的列表的形式包含第一个对象的属性名称。</span><span class="sxs-lookup"><span data-stu-id="31c39-171">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="31c39-172">其余字符串包含每个对象的属性值的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="31c39-172">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="31c39-173">当您将多个对象提交到时 `ConvertTo-CSV` ，将 `ConvertTo-CSV` 根据您提交的第一个对象的属性对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="31c39-173">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="31c39-174">如果剩余的对象没有指定的属性之一，则该对象的属性值为 Null，由两个连续的逗号表示。</span><span class="sxs-lookup"><span data-stu-id="31c39-174">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="31c39-175">如果剩余的对象具有其他属性，则忽略这些属性值。</span><span class="sxs-lookup"><span data-stu-id="31c39-175">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="31c39-176">相关链接</span><span class="sxs-lookup"><span data-stu-id="31c39-176">RELATED LINKS</span></span>

[<span data-ttu-id="31c39-177">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="31c39-177">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="31c39-178">导出-Csv</span><span class="sxs-lookup"><span data-stu-id="31c39-178">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="31c39-179">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="31c39-179">Import-Csv</span></span>](Import-Csv.md)
