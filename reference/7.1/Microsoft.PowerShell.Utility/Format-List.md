---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/19/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-list?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-List
ms.openlocfilehash: a025432e8aed93f6668c676161c21377d0ba225c
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "93199298"
---
# <span data-ttu-id="c4771-103">Format-List</span><span class="sxs-lookup"><span data-stu-id="c4771-103">Format-List</span></span>

## <span data-ttu-id="c4771-104">摘要</span><span class="sxs-lookup"><span data-stu-id="c4771-104">SYNOPSIS</span></span>
<span data-ttu-id="c4771-105">将输出的格式设置为属性列表，其中每个属性都显示在一个新行上。</span><span class="sxs-lookup"><span data-stu-id="c4771-105">Formats the output as a list of properties in which each property appears on a new line.</span></span>

## <span data-ttu-id="c4771-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c4771-106">SYNTAX</span></span>

```
Format-List [[-Property] <Object[]>] [-GroupBy <Object>] [-View <string>] [-ShowError]
[-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>] [<CommonParameters>]
```

## <span data-ttu-id="c4771-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c4771-107">DESCRIPTION</span></span>

<span data-ttu-id="c4771-108">`Format-List`Cmdlet 将命令输出的格式设置为属性列表，其中每个属性都显示在单独的行上。</span><span class="sxs-lookup"><span data-stu-id="c4771-108">The `Format-List` cmdlet formats the output of a command as a list of properties in which each property is displayed on a separate line.</span></span> <span data-ttu-id="c4771-109">您可以使用 `Format-List` 将对象的全部或所选属性的格式设置为列表 (格式列表 \* ) 。</span><span class="sxs-lookup"><span data-stu-id="c4771-109">You can use `Format-List` to format and display all or selected properties of an object as a list (format-list \*).</span></span>

<span data-ttu-id="c4771-110">由于列表中的每个项都有更多可用空间，因此 PowerShell 将在列表中显示该对象的更多属性，并且属性值不太可能被截断。</span><span class="sxs-lookup"><span data-stu-id="c4771-110">Because more space is available for each item in a list than in a table, PowerShell displays more properties of the object in the list, and the property values are less likely to be truncated.</span></span>

## <span data-ttu-id="c4771-111">示例</span><span class="sxs-lookup"><span data-stu-id="c4771-111">EXAMPLES</span></span>

### <span data-ttu-id="c4771-112">示例1：格式化计算机服务</span><span class="sxs-lookup"><span data-stu-id="c4771-112">Example 1: Format computer services</span></span>

```powershell
Get-Service | Format-List
```

<span data-ttu-id="c4771-113">此命令将计算机上服务的相关信息的格式设置为列表。</span><span class="sxs-lookup"><span data-stu-id="c4771-113">This command formats information about services on the computer as a list.</span></span> <span data-ttu-id="c4771-114">默认情况下，将这些服务的格式设置为表。</span><span class="sxs-lookup"><span data-stu-id="c4771-114">By default, the services are formatted as a table.</span></span> <span data-ttu-id="c4771-115">`Get-Service`Cmdlet 将获取表示计算机上的服务的对象。</span><span class="sxs-lookup"><span data-stu-id="c4771-115">The `Get-Service` cmdlet gets objects representing the services on the computer.</span></span> <span data-ttu-id="c4771-116">管道运算符 (|) 通过管道将结果传递给 `Format-List` 。</span><span class="sxs-lookup"><span data-stu-id="c4771-116">The pipeline operator (|) passes the results through the pipeline to `Format-List`.</span></span>
<span data-ttu-id="c4771-117">然后，该 `Format-List` 命令将服务信息的格式设置为列表，并将其发送到默认的输出 cmdlet 以供显示。</span><span class="sxs-lookup"><span data-stu-id="c4771-117">Then, the `Format-List` command formats the service information in a list and sends it to the default output cmdlet for display.</span></span>

### <span data-ttu-id="c4771-118">示例2：格式化 TYPES.PS1XML 文件</span><span class="sxs-lookup"><span data-stu-id="c4771-118">Example 2: Format PS1XML files</span></span>

<span data-ttu-id="c4771-119">这些命令以列表的形式显示有关 PowerShell 目录中的 TYPES.PS1XML 文件的信息。</span><span class="sxs-lookup"><span data-stu-id="c4771-119">These commands display information about the PS1XML files in the PowerShell directory as a list.</span></span>

