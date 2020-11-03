---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-output?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Output
ms.openlocfilehash: ccc72ac961adbcba542a7b8be55ad49df68a5ef6
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "93200504"
---
# <span data-ttu-id="4d0d7-103">Write-Output</span><span class="sxs-lookup"><span data-stu-id="4d0d7-103">Write-Output</span></span>

## <span data-ttu-id="4d0d7-104">摘要</span><span class="sxs-lookup"><span data-stu-id="4d0d7-104">SYNOPSIS</span></span>
<span data-ttu-id="4d0d7-105">将指定的对象发送到管道中的下一个命令。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-105">Sends the specified objects to the next command in the pipeline.</span></span> <span data-ttu-id="4d0d7-106">如果该命令是管道中的最后一个命令，则这些对象将在控制台中显示。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-106">If the command is the last command in the pipeline, the objects are displayed in the console.</span></span>

## <span data-ttu-id="4d0d7-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4d0d7-107">SYNTAX</span></span>

```
Write-Output [-InputObject] <PSObject[]> [-NoEnumerate] [<CommonParameters>]
```

## <span data-ttu-id="4d0d7-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4d0d7-108">DESCRIPTION</span></span>

<span data-ttu-id="4d0d7-109">`Write-Output`Cmdlet 将指定的对象沿管道向下发送到下一个命令。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-109">The `Write-Output` cmdlet sends the specified object down the pipeline to the next command.</span></span>
<span data-ttu-id="4d0d7-110">如果该命令是管道中的最后一个命令，则该对象将在控制台中显示。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-110">If the command is the last command in the pipeline, the object is displayed in the console.</span></span>

<span data-ttu-id="4d0d7-111">`Write-Output` 沿主要管道（也称为 "输出流" 或 "成功管道"）向下发送对象。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-111">`Write-Output` sends objects down the primary pipeline, also known as the "output stream" or the "success pipeline."</span></span> <span data-ttu-id="4d0d7-112">若要通过错误管道向下发送错误对象，请使用 Write-Error。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-112">To send error objects down the error pipeline, use Write-Error.</span></span>

<span data-ttu-id="4d0d7-113">此 cmdlet 通常在脚本中使用，以在控制台上显示字符串和其他对象。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-113">This cmdlet is typically used in scripts to display strings and other objects on the console.</span></span> <span data-ttu-id="4d0d7-114">的内置别名之一是，与 `Write-Output` 使用的 `echo` 其他 shell 类似 `echo` ，默认行为是在管道末尾显示输出。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-114">One of the built-in aliases for `Write-Output` is `echo` and similar to other shells that use `echo`, the default behavior is to display the output at the end of a pipeline.</span></span> <span data-ttu-id="4d0d7-115">在 PowerShell 中，通常不需要在默认情况下显示输出的实例中使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-115">In PowerShell, it is generally not necessary to use the cmdlet in instances where the output is displayed by default.</span></span> <span data-ttu-id="4d0d7-116">例如，`Get-Process | Write-Output` 等效于 `Get-Process`。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-116">For example, `Get-Process | Write-Output` is equivalent to `Get-Process`.</span></span> <span data-ttu-id="4d0d7-117">或 `echo "Home directory: $HOME"` 可以写入 `"Home directory: $HOME"` 。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-117">Or, `echo "Home directory: $HOME"` can be written, `"Home directory: $HOME"`.</span></span>

<span data-ttu-id="4d0d7-118">默认情况下，会 `Write-Output` 枚举提供给 cmdlet 的集合。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-118">By default, `Write-Output` enumerates through collections provided to the cmdlet.</span></span> <span data-ttu-id="4d0d7-119">但是， `Write-Output` 还可用于将集合作为带有 **NoEnumerate** 参数的单个对象向下传递到管道。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-119">However, `Write-Output` can also be used to pass collections down the pipeline as a single object with the **NoEnumerate** parameter.</span></span>

## <span data-ttu-id="4d0d7-120">示例</span><span class="sxs-lookup"><span data-stu-id="4d0d7-120">EXAMPLES</span></span>

### <span data-ttu-id="4d0d7-121">示例1：获取对象并将它们写入控制台</span><span class="sxs-lookup"><span data-stu-id="4d0d7-121">Example 1: Get objects and write them to the console</span></span>

```powershell
$P = Get-Process
Write-Output $P
```

<span data-ttu-id="4d0d7-122">第一个命令获取在计算机上运行的进程，并将其存储在 `$P` 变量中。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-122">The first command gets processes running on the computer and stores them in the `$P` variable.</span></span>

<span data-ttu-id="4d0d7-123">第二个和第三个命令在控制台上显示中的进程对象 `$P` 。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-123">The second and third commands display the process objects in `$P` on the console.</span></span>

### <span data-ttu-id="4d0d7-124">示例2：将输出传递给另一个 cmdlet</span><span class="sxs-lookup"><span data-stu-id="4d0d7-124">Example 2: Pass output to another cmdlet</span></span>

```powershell
Write-Output "test output" | Get-Member
```

