---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-host?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Host
ms.openlocfilehash: 47a4d9bb66e3e6c3267bbdf18f41c8af8e5448f0
ms.sourcegitcommit: 758e6dbb428295698d4852b3e19f5d03deade037
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "93199417"
---
# <span data-ttu-id="428e5-103">Write-Host</span><span class="sxs-lookup"><span data-stu-id="428e5-103">Write-Host</span></span>

## <span data-ttu-id="428e5-104">摘要</span><span class="sxs-lookup"><span data-stu-id="428e5-104">SYNOPSIS</span></span>

<span data-ttu-id="428e5-105">将自定义的输出写入主机。</span><span class="sxs-lookup"><span data-stu-id="428e5-105">Writes customized output to a host.</span></span>

## <span data-ttu-id="428e5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="428e5-106">SYNTAX</span></span>

```
Write-Host [[-Object] <Object>] [-NoNewline] [-Separator <Object>] [-ForegroundColor <ConsoleColor>]
 [-BackgroundColor <ConsoleColor>] [<CommonParameters>]
```

## <span data-ttu-id="428e5-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="428e5-107">DESCRIPTION</span></span>

<span data-ttu-id="428e5-108">此 `Write-Host` cmdlet 的主要用途是生成 (主机) 只显示输出，例如，在提示用户输入与 [读取主机](Read-Host.md)的输入时打印彩色文本（例如）。</span><span class="sxs-lookup"><span data-stu-id="428e5-108">The `Write-Host` cmdlet's primary purpose is to produce for-(host)-display-only output, such as printing colored text like when prompting the user for input in conjunction with [Read-Host](Read-Host.md).</span></span>
<span data-ttu-id="428e5-109">`Write-Host` 使用 [ToString ( # B1 ](/dotnet/api/system.object.tostring) 方法来写入输出。</span><span class="sxs-lookup"><span data-stu-id="428e5-109">`Write-Host` uses the [ToString()](/dotnet/api/system.object.tostring) method to write the output.</span></span> <span data-ttu-id="428e5-110">与此相反，若要将数据输出到管道，请使用 [写入输出](Write-Output.md) 或隐式输出。</span><span class="sxs-lookup"><span data-stu-id="428e5-110">By contrast, to output data to the pipeline, use [Write-Output](Write-Output.md) or implicit output.</span></span>

<span data-ttu-id="428e5-111">可以通过使用参数指定文本颜色 `ForegroundColor` ，也可以使用参数指定背景色 `BackgroundColor` 。</span><span class="sxs-lookup"><span data-stu-id="428e5-111">You can specify the color of text by using the `ForegroundColor` parameter, and you can specify the background color by using the `BackgroundColor` parameter.</span></span> <span data-ttu-id="428e5-112">Separator 参数允许你指定用于分隔显示对象的字符串。</span><span class="sxs-lookup"><span data-stu-id="428e5-112">The Separator parameter lets you specify a string to use to separate displayed objects.</span></span> <span data-ttu-id="428e5-113">具体的结果取决于托管 PowerShell 的程序。</span><span class="sxs-lookup"><span data-stu-id="428e5-113">The particular result depends on the program that is hosting PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="428e5-114">从 Windows PowerShell 5.0 开始， `Write-Host` 是的包装器， `Write-Information` 它允许你使用 `Write-Host` 向信息流发出输出。</span><span class="sxs-lookup"><span data-stu-id="428e5-114">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="428e5-115">这样就可以 **捕获** 或 **抑制** 使用编写的数据， `Write-Host` 同时保留向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="428e5-115">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span>
>
> <span data-ttu-id="428e5-116">`$InformationPreference`首选项变量和 `InformationAction` 通用参数不会影响 `Write-Host` 消息。</span><span class="sxs-lookup"><span data-stu-id="428e5-116">The `$InformationPreference` preference variable and `InformationAction` common parameter do not affect `Write-Host` messages.</span></span> <span data-ttu-id="428e5-117">此规则的例外情况是 `-InformationAction Ignore` ，它可以有效地取消 `Write-Host` 输出。</span><span class="sxs-lookup"><span data-stu-id="428e5-117">The exception to this rule is `-InformationAction Ignore`, which effectively suppresses `Write-Host` output.</span></span> <span data-ttu-id="428e5-118"> (参见 "Example 5" ) </span><span class="sxs-lookup"><span data-stu-id="428e5-118">(see "Example 5")</span></span>

## <span data-ttu-id="428e5-119">示例</span><span class="sxs-lookup"><span data-stu-id="428e5-119">EXAMPLES</span></span>

### <span data-ttu-id="428e5-120">示例1：写入控制台而不添加新行</span><span class="sxs-lookup"><span data-stu-id="428e5-120">Example 1: Write to the console without adding a new line</span></span>

```powershell
Write-Host "no newline test " -NoNewline
Write-Host "second string"
```

```output
no newline test second string
```

<span data-ttu-id="428e5-121">此命令显示具有参数的字符串 "no 换行符 test" `NoNewline` 。</span><span class="sxs-lookup"><span data-stu-id="428e5-121">This command displays the string 'no newline test' with the `NoNewline` parameter.</span></span>

<span data-ttu-id="428e5-122">写入第二个字符串，但该字符串最终与第一个字符串在同一行上，因为缺少分隔字符串的换行符。</span><span class="sxs-lookup"><span data-stu-id="428e5-122">A second string is written, but it ends up on the same line as the first due to the absence of a newline separating the strings.</span></span>

### <span data-ttu-id="428e5-123">示例2：写入控制台并包含分隔符</span><span class="sxs-lookup"><span data-stu-id="428e5-123">Example 2: Write to the console and include a separator</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", +2= "
```

```output
2, +2= 4, +2= 6, +2= 8, +2= 10, +2= 12
```

此命令显示从2到12的偶数。 <span data-ttu-id="428e5-125">**Separator** 参数用于添加字符串 `, +2= ` (逗号、空格、 `+` 、、 `2` `=`) 。</span><span class="sxs-lookup"><span data-stu-id="428e5-125">The **Separator** parameter is used to add the string `, +2= ` (comma, space, `+`, `2`, `=`, space).</span></span>

### <span data-ttu-id="428e5-126">示例3：用不同文本和背景色编写</span><span class="sxs-lookup"><span data-stu-id="428e5-126">Example 3: Write with different text and background colors</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", -> " -ForegroundColor DarkGreen -BackgroundColor White
```

```output
2, -> 4, -> 6, -> 8, -> 10, -> 12
```

<span data-ttu-id="428e5-127">此命令显示从2到12的偶数。</span><span class="sxs-lookup"><span data-stu-id="428e5-127">This command displays the even numbers from two through twelve.</span></span> <span data-ttu-id="428e5-128">它使用 `ForegroundColor` 参数来输出深绿色文本，并使用 `BackgroundColor` 参数来显示白色背景。</span><span class="sxs-lookup"><span data-stu-id="428e5-128">It uses the `ForegroundColor` parameter to output dark green text and the `BackgroundColor` parameter to display a white background.</span></span>

### <span data-ttu-id="428e5-129">示例4：用不同文本和背景色编写</span><span class="sxs-lookup"><span data-stu-id="428e5-129">Example 4: Write with different text and background colors</span></span>

```powershell
Write-Host "Red on white text." -ForegroundColor red -BackgroundColor white
```

```output
Red on white text.
```

<span data-ttu-id="428e5-130">此命令显示字符串“Red on white text”。</span><span class="sxs-lookup"><span data-stu-id="428e5-130">This command displays the string "Red on white text."</span></span> <span data-ttu-id="428e5-131">文本为红色，由 `ForegroundColor` 参数定义。</span><span class="sxs-lookup"><span data-stu-id="428e5-131">The text is red, as defined by the `ForegroundColor` parameter.</span></span> <span data-ttu-id="428e5-132">背景为白色，由 `BackgroundColor` 参数定义。</span><span class="sxs-lookup"><span data-stu-id="428e5-132">The background is white, as defined by the `BackgroundColor` parameter.</span></span>

### <span data-ttu-id="428e5-133">示例5：取消 Write-Host 的输出</span><span class="sxs-lookup"><span data-stu-id="428e5-133">Example 5: Suppress output from Write-Host</span></span>

```powershell
# The following two statements can be used to effectively suppress output from Write-Host
Write-Host "I won't print" -InformationAction Ignore
Write-Host "I won't print" 6>$null
```

```output

```

<span data-ttu-id="428e5-134">这些命令可以有效地取消 cmdlet 的输出 `Write-Host` 。</span><span class="sxs-lookup"><span data-stu-id="428e5-134">These commands effectively suppress output of the `Write-Host` cmdlet.</span></span> <span data-ttu-id="428e5-135">第一个 `InformationAction` 参数将参数与值一起使用， `Ignore` 以禁止输出到信息流。</span><span class="sxs-lookup"><span data-stu-id="428e5-135">The first one uses the `InformationAction` parameter with the `Ignore` Value to suppress output to the information stream.</span></span>
<span data-ttu-id="428e5-136">第二个示例将命令的信息流重定向到 `$null` 变量，从而禁止显示。</span><span class="sxs-lookup"><span data-stu-id="428e5-136">The second example redirects the information stream of the command to the `$null` variable and thereby suppresses it.</span></span>

## <span data-ttu-id="428e5-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="428e5-137">PARAMETERS</span></span>

### <span data-ttu-id="428e5-138">-BackgroundColor</span><span class="sxs-lookup"><span data-stu-id="428e5-138">-BackgroundColor</span></span>

<span data-ttu-id="428e5-139">指定背景色。</span><span class="sxs-lookup"><span data-stu-id="428e5-139">Specifies the background color.</span></span> <span data-ttu-id="428e5-140">没有默认值。</span><span class="sxs-lookup"><span data-stu-id="428e5-140">There is no default.</span></span> <span data-ttu-id="428e5-141">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="428e5-141">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="428e5-142">黑色</span><span class="sxs-lookup"><span data-stu-id="428e5-142">Black</span></span>
- <span data-ttu-id="428e5-143">深蓝色</span><span class="sxs-lookup"><span data-stu-id="428e5-143">DarkBlue</span></span>
- <span data-ttu-id="428e5-144">深绿色</span><span class="sxs-lookup"><span data-stu-id="428e5-144">DarkGreen</span></span>
- <span data-ttu-id="428e5-145">深青色</span><span class="sxs-lookup"><span data-stu-id="428e5-145">DarkCyan</span></span>
- <span data-ttu-id="428e5-146">深红色</span><span class="sxs-lookup"><span data-stu-id="428e5-146">DarkRed</span></span>
- <span data-ttu-id="428e5-147">深洋红色</span><span class="sxs-lookup"><span data-stu-id="428e5-147">DarkMagenta</span></span>
- <span data-ttu-id="428e5-148">深黄色</span><span class="sxs-lookup"><span data-stu-id="428e5-148">DarkYellow</span></span>
- <span data-ttu-id="428e5-149">灰色</span><span class="sxs-lookup"><span data-stu-id="428e5-149">Gray</span></span>
- <span data-ttu-id="428e5-150">深灰色</span><span class="sxs-lookup"><span data-stu-id="428e5-150">DarkGray</span></span>
- <span data-ttu-id="428e5-151">蓝色</span><span class="sxs-lookup"><span data-stu-id="428e5-151">Blue</span></span>
- <span data-ttu-id="428e5-152">绿色</span><span class="sxs-lookup"><span data-stu-id="428e5-152">Green</span></span>
- <span data-ttu-id="428e5-153">蓝</span><span class="sxs-lookup"><span data-stu-id="428e5-153">Cyan</span></span>
- <span data-ttu-id="428e5-154">Red</span><span class="sxs-lookup"><span data-stu-id="428e5-154">Red</span></span>
- <span data-ttu-id="428e5-155">洋红色</span><span class="sxs-lookup"><span data-stu-id="428e5-155">Magenta</span></span>
- <span data-ttu-id="428e5-156">Yellow</span><span class="sxs-lookup"><span data-stu-id="428e5-156">Yellow</span></span>
- <span data-ttu-id="428e5-157">白色</span><span class="sxs-lookup"><span data-stu-id="428e5-157">White</span></span>

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="428e5-158">-ForegroundColor</span><span class="sxs-lookup"><span data-stu-id="428e5-158">-ForegroundColor</span></span>

<span data-ttu-id="428e5-159">指定文本颜色。</span><span class="sxs-lookup"><span data-stu-id="428e5-159">Specifies the text color.</span></span> <span data-ttu-id="428e5-160">没有默认值。</span><span class="sxs-lookup"><span data-stu-id="428e5-160">There is no default.</span></span> <span data-ttu-id="428e5-161">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="428e5-161">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="428e5-162">黑色</span><span class="sxs-lookup"><span data-stu-id="428e5-162">Black</span></span>
- <span data-ttu-id="428e5-163">深蓝色</span><span class="sxs-lookup"><span data-stu-id="428e5-163">DarkBlue</span></span>
- <span data-ttu-id="428e5-164">深绿色</span><span class="sxs-lookup"><span data-stu-id="428e5-164">DarkGreen</span></span>
- <span data-ttu-id="428e5-165">深青色</span><span class="sxs-lookup"><span data-stu-id="428e5-165">DarkCyan</span></span>
- <span data-ttu-id="428e5-166">深红色</span><span class="sxs-lookup"><span data-stu-id="428e5-166">DarkRed</span></span>
- <span data-ttu-id="428e5-167">深洋红色</span><span class="sxs-lookup"><span data-stu-id="428e5-167">DarkMagenta</span></span>
- <span data-ttu-id="428e5-168">深黄色</span><span class="sxs-lookup"><span data-stu-id="428e5-168">DarkYellow</span></span>
- <span data-ttu-id="428e5-169">灰色</span><span class="sxs-lookup"><span data-stu-id="428e5-169">Gray</span></span>
- <span data-ttu-id="428e5-170">深灰色</span><span class="sxs-lookup"><span data-stu-id="428e5-170">DarkGray</span></span>
- <span data-ttu-id="428e5-171">蓝色</span><span class="sxs-lookup"><span data-stu-id="428e5-171">Blue</span></span>
- <span data-ttu-id="428e5-172">绿色</span><span class="sxs-lookup"><span data-stu-id="428e5-172">Green</span></span>
- <span data-ttu-id="428e5-173">蓝</span><span class="sxs-lookup"><span data-stu-id="428e5-173">Cyan</span></span>
- <span data-ttu-id="428e5-174">Red</span><span class="sxs-lookup"><span data-stu-id="428e5-174">Red</span></span>
- <span data-ttu-id="428e5-175">洋红色</span><span class="sxs-lookup"><span data-stu-id="428e5-175">Magenta</span></span>
- <span data-ttu-id="428e5-176">Yellow</span><span class="sxs-lookup"><span data-stu-id="428e5-176">Yellow</span></span>
- <span data-ttu-id="428e5-177">白色</span><span class="sxs-lookup"><span data-stu-id="428e5-177">White</span></span>

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="428e5-178">-NoNewline</span><span class="sxs-lookup"><span data-stu-id="428e5-178">-NoNewline</span></span>

<span data-ttu-id="428e5-179">输入对象的字符串表示形式连接起来以形成输出。</span><span class="sxs-lookup"><span data-stu-id="428e5-179">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="428e5-180">不会在输出字符串之间插入空格或换行符。</span><span class="sxs-lookup"><span data-stu-id="428e5-180">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="428e5-181">在最后一个输出字符串之后不添加任何行。</span><span class="sxs-lookup"><span data-stu-id="428e5-181">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="428e5-182">-Object</span><span class="sxs-lookup"><span data-stu-id="428e5-182">-Object</span></span>

<span data-ttu-id="428e5-183">要在主机中显示的对象。</span><span class="sxs-lookup"><span data-stu-id="428e5-183">Objects to display in the host.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg, Message

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="428e5-184">-Separator</span><span class="sxs-lookup"><span data-stu-id="428e5-184">-Separator</span></span>

<span data-ttu-id="428e5-185">指定要在主机显示的对象之间插入的分隔符字符串。</span><span class="sxs-lookup"><span data-stu-id="428e5-185">Specifies a separator string to insert between objects displayed by the host.</span></span>

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

### <span data-ttu-id="428e5-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="428e5-186">CommonParameters</span></span>
<span data-ttu-id="428e5-187">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="428e5-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="428e5-188">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="428e5-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="428e5-189">输入</span><span class="sxs-lookup"><span data-stu-id="428e5-189">INPUTS</span></span>

### <span data-ttu-id="428e5-190">System.Object</span><span class="sxs-lookup"><span data-stu-id="428e5-190">System.Object</span></span>

<span data-ttu-id="428e5-191">可以通过管道将要写入的对象传递给主机。</span><span class="sxs-lookup"><span data-stu-id="428e5-191">You can pipe objects to be written to the host.</span></span>

## <span data-ttu-id="428e5-192">输出</span><span class="sxs-lookup"><span data-stu-id="428e5-192">OUTPUTS</span></span>

### <span data-ttu-id="428e5-193">无</span><span class="sxs-lookup"><span data-stu-id="428e5-193">None</span></span>

<span data-ttu-id="428e5-194">`Write-Host` 将对象发送到主机。</span><span class="sxs-lookup"><span data-stu-id="428e5-194">`Write-Host` sends the objects to the host.</span></span> <span data-ttu-id="428e5-195">它不返回任何对象。</span><span class="sxs-lookup"><span data-stu-id="428e5-195">It does not return any objects.</span></span> <span data-ttu-id="428e5-196">但是，主机 `Write-Host` 会显示发送给它的对象。</span><span class="sxs-lookup"><span data-stu-id="428e5-196">However, the host displays the objects that `Write-Host` sends to it.</span></span>

## <span data-ttu-id="428e5-197">注释</span><span class="sxs-lookup"><span data-stu-id="428e5-197">NOTES</span></span>

- <span data-ttu-id="428e5-198">将集合写入主机时，集合中的元素将打印在由单个空格分隔的同一行中。</span><span class="sxs-lookup"><span data-stu-id="428e5-198">When writing a collection to the host, elements of the collection are printed on the same line separated by a single space.</span></span> <span data-ttu-id="428e5-199">这可以用 **Separator** 参数重写。</span><span class="sxs-lookup"><span data-stu-id="428e5-199">This can be overridden with the **Separator** parameter.</span></span>

- <span data-ttu-id="428e5-200">非基元数据类型（如具有属性的对象）可能导致意外的结果，而不提供有意义的输出。</span><span class="sxs-lookup"><span data-stu-id="428e5-200">Non-primitive data types such as objects with properties can cause unexpected results and not provide meaningful output.</span></span> <span data-ttu-id="428e5-201">例如， `Write-Host @{a = 1; b = 2}` 将打印 `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` 到主机。</span><span class="sxs-lookup"><span data-stu-id="428e5-201">For example, `Write-Host @{a = 1; b = 2}` will print `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` to the host.</span></span>

## <span data-ttu-id="428e5-202">相关链接</span><span class="sxs-lookup"><span data-stu-id="428e5-202">RELATED LINKS</span></span>

[<span data-ttu-id="428e5-203">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="428e5-203">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="428e5-204">Out-Host</span><span class="sxs-lookup"><span data-stu-id="428e5-204">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="428e5-205">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="428e5-205">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="428e5-206">写入错误</span><span class="sxs-lookup"><span data-stu-id="428e5-206">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="428e5-207">Write-Output</span><span class="sxs-lookup"><span data-stu-id="428e5-207">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="428e5-208">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="428e5-208">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="428e5-209">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="428e5-209">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="428e5-210">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="428e5-210">Write-Warning</span></span>](Write-Warning.md)
