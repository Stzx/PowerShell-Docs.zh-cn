---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-custom?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Custom
ms.openlocfilehash: c8bf4dfa9077af04e4122672a15a7c768cb49ea2
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "93199245"
---
# <span data-ttu-id="94fc6-103">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="94fc6-103">Format-Custom</span></span>

## <span data-ttu-id="94fc6-104">摘要</span><span class="sxs-lookup"><span data-stu-id="94fc6-104">SYNOPSIS</span></span>
<span data-ttu-id="94fc6-105">使用自定义的视图来设置输出格式。</span><span class="sxs-lookup"><span data-stu-id="94fc6-105">Uses a customized view to format the output.</span></span>

## <span data-ttu-id="94fc6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="94fc6-106">SYNTAX</span></span>

```
Format-Custom [[-Property] <Object[]>] [-Depth <Int32>] [-GroupBy <Object>] [-View <String>]
 [-ShowError] [-DisplayError] [-Force] [-Expand <String>] [-InputObject <PSObject>]
 [<CommonParameters>]
```

## <span data-ttu-id="94fc6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="94fc6-107">DESCRIPTION</span></span>

<span data-ttu-id="94fc6-108">`Format-Custom`Cmdlet 将命令的输出格式设置为替代视图中的定义。</span><span class="sxs-lookup"><span data-stu-id="94fc6-108">The `Format-Custom` cmdlet formats the output of a command as defined in an alternate view.</span></span>
<span data-ttu-id="94fc6-109">`Format-Custom` 旨在显示不只是表格或只是列表的视图。</span><span class="sxs-lookup"><span data-stu-id="94fc6-109">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="94fc6-110">你可以使用在 PowerShell 中定义的视图，也可以在新文件中创建你自己的视图， `format.ps1xml` 并使用 `Update-FormatData` cmdlet 将它们添加到 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="94fc6-110">You can use the views defined in PowerShell, or you can create your own views in a new `format.ps1xml` file and use the `Update-FormatData` cmdlet to add them to PowerShell.</span></span>

## <span data-ttu-id="94fc6-111">示例</span><span class="sxs-lookup"><span data-stu-id="94fc6-111">EXAMPLES</span></span>

### <span data-ttu-id="94fc6-112">示例1：使用自定义视图设置输出格式</span><span class="sxs-lookup"><span data-stu-id="94fc6-112">Example 1: Format output with a custom view</span></span>

```powershell
Get-Command Start-Transcript | Format-Custom -View MyView
```

<span data-ttu-id="94fc6-113">此命令使用 `Start-Transcript` MyView 视图（用户创建的自定义视图）定义的格式设置有关 cmdlet 的信息的格式。</span><span class="sxs-lookup"><span data-stu-id="94fc6-113">This command formats information about the `Start-Transcript` cmdlet in the format defined by the MyView view, a custom view created by the user.</span></span> <span data-ttu-id="94fc6-114">若要成功运行此命令，必须首先创建一个新的 TYPES.PS1XML 文件，定义 **MyView** 视图，然后使用 `Update-FormatData` 命令将 types.ps1xml 文件添加到 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="94fc6-114">To run this command successfully, you must first create a new PS1XML file, define the **MyView** view, and then use the `Update-FormatData` command to add the PS1XML file to PowerShell.</span></span>

### <span data-ttu-id="94fc6-115">示例2：用默认视图设置输出格式</span><span class="sxs-lookup"><span data-stu-id="94fc6-115">Example 2: Format output with the default view</span></span>

```powershell
Get-Process Winlogon | Format-Custom
```

<span data-ttu-id="94fc6-116">此命令设置有关其他自定义视图中 **Winlogon** 进程的信息的格式。</span><span class="sxs-lookup"><span data-stu-id="94fc6-116">This command formats information about the **Winlogon** process in an alternate customized view.</span></span>
<span data-ttu-id="94fc6-117">由于该命令不使用 **View** 参数，因此将 `Format-Custom` 使用默认的自定义视图来设置数据的格式。</span><span class="sxs-lookup"><span data-stu-id="94fc6-117">Because the command does not use the **View** parameter, `Format-Custom` uses a default custom view to format the data.</span></span>