```powershell
$A = Get-ChildItem $pshome\*.ps1xml
Format-List -InputObject $A
```

<span data-ttu-id="c4771-120">第一个命令获取表示文件的对象，并将其存储在 `$A` 变量中。</span><span class="sxs-lookup"><span data-stu-id="c4771-120">The first command gets the objects representing the files and stores them in the `$A` variable.</span></span>

<span data-ttu-id="c4771-121">第二个命令使用 `Format-List` 来设置有关存储在中的对象的信息的格式 `$A` 。</span><span class="sxs-lookup"><span data-stu-id="c4771-121">The second command uses `Format-List` to format information about objects stored in `$A`.</span></span> <span data-ttu-id="c4771-122">此命令使用 **InputObject** 参数将该变量传递给 `Format-List` ，后者随后会将格式化输出发送到默认的输出 cmdlet 以供显示。</span><span class="sxs-lookup"><span data-stu-id="c4771-122">This command uses the **InputObject** parameter to pass the variable to `Format-List`, which then sends the formatted output to the default output cmdlet for display.</span></span>

### <span data-ttu-id="c4771-123">示例3：按名称设置进程属性的格式</span><span class="sxs-lookup"><span data-stu-id="c4771-123">Example 3: Format process properties by name</span></span>

<span data-ttu-id="c4771-124">此命令将显示计算机上每个进程的名称、基本优先级和优先级类。</span><span class="sxs-lookup"><span data-stu-id="c4771-124">This command displays the name, base priority, and priority class of each process on the computer.</span></span>

```powershell
Get-Process | Format-List -Property name, basepriority, priorityclass
```

<span data-ttu-id="c4771-125">它使用 `Get-Process` cmdlet 来获取表示每个进程的对象。</span><span class="sxs-lookup"><span data-stu-id="c4771-125">It uses the `Get-Process` cmdlet to get an object representing each process.</span></span> <span data-ttu-id="c4771-126">管道运算符 (|) 将进程对象通过管道传递给 `Format-List` 。</span><span class="sxs-lookup"><span data-stu-id="c4771-126">The pipeline operator (|) passes the process objects through the pipeline to `Format-List`.</span></span> <span data-ttu-id="c4771-127">`Format-List` 将进程的格式设置为指定属性的列表。</span><span class="sxs-lookup"><span data-stu-id="c4771-127">`Format-List` formats the processes as a list of the specified properties.</span></span> <span data-ttu-id="c4771-128">*属性* 参数名称是可选的，因此可以省略它。</span><span class="sxs-lookup"><span data-stu-id="c4771-128">The *Property* parameter name is optional, so you can omit it.</span></span>

### <span data-ttu-id="c4771-129">示例4：设置进程的所有属性的格式</span><span class="sxs-lookup"><span data-stu-id="c4771-129">Example 4: Format all properties for a process</span></span>

<span data-ttu-id="c4771-130">此命令显示 Winlogon 进程的所有属性。</span><span class="sxs-lookup"><span data-stu-id="c4771-130">This command displays all of the properties of the Winlogon process.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="c4771-131">它使用 Get-Process cmdlet 来获取表示 Winlogon 进程的对象。</span><span class="sxs-lookup"><span data-stu-id="c4771-131">It uses the Get-Process cmdlet to get an object representing the Winlogon process.</span></span> <span data-ttu-id="c4771-132">管道运算符 (|) 通过管道将 Winlogon 进程对象传递给 `Format-List` 。</span><span class="sxs-lookup"><span data-stu-id="c4771-132">The pipeline operator (|) passes the Winlogon process object through the pipeline to `Format-List`.</span></span> <span data-ttu-id="c4771-133">该命令使用 *Property* 参数来指定属性，并使用 \* 来指示所有属性。</span><span class="sxs-lookup"><span data-stu-id="c4771-133">The command uses the *Property* parameter to specify the properties and the \* to indicate all properties.</span></span>
<span data-ttu-id="c4771-134">因为 *属性* 参数的名称是可选的，所以可以省略它，然后将命令键入为 `Format-List *` 。</span><span class="sxs-lookup"><span data-stu-id="c4771-134">Because the name of the *Property* parameter is optional, you can omit it and type the command as `Format-List *`.</span></span> <span data-ttu-id="c4771-135">`Format-List` 自动将结果发送到默认的输出 cmdlet 以供显示。</span><span class="sxs-lookup"><span data-stu-id="c4771-135">`Format-List` automatically sends the results to the default output cmdlet for display.</span></span>

