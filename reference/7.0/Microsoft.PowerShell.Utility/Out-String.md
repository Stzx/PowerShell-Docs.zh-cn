---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-string?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-String
ms.openlocfilehash: a64b11206a0755cedabad2894ecc330fac95a8d5
ms.sourcegitcommit: c8d1ffeab215e74e87ea1b0af8cd606c1a6a80ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "93199464"
---
# <span data-ttu-id="2ea87-103">Out-String</span><span class="sxs-lookup"><span data-stu-id="2ea87-103">Out-String</span></span>

## <span data-ttu-id="2ea87-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2ea87-104">SYNOPSIS</span></span>
<span data-ttu-id="2ea87-105">将输入对象输出为字符串。</span><span class="sxs-lookup"><span data-stu-id="2ea87-105">Outputs input objects as a strings.</span></span>

## <span data-ttu-id="2ea87-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ea87-106">SYNTAX</span></span>

### <span data-ttu-id="2ea87-107">NoNewLineFormatting (默认值) </span><span class="sxs-lookup"><span data-stu-id="2ea87-107">NoNewLineFormatting (Default)</span></span>

```
Out-String [-Width <Int32>] [-NoNewline] [-InputObject <PSObject>] [<CommonParameters>]
```

### <span data-ttu-id="2ea87-108">StreamFormatting</span><span class="sxs-lookup"><span data-stu-id="2ea87-108">StreamFormatting</span></span>

```
Out-String [-Stream] [-Width <Int32>] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="2ea87-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2ea87-109">DESCRIPTION</span></span>

<span data-ttu-id="2ea87-110">`Out-String`Cmdlet 将输入对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="2ea87-110">The `Out-String` cmdlet converts input objects into strings.</span></span> <span data-ttu-id="2ea87-111">默认情况下， `Out-String` 累积字符串并将它们作为单个字符串返回，但你可以使用 **Stream** 参数定向 `Out-String` 到一次返回一行或创建字符串数组。</span><span class="sxs-lookup"><span data-stu-id="2ea87-111">By default, `Out-String` accumulates the strings and returns them as a single string, but you can use the **Stream** parameter to direct `Out-String` to return one line at a time or create and array of strings.</span></span> <span data-ttu-id="2ea87-112">此 cmdlet 用于在对象操作不太方便时像在传统 shell 中一样搜索和操作字符串输出。</span><span class="sxs-lookup"><span data-stu-id="2ea87-112">This cmdlet lets you search and manipulate string output as you would in traditional shells when object manipulation is less convenient.</span></span>

## <span data-ttu-id="2ea87-113">示例</span><span class="sxs-lookup"><span data-stu-id="2ea87-113">EXAMPLES</span></span>

### <span data-ttu-id="2ea87-114">示例1：获取当前区域性并将数据转换为字符串</span><span class="sxs-lookup"><span data-stu-id="2ea87-114">Example 1: Get the current culture and convert the data to strings</span></span>

<span data-ttu-id="2ea87-115">此示例获取当前用户的区域设置，并将对象数据转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="2ea87-115">This example gets the regional settings for the current user and converts the object data to strings.</span></span>

```powershell
$C = Get-Culture | Select-Object -Property *
Out-String -InputObject $C -Width 100
```

```Output
Parent                         : en
LCID                           : 1033
KeyboardLayoutId               : 1033
Name                           : en-US
IetfLanguageTag                : en-US
DisplayName                    : English (United States)
NativeName                     : English (United States)
EnglishName                    : English (United States)
TwoLetterISOLanguageName       : en
ThreeLetterISOLanguageName     : eng
ThreeLetterWindowsLanguageName : ENU
CompareInfo                    : CompareInfo - en-US
TextInfo                       : TextInfo - en-US
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar,
                                 System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False