<span data-ttu-id="4d0d7-125">此命令通过管道将 "测试输出" 字符串传递给 `Get-Member` cmdlet，该 cmdlet 将显示 **system.object** 类的成员，并演示该字符串是沿管道传递的。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-125">This command pipes the "test output" string to the `Get-Member` cmdlet, which displays the members of the **System.String** class, demonstrating that the string was passed along the pipeline.</span></span>

### <span data-ttu-id="4d0d7-126">示例3：在输出中取消枚举</span><span class="sxs-lookup"><span data-stu-id="4d0d7-126">Example 3: Suppress enumeration in output</span></span>

```powershell
Write-Output 1,2,3 | Measure-Object
```

```Output
Count    : 3
...
```

```powershell
Write-Output 1,2,3 -NoEnumerate | Measure-Object
```

```Output
Count    : 1
...
```

<span data-ttu-id="4d0d7-127">此命令添加 **NoEnumerate** 参数以将集合或数组视为通过管道的单个对象。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-127">This command adds the **NoEnumerate** parameter to treat a collection or array as a single object through the pipeline.</span></span>

## <span data-ttu-id="4d0d7-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4d0d7-128">PARAMETERS</span></span>

### <span data-ttu-id="4d0d7-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4d0d7-129">-InputObject</span></span>

<span data-ttu-id="4d0d7-130">指定要通过管道向下发送的对象。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-130">Specifies the objects to send down the pipeline.</span></span> <span data-ttu-id="4d0d7-131">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-131">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4d0d7-132">-NoEnumerate</span><span class="sxs-lookup"><span data-stu-id="4d0d7-132">-NoEnumerate</span></span>

<span data-ttu-id="4d0d7-133">默认情况下，该 `Write-Output` cmdlet 始终枚举其输出。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-133">By default, the `Write-Output` cmdlet always enumerates its output.</span></span> <span data-ttu-id="4d0d7-134">**NoEnumerate** 参数取消默认行为，并阻止 `Write-Output` 枚举输出。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-134">The **NoEnumerate** parameter suppresses the default behavior, and prevents `Write-Output` from enumerating output.</span></span> <span data-ttu-id="4d0d7-135">如果将命令括在括号中，则 **NoEnumerate** 参数不起作用，因为括号会强制执行枚举。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-135">The **NoEnumerate** parameter has no effect if the command is wrapped in parentheses, because the parentheses force enumeration.</span></span> <span data-ttu-id="4d0d7-136">例如， `(Write-Output 1,2,3)` 仍枚举数组。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-136">For example, `(Write-Output 1,2,3)` still enumerates the array.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d0d7-137">在 PowerShell 6.2 及更高版本中，Windows PowerShell 中的此开关存在问题。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-137">There is an issue with this switch in Windows PowerShell that is fixed in PowerShell 6.2 and above.</span></span> <span data-ttu-id="4d0d7-138">使用 **NoEnumerate** 并显式使用 **InputObject** 参数时，该命令仍会枚举。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-138">When using **NoEnumerate** and explicitly using the **InputObject** parameter, the command still enumerates.</span></span> <span data-ttu-id="4d0d7-139">若要解决此情况，请将 **InputObject** 参数传递 (s) 按位置。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-139">To work around this, pass the **InputObject** argument(s) positionally.</span></span>

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

### <span data-ttu-id="4d0d7-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4d0d7-140">CommonParameters</span></span>

<span data-ttu-id="4d0d7-141">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4d0d7-142">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4d0d7-143">输入</span><span class="sxs-lookup"><span data-stu-id="4d0d7-143">INPUTS</span></span>

### <span data-ttu-id="4d0d7-144">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="4d0d7-144">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="4d0d7-145">可以通过管道将对象传递给 `Write-Output` 。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-145">You can pipe objects to `Write-Output`.</span></span>

## <span data-ttu-id="4d0d7-146">输出</span><span class="sxs-lookup"><span data-stu-id="4d0d7-146">OUTPUTS</span></span>

### <span data-ttu-id="4d0d7-147">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="4d0d7-147">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="4d0d7-148">`Write-Output` 返回作为输入提交的对象。</span><span class="sxs-lookup"><span data-stu-id="4d0d7-148">`Write-Output` returns the objects that are submitted as input.</span></span>

## <span data-ttu-id="4d0d7-149">注释</span><span class="sxs-lookup"><span data-stu-id="4d0d7-149">NOTES</span></span>

## <span data-ttu-id="4d0d7-150">相关链接</span><span class="sxs-lookup"><span data-stu-id="4d0d7-150">RELATED LINKS</span></span>

[<span data-ttu-id="4d0d7-151">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="4d0d7-151">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="4d0d7-152">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="4d0d7-152">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="4d0d7-153">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="4d0d7-153">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="4d0d7-154">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="4d0d7-154">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="4d0d7-155">写入错误</span><span class="sxs-lookup"><span data-stu-id="4d0d7-155">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="4d0d7-156">Write-Host</span><span class="sxs-lookup"><span data-stu-id="4d0d7-156">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="4d0d7-157">Write-Information</span><span class="sxs-lookup"><span data-stu-id="4d0d7-157">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="4d0d7-158">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="4d0d7-158">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="4d0d7-159">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="4d0d7-159">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="4d0d7-160">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="4d0d7-160">Write-Warning</span></span>](Write-Warning.md)