### <span data-ttu-id="c4771-136">示例5：排查格式错误</span><span class="sxs-lookup"><span data-stu-id="c4771-136">Example 5: Troubleshooting format errors</span></span>

<span data-ttu-id="c4771-137">下面的示例显示了使用表达式添加 **DisplayError** 或 **ShowError** 参数的结果。</span><span class="sxs-lookup"><span data-stu-id="c4771-137">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -DisplayError

DayOfWeek    : Friday
 $_ / $null  : #ERR

PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -ShowError

DayOfWeek    : Friday
 $_ / $null  :

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 7:59:23 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="c4771-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c4771-138">PARAMETERS</span></span>

### <span data-ttu-id="c4771-139">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="c4771-139">-DisplayError</span></span>

<span data-ttu-id="c4771-140">指示此 cmdlet 在命令行中显示错误。</span><span class="sxs-lookup"><span data-stu-id="c4771-140">Indicates that this cmdlet displays errors at the command line.</span></span> <span data-ttu-id="c4771-141">此参数很少使用，但当你在命令中设置表达式的格式 `Format-List` ，并且表达式似乎无法正常工作时，可将其用作调试帮助。</span><span class="sxs-lookup"><span data-stu-id="c4771-141">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="c4771-142">-Expand</span><span class="sxs-lookup"><span data-stu-id="c4771-142">-Expand</span></span>

<span data-ttu-id="c4771-143">指定格式化的集合对象以及集合中的对象。</span><span class="sxs-lookup"><span data-stu-id="c4771-143">Specifies the formatted collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="c4771-144">此参数旨在用于设置支持 ICollection (System.Collections) 接口的对象的格式。</span><span class="sxs-lookup"><span data-stu-id="c4771-144">This parameter is designed to format objects that support the ICollection (System.Collections) interface.</span></span> <span data-ttu-id="c4771-145">默认值为 EnumOnly。</span><span class="sxs-lookup"><span data-stu-id="c4771-145">The default value is EnumOnly.</span></span> <span data-ttu-id="c4771-146">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="c4771-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c4771-147">EnumOnly.</span><span class="sxs-lookup"><span data-stu-id="c4771-147">EnumOnly.</span></span> <span data-ttu-id="c4771-148">显示集合中的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="c4771-148">Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="c4771-149">CoreOnly.</span><span class="sxs-lookup"><span data-stu-id="c4771-149">CoreOnly.</span></span> <span data-ttu-id="c4771-150">显示集合对象的属性。</span><span class="sxs-lookup"><span data-stu-id="c4771-150">Displays the properties of the collection object.</span></span>
- <span data-ttu-id="c4771-151">两者。</span><span class="sxs-lookup"><span data-stu-id="c4771-151">Both.</span></span> <span data-ttu-id="c4771-152">显示集合对象的属性以及集合中的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="c4771-152">Displays the properties of the collection object and the properties of objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c4771-153">-Force</span><span class="sxs-lookup"><span data-stu-id="c4771-153">-Force</span></span>

<span data-ttu-id="c4771-154">指示此 cmdlet 显示所有错误信息。</span><span class="sxs-lookup"><span data-stu-id="c4771-154">Indicates that this cmdlet displays all of the error information.</span></span> <span data-ttu-id="c4771-155">与 **DisplayError** 或 **ShowError** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="c4771-155">Use with the **DisplayError** or **ShowError** parameter.</span></span> <span data-ttu-id="c4771-156">默认情况下，当将错误对象写入到错误或显示流时，仅显示部分错误信息。</span><span class="sxs-lookup"><span data-stu-id="c4771-156">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="c4771-157">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="c4771-157">-GroupBy</span></span>

<span data-ttu-id="c4771-158">基于共享属性或值指定组中的输出。</span><span class="sxs-lookup"><span data-stu-id="c4771-158">Specifies the output in groups based on a shared property or value.</span></span> <span data-ttu-id="c4771-159">请输入表达式或输出的属性。</span><span class="sxs-lookup"><span data-stu-id="c4771-159">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="c4771-160">**GroupBy** 参数的值可以是新的计算属性。</span><span class="sxs-lookup"><span data-stu-id="c4771-160">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="c4771-161">计算属性可以是脚本块，也可以是哈希表。</span><span class="sxs-lookup"><span data-stu-id="c4771-161">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="c4771-162">有效的键-值对为：</span><span class="sxs-lookup"><span data-stu-id="c4771-162">Valid key-value pairs are:</span></span>

