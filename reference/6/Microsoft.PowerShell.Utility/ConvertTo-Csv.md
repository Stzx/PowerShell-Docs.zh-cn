---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: 5de6a3bd28b850d3fc1632e26998986f302b78f8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198637"
---
# <span data-ttu-id="b5d5f-103">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="b5d5f-103">ConvertTo-Csv</span></span>

## <span data-ttu-id="b5d5f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b5d5f-104">SYNOPSIS</span></span>
<span data-ttu-id="b5d5f-105">将 .NET 对象转换为一系列字符分隔值 (CSV) 字符串。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-105">Converts .NET objects into a series of character-separated value (CSV) strings.</span></span>

## <span data-ttu-id="b5d5f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b5d5f-106">SYNTAX</span></span>

### <span data-ttu-id="b5d5f-107">DelimiterPath (默认值) </span><span class="sxs-lookup"><span data-stu-id="b5d5f-107">DelimiterPath (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [-IncludeTypeInformation] [-NoTypeInformation]
 [<CommonParameters>]
```

### <span data-ttu-id="b5d5f-108">分隔符</span><span class="sxs-lookup"><span data-stu-id="b5d5f-108">Delimiter</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [<CommonParameters>]
```

### <span data-ttu-id="b5d5f-109">UseCulture</span><span class="sxs-lookup"><span data-stu-id="b5d5f-109">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [<CommonParameters>]
```

## <span data-ttu-id="b5d5f-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b5d5f-110">DESCRIPTION</span></span>

<span data-ttu-id="b5d5f-111">`ConvertTo-CSV`Cmdlet 将返回一系列逗号分隔值 (CSV) 字符串，这些字符串表示你提交的对象。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-111">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="b5d5f-112">然后，可以使用 `ConvertFrom-Csv` cmdlet 从 CSV 字符串重新创建对象。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-112">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="b5d5f-113">从 CSV 转换的对象是包含属性值和没有方法的原始对象的字符串值。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-113">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="b5d5f-114">可以使用 `Export-Csv` cmdlet 将对象转换为 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-114">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="b5d5f-115">`Export-CSV` 类似于 `ConvertTo-CSV` ，只不过它将 CSV 字符串保存到文件。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-115">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="b5d5f-116">`ConvertTo-CSV`Cmdlet 具有参数以指定逗号以外的分隔符，或使用当前区域性作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-116">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="b5d5f-117">示例</span><span class="sxs-lookup"><span data-stu-id="b5d5f-117">EXAMPLES</span></span>

### <span data-ttu-id="b5d5f-118">示例1：将对象转换为 CSV</span><span class="sxs-lookup"><span data-stu-id="b5d5f-118">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="b5d5f-119">此示例将 **进程** 对象转换为 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-119">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name pwsh | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"pwsh","8","950","2204001161216","100925440","59686912","67104", ...
```

<span data-ttu-id="b5d5f-120">该 `Get-Process` cmdlet 将获取 **Process** 对象，并使用 **Name** 参数来指定 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-120">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="b5d5f-121">进程对象将通过管道向下发送到 `ConvertTo-CSV` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-121">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="b5d5f-122">`ConvertTo-CSV`Cmdlet 可将对象转换为 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-122">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="b5d5f-123">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头，而在 PowerShell 6 中则不需要。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-123">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="b5d5f-124">示例2：将 DateTime 对象转换为 CSV</span><span class="sxs-lookup"><span data-stu-id="b5d5f-124">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="b5d5f-125">此示例将 **DateTime** 对象转换为 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-125">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="b5d5f-126">该 `Get-Date` cmdlet 将获取 **DateTime** 对象并将其保存在 `$Date` 变量中。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-126">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="b5d5f-127">`ConvertTo-Csv`Cmdlet 将 **DateTime** 对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-127">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="b5d5f-128">**InputObject** 参数使用存储在变量中的 **DateTime** 对象 `$Date` 。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-128">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="b5d5f-129">**分隔符** 参数指定用分号分隔字符串值。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-129">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="b5d5f-130">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头，而在 PowerShell 6 中则不需要。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-130">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="b5d5f-131">示例3：将 PowerShell 事件日志转换为 CSV</span><span class="sxs-lookup"><span data-stu-id="b5d5f-131">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="b5d5f-132">此示例将 PowerShell 的 Windows 事件日志转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-132">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'PowerShellCore/Operational' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error""4100","1",,"3","106","19","0","31716","PowerShellCore", ...
```

<span data-ttu-id="b5d5f-133">该 `Get-Culture` cmdlet 使用嵌套属性 **TextInfo** 和 **ListSeparator** ，并显示当前区域性的默认列表分隔符。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-133">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="b5d5f-134">该 `Get-WinEvent` cmdlet 将获取事件日志对象，并使用 **LogName** 参数来指定日志文件名。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-134">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="b5d5f-135">事件日志对象通过管道发送到 `ConvertTo-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-135">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="b5d5f-136">`ConvertTo-Csv`Cmdlet 将事件日志对象转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-136">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="b5d5f-137">**UseCulture** 参数使用当前区域性的默认列表分隔符作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-137">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="b5d5f-138">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头，而在 PowerShell 6 中则不需要。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-138">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

## <span data-ttu-id="b5d5f-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b5d5f-139">PARAMETERS</span></span>

### <span data-ttu-id="b5d5f-140">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="b5d5f-140">-Delimiter</span></span>