```

<span data-ttu-id="2ea87-116">`$C`变量存储 **Selected.System。全球化 CultureInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="2ea87-116">The `$C` variable stores a **Selected.System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="2ea87-117">对象是将 `Get-Culture` 管道的输出发送到的结果 `Select-Object` 。</span><span class="sxs-lookup"><span data-stu-id="2ea87-117">The object is the result of `Get-Culture` sending output down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="2ea87-118">**Property** 参数使用星号 (`*`) 通配符来指定对象中包含的所有属性。</span><span class="sxs-lookup"><span data-stu-id="2ea87-118">The **Property** parameter uses an asterisk (`*`) wildcard to specify all properties are contained in the object.</span></span>

<span data-ttu-id="2ea87-119">`Out-String` 使用 **InputObject** 参数指定存储在变量中的 **CultureInfo** 对象 `$C` 。</span><span class="sxs-lookup"><span data-stu-id="2ea87-119">`Out-String` uses the **InputObject** parameter to specify the **CultureInfo** object stored in the `$C` variable.</span></span> <span data-ttu-id="2ea87-120">中的对象 `$C` 将转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="2ea87-120">The objects in `$C` are converted to a string.</span></span>

> [!NOTE]
> <span data-ttu-id="2ea87-121">若要查看 `Out-String` 数组，请将输出存储到变量中，并使用数组索引来查看元素。</span><span class="sxs-lookup"><span data-stu-id="2ea87-121">To view the `Out-String` array, store the output to a variable and use an array index to view the elements.</span></span> <span data-ttu-id="2ea87-122">有关数组索引的详细信息，请参阅 [about_Arrays](../microsoft.powershell.core/about/about_arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="2ea87-122">For more information about the array index, see [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).</span></span>
>
> `$str = Out-String -InputObject $C -Width 100`

### <span data-ttu-id="2ea87-123">示例2：使用对象</span><span class="sxs-lookup"><span data-stu-id="2ea87-123">Example 2: Working with objects</span></span>

<span data-ttu-id="2ea87-124">此示例演示了使用对象和使用字符串之间的差异。</span><span class="sxs-lookup"><span data-stu-id="2ea87-124">This example demonstrates the difference between working with objects and working with strings.</span></span> <span data-ttu-id="2ea87-125">该命令显示一个别名，其中包含文本 **gcm** （的别名） `Get-Command` 。</span><span class="sxs-lookup"><span data-stu-id="2ea87-125">The command displays an alias that includes the text **gcm** , the alias for `Get-Command`.</span></span>

```powershell
Get-Alias | Out-String -Stream | Select-String -Pattern "gcm"
```

```Output
Alias           gcm -> Get-Command
```

<span data-ttu-id="2ea87-126">`Get-Alias` 获取每个别名的 **system.management.automation.aliasinfo** 对象，并沿管道向下发送对象。</span><span class="sxs-lookup"><span data-stu-id="2ea87-126">`Get-Alias` gets the **System.Management.Automation.AliasInfo** objects, one for each alias, and sends the objects down the pipeline.</span></span> <span data-ttu-id="2ea87-127">`Out-String` 使用 **Stream** 参数将每个对象转换为字符串，而不是将所有对象连接到一个字符串。</span><span class="sxs-lookup"><span data-stu-id="2ea87-127">`Out-String` uses the **Stream** parameter to convert each object to a string rather concatenating all the objects into a single string.</span></span> <span data-ttu-id="2ea87-128">**系统** 对象将沿管道向下发送，并 `Select-String` 使用 **Pattern** 参数查找文本 **gcm** 的匹配项。</span><span class="sxs-lookup"><span data-stu-id="2ea87-128">The **System.String** objects are sent down the pipeline and `Select-String` uses the **Pattern** parameter to find matches for the text **gcm** .</span></span>

> [!NOTE]
> <span data-ttu-id="2ea87-129">如果省略 **Stream** 参数，则该命令将显示所有别名，因为 `Select-String` 在返回的 **gcm** 单个字符串中查找文本 gcm `Out-String` 。</span><span class="sxs-lookup"><span data-stu-id="2ea87-129">If you omit the **Stream** parameter, the command displays all the aliases because `Select-String` finds the text **gcm** in the single string that `Out-String` returns.</span></span>

### <span data-ttu-id="2ea87-130">示例3：使用 Width 参数防止截断。</span><span class="sxs-lookup"><span data-stu-id="2ea87-130">Example 3: Use the Width parameter to prevent truncation.</span></span>

<span data-ttu-id="2ea87-131">虽然中的大部分输出 `Out-String` 都被包装到下一行，但在某些情况下，输出在传递到之前会被格式化系统截断 `Out-String` 。</span><span class="sxs-lookup"><span data-stu-id="2ea87-131">While most output from `Out-String` is wrapped to the next line, there are scenarios where the output is truncated by the formatting system before being passed to `Out-String`.</span></span> <span data-ttu-id="2ea87-132">使用 **Width** 参数可避免截断。</span><span class="sxs-lookup"><span data-stu-id="2ea87-132">You can avoid truncation using the **Width** parameter.</span></span>

```powershell
PS> @{TestKey = ('x' * 200)} | Out-String
Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx...

PS> @{TestKey = ('x' * 200)} | Out-String -Width 250

Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## <span data-ttu-id="2ea87-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2ea87-133">PARAMETERS</span></span>

### <span data-ttu-id="2ea87-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2ea87-134">-InputObject</span></span>

<span data-ttu-id="2ea87-135">指定要写入字符串的对象。</span><span class="sxs-lookup"><span data-stu-id="2ea87-135">Specifies the objects to be written to a string.</span></span> <span data-ttu-id="2ea87-136">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="2ea87-136">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="2ea87-137">-NoNewline</span><span class="sxs-lookup"><span data-stu-id="2ea87-137">-NoNewline</span></span>

<span data-ttu-id="2ea87-138">从 PowerShell 格式化程序生成的输出中删除所有换行符。</span><span class="sxs-lookup"><span data-stu-id="2ea87-138">Removes all newlines from output generated by the PowerShell formatter.</span></span> <span data-ttu-id="2ea87-139">保留作为字符串对象一部分的换行符。</span><span class="sxs-lookup"><span data-stu-id="2ea87-139">Newlines that are part of the string objects are preserved.</span></span>

<span data-ttu-id="2ea87-140">此参数是在 PowerShell 6.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="2ea87-140">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoNewLineFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ea87-141">-Stream</span><span class="sxs-lookup"><span data-stu-id="2ea87-141">-Stream</span></span>