### <span data-ttu-id="94fc6-118">示例3：疑难解答格式错误</span><span class="sxs-lookup"><span data-stu-id="94fc6-118">Example 3: Troubleshooting format errors</span></span>

<span data-ttu-id="94fc6-119">下面的示例显示了使用表达式添加 **DisplayError** 或 **ShowError** 参数的结果。</span><span class="sxs-lookup"><span data-stu-id="94fc6-119">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -DisplayError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  = #ERR
}


PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -ShowError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  =
}

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:01:04 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="94fc6-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="94fc6-120">PARAMETERS</span></span>

### <span data-ttu-id="94fc6-121">-Depth</span><span class="sxs-lookup"><span data-stu-id="94fc6-121">-Depth</span></span>

<span data-ttu-id="94fc6-122">指定显示中的列数。</span><span class="sxs-lookup"><span data-stu-id="94fc6-122">Specifies the number of columns in the display.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="94fc6-123">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="94fc6-123">-DisplayError</span></span>

<span data-ttu-id="94fc6-124">在命令行中显示错误。</span><span class="sxs-lookup"><span data-stu-id="94fc6-124">Displays errors at the command line.</span></span> <span data-ttu-id="94fc6-125">此参数很少使用，但当你在命令中设置表达式的格式 `Format-Custom` ，并且表达式似乎无法正常工作时，可将其用作调试帮助。</span><span class="sxs-lookup"><span data-stu-id="94fc6-125">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="94fc6-126">-Expand</span><span class="sxs-lookup"><span data-stu-id="94fc6-126">-Expand</span></span>

<span data-ttu-id="94fc6-127">设置集合对象以及集合中的对象的格式。</span><span class="sxs-lookup"><span data-stu-id="94fc6-127">Formats the collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="94fc6-128">此参数旨在设置支持 **system.object** 接口的对象的格式。</span><span class="sxs-lookup"><span data-stu-id="94fc6-128">This parameter is designed to format objects that support the **System.Collections.ICollection** interface.</span></span> <span data-ttu-id="94fc6-129">默认值为 **EnumOnly** 。</span><span class="sxs-lookup"><span data-stu-id="94fc6-129">The default value is **EnumOnly** .</span></span>

<span data-ttu-id="94fc6-130">有效值是：</span><span class="sxs-lookup"><span data-stu-id="94fc6-130">Valid values are:</span></span>

- <span data-ttu-id="94fc6-131">EnumOnly：显示集合中的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="94fc6-131">EnumOnly: Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="94fc6-132">CoreOnly：显示集合对象的属性。</span><span class="sxs-lookup"><span data-stu-id="94fc6-132">CoreOnly: Displays the properties of the collection object.</span></span>
- <span data-ttu-id="94fc6-133">Both：显示集合对象和集合中对象的属性。</span><span class="sxs-lookup"><span data-stu-id="94fc6-133">Both: Displays the properties of the collection object and the objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: EnumOnly
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="94fc6-134">-Force</span><span class="sxs-lookup"><span data-stu-id="94fc6-134">-Force</span></span>

<span data-ttu-id="94fc6-135">指示 cmdlet 显示所有错误信息。</span><span class="sxs-lookup"><span data-stu-id="94fc6-135">Directs the cmdlet to display all of the error information.</span></span> <span data-ttu-id="94fc6-136">与 **DisplayError** 或 **ShowError** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="94fc6-136">Use with the **DisplayError** or **ShowError** parameters.</span></span> <span data-ttu-id="94fc6-137">默认情况下，当将错误对象写入到错误或显示流时，仅显示部分错误信息。</span><span class="sxs-lookup"><span data-stu-id="94fc6-137">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="94fc6-138">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="94fc6-138">-GroupBy</span></span>