<span data-ttu-id="b5d5f-141">指定分隔 CSV 字符串中的属性值的分隔符。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-141">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="b5d5f-142">默认值为逗号 (`,`) 。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-142">The default is a comma (`,`).</span></span> <span data-ttu-id="b5d5f-143">输入一个字符，例如冒号 (`:`) 。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-143">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="b5d5f-144">若要指定分号 (`;`) 将其括在单引号内。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-144">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

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

### <span data-ttu-id="b5d5f-145">-IncludeTypeInformation</span><span class="sxs-lookup"><span data-stu-id="b5d5f-145">-IncludeTypeInformation</span></span>

<span data-ttu-id="b5d5f-146">使用此参数时，输出的第一行将包含 **#TYPE** 后跟对象类型的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-146">When this parameter is used the first line of the output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="b5d5f-147">例如， **#TYPE** "。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-147">For example, **#TYPE System.Diagnostics.Process** .</span></span>

<span data-ttu-id="b5d5f-148">此参数是在 PowerShell 6.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-148">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ITI

Required: False
Position: Named
Default value: #TYPE <Object>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b5d5f-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b5d5f-149">-InputObject</span></span>

<span data-ttu-id="b5d5f-150">指定转换为 CSV 字符串的对象。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-150">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="b5d5f-151">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-151">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="b5d5f-152">还可以通过管道将对象传递给 `ConvertTo-CSV` 。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-152">You can also pipe objects to `ConvertTo-CSV`.</span></span>

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

### <span data-ttu-id="b5d5f-153">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="b5d5f-153">-NoTypeInformation</span></span>

<span data-ttu-id="b5d5f-154">从输出中删除 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-154">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="b5d5f-155">此参数已成为 PowerShell 6.0 中的默认参数，包含它是为了向后兼容。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-155">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="b5d5f-156">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="b5d5f-156">-UseCulture</span></span>

<span data-ttu-id="b5d5f-157">将当前区域性的列表分隔符用作项分隔符。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-157">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="b5d5f-158">若要查找区域性的列表分隔符，请使用以下命令： `(Get-Culture).TextInfo.ListSeparator` 。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-158">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="b5d5f-159">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b5d5f-159">CommonParameters</span></span>

<span data-ttu-id="b5d5f-160">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b5d5f-161">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b5d5f-162">输入</span><span class="sxs-lookup"><span data-stu-id="b5d5f-162">INPUTS</span></span>

### <span data-ttu-id="b5d5f-163">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="b5d5f-163">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b5d5f-164">可以通过管道将具有扩展类型系统 (ETS) 适配器的任何对象传递给 `ConvertTo-CSV` 。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-164">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="b5d5f-165">输出</span><span class="sxs-lookup"><span data-stu-id="b5d5f-165">OUTPUTS</span></span>

### <span data-ttu-id="b5d5f-166">System.String</span><span class="sxs-lookup"><span data-stu-id="b5d5f-166">System.String</span></span>

<span data-ttu-id="b5d5f-167">CSV 输出将作为字符串集合返回。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-167">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="b5d5f-168">注释</span><span class="sxs-lookup"><span data-stu-id="b5d5f-168">NOTES</span></span>

<span data-ttu-id="b5d5f-169">采用 CSV 格式时，通过以逗号分隔的对象属性值列表来表示每个对象。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-169">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="b5d5f-170">使用对象的 **ToString ( # B1** 方法将属性值转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-170">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="b5d5f-171">字符串由属性值名称表示。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-171">The strings are represented by the property value name.</span></span> <span data-ttu-id="b5d5f-172">`ConvertTo-CSV` 不导出对象的方法。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-172">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="b5d5f-173">CSV 字符串的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="b5d5f-173">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="b5d5f-174">如果使用了 **IncludeTypeInformation** ，则第一个字符串将包含 **#TYPE** 后跟对象类型的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-174">If **IncludeTypeInformation** is used, the first string consists of **#TYPE** followed by the object type's fully qualified name.</span></span> <span data-ttu-id="b5d5f-175">例如， **#TYPE** "。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-175">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="b5d5f-176">如果未使用 **IncludeTypeInformation** ，则第一个字符串包括列标题。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-176">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="b5d5f-177">标头以逗号分隔的列表的形式包含第一个对象的属性名称。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-177">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="b5d5f-178">其余字符串包含每个对象的属性值的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-178">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="b5d5f-179">从 PowerShell 6.0 开始，的默认行为 `ConvertTo-CSV` 是不包括 CSV 中的 **#TYPE** 信息，并且 **NoTypeInformation** 是隐含的。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-179">Beginning with PowerShell 6.0 the default behavior of `ConvertTo-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="b5d5f-180">**IncludeTypeInformation** 可用于包含 **#TYPE** 信息并模拟 `ConvertTo-CSV` PowerShell 6.0 之前的默认行为。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-180">**IncludeTypeInformation** can be used to include the **#TYPE** information and emulate the default behavior of `ConvertTo-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="b5d5f-181">当您将多个对象提交到时 `ConvertTo-CSV` ，将 `ConvertTo-CSV` 根据您提交的第一个对象的属性对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-181">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="b5d5f-182">如果剩余的对象没有指定的属性之一，则该对象的属性值为 Null，由两个连续的逗号表示。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-182">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="b5d5f-183">如果剩余的对象具有其他属性，则忽略这些属性值。</span><span class="sxs-lookup"><span data-stu-id="b5d5f-183">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="b5d5f-184">相关链接</span><span class="sxs-lookup"><span data-stu-id="b5d5f-184">RELATED LINKS</span></span>

[<span data-ttu-id="b5d5f-185">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="b5d5f-185">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="b5d5f-186">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="b5d5f-186">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="b5d5f-187">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="b5d5f-187">Import-Csv</span></span>](Import-Csv.md)