<span data-ttu-id="2ea87-142">指示 cmdlet 为输入对象的每一行发送单独的字符串。</span><span class="sxs-lookup"><span data-stu-id="2ea87-142">Indicates that the cmdlet sends a separate string for each line of an input object.</span></span> <span data-ttu-id="2ea87-143">默认情况下，每个对象的字符串都将作为单个字符串进行累积和发送。</span><span class="sxs-lookup"><span data-stu-id="2ea87-143">By default, the strings for each object are accumulated and sent as a single string.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StreamFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ea87-144">-Width</span><span class="sxs-lookup"><span data-stu-id="2ea87-144">-Width</span></span>

<span data-ttu-id="2ea87-145">指定输出的每一行中的字符数。</span><span class="sxs-lookup"><span data-stu-id="2ea87-145">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="2ea87-146">任何其他字符将换行到下一行，或根据所使用的格式化程序 cmdlet 进行截断。</span><span class="sxs-lookup"><span data-stu-id="2ea87-146">Any additional characters are wrapped to the next line or truncated depending on the formatter cmdlet used.</span></span> <span data-ttu-id="2ea87-147">**Width** 参数仅适用于正在设置格式的对象。</span><span class="sxs-lookup"><span data-stu-id="2ea87-147">The **Width** parameter applies only to objects that are being formatted.</span></span> <span data-ttu-id="2ea87-148">如果省略此参数，则由主机程序的特征确定宽度。</span><span class="sxs-lookup"><span data-stu-id="2ea87-148">If you omit this parameter, the width is determined by the characteristics of the host program.</span></span> <span data-ttu-id="2ea87-149">在终端 (console) windows 中，当前窗口宽度用作默认值。</span><span class="sxs-lookup"><span data-stu-id="2ea87-149">In terminal (console) windows, the current window width is used as the default value.</span></span> <span data-ttu-id="2ea87-150">默认情况下，在安装时，PowerShell 控制台 windows 的宽度为80个字符。</span><span class="sxs-lookup"><span data-stu-id="2ea87-150">PowerShell console windows default to a width of 80 characters on installation.</span></span>

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

### <span data-ttu-id="2ea87-151">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2ea87-151">CommonParameters</span></span>

<span data-ttu-id="2ea87-152">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="2ea87-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2ea87-153">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="2ea87-153">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2ea87-154">输入</span><span class="sxs-lookup"><span data-stu-id="2ea87-154">INPUTS</span></span>

### <span data-ttu-id="2ea87-155">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="2ea87-155">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="2ea87-156">可以将对象向下发送到 `Out-String` 。</span><span class="sxs-lookup"><span data-stu-id="2ea87-156">You can send objects down the pipeline to `Out-String`.</span></span>

## <span data-ttu-id="2ea87-157">输出</span><span class="sxs-lookup"><span data-stu-id="2ea87-157">OUTPUTS</span></span>

### <span data-ttu-id="2ea87-158">System.String</span><span class="sxs-lookup"><span data-stu-id="2ea87-158">System.String</span></span>

<span data-ttu-id="2ea87-159">`Out-String` 返回它通过输入对象创建的字符串。</span><span class="sxs-lookup"><span data-stu-id="2ea87-159">`Out-String` returns the string that it creates from the input object.</span></span>

## <span data-ttu-id="2ea87-160">注释</span><span class="sxs-lookup"><span data-stu-id="2ea87-160">NOTES</span></span>

<span data-ttu-id="2ea87-161">包含谓词的 cmdlet `Out` 不设置对象的格式。</span><span class="sxs-lookup"><span data-stu-id="2ea87-161">The cmdlets that contain the `Out` verb don't format objects.</span></span> <span data-ttu-id="2ea87-162">`Out`Cmdlet 将对象发送到指定的显示目标的格式化程序。</span><span class="sxs-lookup"><span data-stu-id="2ea87-162">The `Out` cmdlets send objects to the formatter for the specified display destination.</span></span>

## <span data-ttu-id="2ea87-163">相关链接</span><span class="sxs-lookup"><span data-stu-id="2ea87-163">RELATED LINKS</span></span>

[<span data-ttu-id="2ea87-164">about_Formatting</span><span class="sxs-lookup"><span data-stu-id="2ea87-164">about_Formatting</span></span>](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[<span data-ttu-id="2ea87-165">Out-Default</span><span class="sxs-lookup"><span data-stu-id="2ea87-165">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="2ea87-166">Out-File</span><span class="sxs-lookup"><span data-stu-id="2ea87-166">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="2ea87-167">Out-Host</span><span class="sxs-lookup"><span data-stu-id="2ea87-167">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="2ea87-168">Out-Null</span><span class="sxs-lookup"><span data-stu-id="2ea87-168">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="2ea87-169">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="2ea87-169">Out-GridView</span></span>](Out-GridView.md)

[<span data-ttu-id="2ea87-170">Out-printer</span><span class="sxs-lookup"><span data-stu-id="2ea87-170">Out-Printer</span></span>](Out-Printer.md)