<span data-ttu-id="94fc6-139">基于共享属性或值设置组中输出的格式。</span><span class="sxs-lookup"><span data-stu-id="94fc6-139">Formats the output in groups based on a shared property or value.</span></span> <span data-ttu-id="94fc6-140">请输入表达式或输出的属性。</span><span class="sxs-lookup"><span data-stu-id="94fc6-140">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="94fc6-141">**GroupBy** 参数的值可以是新的计算属性。</span><span class="sxs-lookup"><span data-stu-id="94fc6-141">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="94fc6-142">计算属性可以是脚本块，也可以是哈希表。</span><span class="sxs-lookup"><span data-stu-id="94fc6-142">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="94fc6-143">有效的键-值对为：</span><span class="sxs-lookup"><span data-stu-id="94fc6-143">Valid key-value pairs are:</span></span>

- <span data-ttu-id="94fc6-144">名称 (或标签) - `<string>`</span><span class="sxs-lookup"><span data-stu-id="94fc6-144">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="94fc6-145">Expression `<string>` 或 `<script block>`</span><span class="sxs-lookup"><span data-stu-id="94fc6-145">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="94fc6-146">说明符 `<string>`</span><span class="sxs-lookup"><span data-stu-id="94fc6-146">FormatString - `<string>`</span></span>

<span data-ttu-id="94fc6-147">有关详细信息，请参阅 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)。</span><span class="sxs-lookup"><span data-stu-id="94fc6-147">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="94fc6-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="94fc6-148">-InputObject</span></span>

<span data-ttu-id="94fc6-149">指定要设置格式的对象。</span><span class="sxs-lookup"><span data-stu-id="94fc6-149">Specifies the objects to be formatted.</span></span> <span data-ttu-id="94fc6-150">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="94fc6-150">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="94fc6-151">-Property</span><span class="sxs-lookup"><span data-stu-id="94fc6-151">-Property</span></span>

<span data-ttu-id="94fc6-152">指定要在屏幕上显示的对象属性及其显示顺序。</span><span class="sxs-lookup"><span data-stu-id="94fc6-152">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="94fc6-153">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="94fc6-153">Wildcards are permitted.</span></span>

<span data-ttu-id="94fc6-154">如果省略此参数，则屏幕上显示的属性取决于要显示的对象。</span><span class="sxs-lookup"><span data-stu-id="94fc6-154">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="94fc6-155">参数 name **属性** 是可选的。</span><span class="sxs-lookup"><span data-stu-id="94fc6-155">The parameter name **Property** is optional.</span></span> <span data-ttu-id="94fc6-156">不能在同一命令中使用 **Property** 和 **View** 参数。</span><span class="sxs-lookup"><span data-stu-id="94fc6-156">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="94fc6-157">**Property** 参数的值可以是新的计算属性。</span><span class="sxs-lookup"><span data-stu-id="94fc6-157">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="94fc6-158">计算属性可以是脚本块，也可以是哈希表。</span><span class="sxs-lookup"><span data-stu-id="94fc6-158">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="94fc6-159">有效的键-值对为：</span><span class="sxs-lookup"><span data-stu-id="94fc6-159">Valid key-value pairs are:</span></span>

- <span data-ttu-id="94fc6-160">Expression `<string>` 或 `<script block>`</span><span class="sxs-lookup"><span data-stu-id="94fc6-160">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="94fc6-161">长度 `<int32>`</span><span class="sxs-lookup"><span data-stu-id="94fc6-161">Depth - `<int32>`</span></span>

<span data-ttu-id="94fc6-162">有关详细信息，请参阅 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)。</span><span class="sxs-lookup"><span data-stu-id="94fc6-162">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="94fc6-163">-ShowError</span><span class="sxs-lookup"><span data-stu-id="94fc6-163">-ShowError</span></span>

<span data-ttu-id="94fc6-164">通过管道发送错误。</span><span class="sxs-lookup"><span data-stu-id="94fc6-164">Sends errors through the pipeline.</span></span> <span data-ttu-id="94fc6-165">此参数很少使用，但当你在命令中设置表达式的格式 `Format-Custom` ，并且表达式似乎无法正常工作时，可将其用作调试帮助。</span><span class="sxs-lookup"><span data-stu-id="94fc6-165">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="94fc6-166">-View</span><span class="sxs-lookup"><span data-stu-id="94fc6-166">-View</span></span>