- <span data-ttu-id="c4771-163">名称 (或标签) - `<string>`</span><span class="sxs-lookup"><span data-stu-id="c4771-163">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="c4771-164">Expression `<string>` 或 `<script block>`</span><span class="sxs-lookup"><span data-stu-id="c4771-164">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="c4771-165">说明符 `<string>`</span><span class="sxs-lookup"><span data-stu-id="c4771-165">FormatString - `<string>`</span></span>

<span data-ttu-id="c4771-166">有关详细信息，请参阅 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c4771-166">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="c4771-167">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c4771-167">-InputObject</span></span>

<span data-ttu-id="c4771-168">指定要设置格式的对象。</span><span class="sxs-lookup"><span data-stu-id="c4771-168">Specifies the objects to be formatted.</span></span> <span data-ttu-id="c4771-169">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="c4771-169">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="c4771-170">-Property</span><span class="sxs-lookup"><span data-stu-id="c4771-170">-Property</span></span>

<span data-ttu-id="c4771-171">指定要在屏幕上显示的对象属性及其显示顺序。</span><span class="sxs-lookup"><span data-stu-id="c4771-171">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="c4771-172">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="c4771-172">Wildcards are permitted.</span></span>

<span data-ttu-id="c4771-173">如果省略此参数，则屏幕上显示的属性取决于要显示的对象。</span><span class="sxs-lookup"><span data-stu-id="c4771-173">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="c4771-174">参数名称 "Property" 是可选的。</span><span class="sxs-lookup"><span data-stu-id="c4771-174">The parameter name "Property" is optional.</span></span> <span data-ttu-id="c4771-175">不能在同一命令中使用 **Property** 和 **View** 参数。</span><span class="sxs-lookup"><span data-stu-id="c4771-175">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="c4771-176">**Property** 参数的值可以是新的计算属性。</span><span class="sxs-lookup"><span data-stu-id="c4771-176">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="c4771-177">计算属性可以是脚本块，也可以是哈希表。</span><span class="sxs-lookup"><span data-stu-id="c4771-177">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="c4771-178">有效的键-值对为：</span><span class="sxs-lookup"><span data-stu-id="c4771-178">Valid key-value pairs are:</span></span>

- <span data-ttu-id="c4771-179">名称 (或标签) - `<string>`</span><span class="sxs-lookup"><span data-stu-id="c4771-179">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="c4771-180">Expression `<string>` 或 `<script block>`</span><span class="sxs-lookup"><span data-stu-id="c4771-180">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="c4771-181">说明符 `<string>`</span><span class="sxs-lookup"><span data-stu-id="c4771-181">FormatString - `<string>`</span></span>

<span data-ttu-id="c4771-182">有关详细信息，请参阅 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c4771-182">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="c4771-183">-ShowError</span><span class="sxs-lookup"><span data-stu-id="c4771-183">-ShowError</span></span>

<span data-ttu-id="c4771-184">指示 cmdlet 通过管道发送错误。</span><span class="sxs-lookup"><span data-stu-id="c4771-184">Indicates that the cmdlet sends errors through the pipeline.</span></span> <span data-ttu-id="c4771-185">此参数很少使用，但当你在命令中设置表达式的格式 `Format-List` ，并且表达式似乎无法正常工作时，可将其用作调试帮助。</span><span class="sxs-lookup"><span data-stu-id="c4771-185">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="c4771-186">-View</span><span class="sxs-lookup"><span data-stu-id="c4771-186">-View</span></span>

<span data-ttu-id="c4771-187">指定替代列表格式或视图的名称。</span><span class="sxs-lookup"><span data-stu-id="c4771-187">Specifies the name of an alternate list format or view.</span></span> <span data-ttu-id="c4771-188">不能在同一命令中使用 **Property** 和 **View** 参数。</span><span class="sxs-lookup"><span data-stu-id="c4771-188">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="c4771-189">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c4771-189">CommonParameters</span></span>

<span data-ttu-id="c4771-190">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="c4771-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c4771-191">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="c4771-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c4771-192">输入</span><span class="sxs-lookup"><span data-stu-id="c4771-192">INPUTS</span></span>

### <span data-ttu-id="c4771-193">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="c4771-193">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="c4771-194">可以通过管道将任何对象传递给 `Format-List` 。</span><span class="sxs-lookup"><span data-stu-id="c4771-194">You can pipe any object to `Format-List`.</span></span>

## <span data-ttu-id="c4771-195">输出</span><span class="sxs-lookup"><span data-stu-id="c4771-195">OUTPUTS</span></span>

### <span data-ttu-id="c4771-196">Microsoft.PowerShell.Commands.Internal.Format</span><span class="sxs-lookup"><span data-stu-id="c4771-196">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="c4771-197">`Format-List` 返回表示列表的格式对象。</span><span class="sxs-lookup"><span data-stu-id="c4771-197">`Format-List` returns the format objects that represent the list.</span></span>

## <span data-ttu-id="c4771-198">注释</span><span class="sxs-lookup"><span data-stu-id="c4771-198">NOTES</span></span>

<span data-ttu-id="c4771-199">你还可以通过其内置别名 FL 来引用 Format-List。</span><span class="sxs-lookup"><span data-stu-id="c4771-199">You can also refer to Format-List by its built-in alias, FL.</span></span> <span data-ttu-id="c4771-200">有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="c4771-200">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="c4771-201">格式 cmdlet （例如 `Format-List` ）用于排列要显示的数据，但不显示。</span><span class="sxs-lookup"><span data-stu-id="c4771-201">The format cmdlets, such as `Format-List`, arrange the data to be displayed but do not display it.</span></span>
<span data-ttu-id="c4771-202">数据由 PowerShell 的输出功能以及包含 out cmdlet (Out) （如或）的 cmdlet 显示 `Out-Host` `Out-File` 。</span><span class="sxs-lookup"><span data-stu-id="c4771-202">The data is displayed by the output features of PowerShell and by the cmdlets that contain the Out verb (the Out cmdlets), such as `Out-Host` or `Out-File`.</span></span>

<span data-ttu-id="c4771-203">如果未使用格式 cmdlet，则 PowerShell 会将其显示的每个对象应用默认格式。</span><span class="sxs-lookup"><span data-stu-id="c4771-203">If you do not use a format cmdlet, PowerShell applies that default format for each object that it displays.</span></span>

<span data-ttu-id="c4771-204">**GroupBy** 参数假定对象已排序。</span><span class="sxs-lookup"><span data-stu-id="c4771-204">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="c4771-205">使用 Sort-Object，然后使用 `Format-List` 将对象分组。</span><span class="sxs-lookup"><span data-stu-id="c4771-205">Use Sort-Object before using `Format-List` to group the objects.</span></span>

<span data-ttu-id="c4771-206">使用 **View** 参数可以指定表的替代格式。</span><span class="sxs-lookup"><span data-stu-id="c4771-206">The **View** parameter lets you specify an alternate format for the table.</span></span> <span data-ttu-id="c4771-207">你可以使用 PowerShell 目录的文件中定义的视图 `*.format.PS1XML` ，也可以在新的 types.ps1xml 文件中创建你自己的视图，并使用 Update-FormatData cmdlet 将它们包含在 powershell 中。</span><span class="sxs-lookup"><span data-stu-id="c4771-207">You can use the views defined in the `*.format.PS1XML` files in the PowerShell directory, or you can create your own views in new PS1XML files and use the Update-FormatData cmdlet to include them in PowerShell.</span></span>

<span data-ttu-id="c4771-208">**View** 参数的替代视图必须使用列表格式，否则，该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="c4771-208">The alternate view for the **View** parameter must use the list format, otherwise, the command fails.</span></span> <span data-ttu-id="c4771-209">如果替代视图是一个表，则使用 `Format-Table` 。</span><span class="sxs-lookup"><span data-stu-id="c4771-209">If the alternate view is a table, use `Format-Table`.</span></span> <span data-ttu-id="c4771-210">如果替代视图不是列表或表，请使用 `Format-Custom` 。</span><span class="sxs-lookup"><span data-stu-id="c4771-210">If the alternate view is not a list or a table, use `Format-Custom`.</span></span>

## <span data-ttu-id="c4771-211">相关链接</span><span class="sxs-lookup"><span data-stu-id="c4771-211">RELATED LINKS</span></span>

[<span data-ttu-id="c4771-212">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="c4771-212">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="c4771-213">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="c4771-213">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="c4771-214">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="c4771-214">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="c4771-215">Format-Table</span><span class="sxs-lookup"><span data-stu-id="c4771-215">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="c4771-216">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="c4771-216">Format-Wide</span></span>](Format-Wide.md)