<span data-ttu-id="94fc6-167">指定替代格式或视图的名称。</span><span class="sxs-lookup"><span data-stu-id="94fc6-167">Specifies the name of an alternate format or view.</span></span> <span data-ttu-id="94fc6-168">如果省略此参数，则 `Format-Custom` 使用默认的自定义视图。</span><span class="sxs-lookup"><span data-stu-id="94fc6-168">If you omit this parameter, `Format-Custom` uses a default custom view.</span></span> <span data-ttu-id="94fc6-169">不能在同一命令中使用 **Property** 和 **View** 参数。</span><span class="sxs-lookup"><span data-stu-id="94fc6-169">You cannot use the **Property** and **View** parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="94fc6-170">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="94fc6-170">CommonParameters</span></span>

<span data-ttu-id="94fc6-171">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="94fc6-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="94fc6-172">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="94fc6-172">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="94fc6-173">输入</span><span class="sxs-lookup"><span data-stu-id="94fc6-173">INPUTS</span></span>

### <span data-ttu-id="94fc6-174">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="94fc6-174">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="94fc6-175">可以通过管道将任何对象传递给 `Format-Custom` 。</span><span class="sxs-lookup"><span data-stu-id="94fc6-175">You can pipe any object to `Format-Custom`.</span></span>

## <span data-ttu-id="94fc6-176">输出</span><span class="sxs-lookup"><span data-stu-id="94fc6-176">OUTPUTS</span></span>

### <span data-ttu-id="94fc6-177">Microsoft.PowerShell.Commands.Internal.Format</span><span class="sxs-lookup"><span data-stu-id="94fc6-177">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="94fc6-178">`Format-Custom` 返回表示显示的格式对象。</span><span class="sxs-lookup"><span data-stu-id="94fc6-178">`Format-Custom` returns the format objects that represent the display.</span></span>

## <span data-ttu-id="94fc6-179">注释</span><span class="sxs-lookup"><span data-stu-id="94fc6-179">NOTES</span></span>

<span data-ttu-id="94fc6-180">`Format-Custom` 旨在显示不只是表格或只是列表的视图。</span><span class="sxs-lookup"><span data-stu-id="94fc6-180">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="94fc6-181">若要显示替代表视图，请使用 `Format-Table` 。</span><span class="sxs-lookup"><span data-stu-id="94fc6-181">To display an alternate table view, use `Format-Table`.</span></span> <span data-ttu-id="94fc6-182">若要显示替代列表视图，请使用 `Format-List` 。</span><span class="sxs-lookup"><span data-stu-id="94fc6-182">To display an alternate list view, use `Format-List`.</span></span>

<span data-ttu-id="94fc6-183">还可以 `Format-Custom` 通过其内置别名来引用 `fc` 。</span><span class="sxs-lookup"><span data-stu-id="94fc6-183">You can also refer to `Format-Custom` by its built-in alias, `fc`.</span></span> <span data-ttu-id="94fc6-184">有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="94fc6-184">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="94fc6-185">**GroupBy** 参数假定对象已排序。</span><span class="sxs-lookup"><span data-stu-id="94fc6-185">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="94fc6-186">使用对 `Format-Custom` 对象进行分组之前，请使用对 `Sort-Object` 它们进行排序。</span><span class="sxs-lookup"><span data-stu-id="94fc6-186">Before using `Format-Custom` to group the objects, use `Sort-Object` to sort them.</span></span>

## <span data-ttu-id="94fc6-187">相关链接</span><span class="sxs-lookup"><span data-stu-id="94fc6-187">RELATED LINKS</span></span>

[<span data-ttu-id="94fc6-188">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="94fc6-188">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="94fc6-189">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="94fc6-189">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="94fc6-190">Format-List</span><span class="sxs-lookup"><span data-stu-id="94fc6-190">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="94fc6-191">Format-Table</span><span class="sxs-lookup"><span data-stu-id="94fc6-191">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="94fc6-192">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="94fc6-192">Format-Wide</span></span>](Format-Wide.md)

[<span data-ttu-id="94fc6-193">Get-Process</span><span class="sxs-lookup"><span data-stu-id="94fc6-193">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
