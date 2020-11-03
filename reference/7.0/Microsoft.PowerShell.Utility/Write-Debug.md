---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 3217a3c67c262f8061963fd1302c6782620e270d
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "93200539"
---
# <span data-ttu-id="512e2-103">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="512e2-103">Write-Debug</span></span>

## <span data-ttu-id="512e2-104">摘要</span><span class="sxs-lookup"><span data-stu-id="512e2-104">SYNOPSIS</span></span>
<span data-ttu-id="512e2-105">将调试消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="512e2-105">Writes a debug message to the console.</span></span>

## <span data-ttu-id="512e2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="512e2-106">SYNTAX</span></span>

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="512e2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="512e2-107">DESCRIPTION</span></span>

<span data-ttu-id="512e2-108">该 `Write-Debug` cmdlet 从脚本或命令中将调试消息写入主机。</span><span class="sxs-lookup"><span data-stu-id="512e2-108">The `Write-Debug` cmdlet writes debug messages to the host from a script or command.</span></span>

<span data-ttu-id="512e2-109">默认情况下，调试消息不会显示在控制台中，但可以使用 **debug** 参数或变量显示它们 `$DebugPreference` 。</span><span class="sxs-lookup"><span data-stu-id="512e2-109">By default, debug messages are not displayed in the console, but you can display them by using the **Debug** parameter or the `$DebugPreference` variable.</span></span>

## <span data-ttu-id="512e2-110">示例</span><span class="sxs-lookup"><span data-stu-id="512e2-110">EXAMPLES</span></span>

### <span data-ttu-id="512e2-111">示例 1：了解 $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="512e2-111">Example 1: Understand $DebugPreference</span></span>

<span data-ttu-id="512e2-112">此示例编写调试消息。</span><span class="sxs-lookup"><span data-stu-id="512e2-112">This example writes a debug message.</span></span>

```powershell
Write-Debug "Cannot open file."
```

<span data-ttu-id="512e2-113">的默认值 `$DebugPreference` 为 **SilentlyContinue** 。</span><span class="sxs-lookup"><span data-stu-id="512e2-113">The default value of `$DebugPreference` is **SilentlyContinue** .</span></span> <span data-ttu-id="512e2-114">因此，该消息不会显示在控制台中。</span><span class="sxs-lookup"><span data-stu-id="512e2-114">Therefore, the message is not displayed in the console.</span></span>

### <span data-ttu-id="512e2-115">示例2：更改 $DebugPreference 的值</span><span class="sxs-lookup"><span data-stu-id="512e2-115">Example 2: Change the value of $DebugPreference</span></span>

<span data-ttu-id="512e2-116">此示例演示更改变量的值的效果 `$DebugPreference` 。</span><span class="sxs-lookup"><span data-stu-id="512e2-116">This example shows the effect of changing the value of the `$DebugPreference` variable.</span></span> <span data-ttu-id="512e2-117">首先，我们显示的当前值 `$DebugPreference` ，并尝试编写调试消息。</span><span class="sxs-lookup"><span data-stu-id="512e2-117">First, we display the current value of `$DebugPreference` and attempt to write a debug message.</span></span> <span data-ttu-id="512e2-118">然后，将的值更改 `$DebugPreference` 为 **Continue** ，这允许显示调试消息。</span><span class="sxs-lookup"><span data-stu-id="512e2-118">Then we change the value of `$DebugPreference` to **Continue** , which allows debug messages to be displayed.</span></span>

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

<span data-ttu-id="512e2-119">有关的详细信息 `$DebugPreference` ，请参阅 [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables)。</span><span class="sxs-lookup"><span data-stu-id="512e2-119">For more information about `$DebugPreference`, see [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span></span>

### <span data-ttu-id="512e2-120">示例3：使用 Debug 参数覆盖 $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="512e2-120">Example 3: Use the Debug parameter to override $DebugPreference</span></span>

<span data-ttu-id="512e2-121">`Test-Debug`函数将变量的值写入 `$DebugPreference` PowerShell 主机和调试流。</span><span class="sxs-lookup"><span data-stu-id="512e2-121">The `Test-Debug` function writes the value of the `$DebugPreference` variable to the PowerShell host and to the Debug stream.</span></span> <span data-ttu-id="512e2-122">在此示例中，我们使用 **Debug** 参数重写 `$DebugPreference` 该值。</span><span class="sxs-lookup"><span data-stu-id="512e2-122">In this example, we use the **Debug** parameter to override the `$DebugPreference` value.</span></span>

```powershell
function Test-Debug {
    [CmdletBinding()]
    param()
    Write-Debug ('$DebugPreference is ' + $DebugPreference)
    Write-Host ('$DebugPreference is ' + $DebugPreference)
}
```

```
PS> Test-Debug
$DebugPreference is SilentlyContinue

PS> Test-Debug -Debug
DEBUG: $DebugPreference is Continue
$DebugPreference is Continue
PS> $DebugPreference
SilentlyContinue
```

<span data-ttu-id="512e2-123">请注意， `$DebugPreference` 当你使用 **Debug** 参数时，的值将更改。</span><span class="sxs-lookup"><span data-stu-id="512e2-123">Notice that the value of `$DebugPreference` changes when you use the **Debug** parameter.</span></span> <span data-ttu-id="512e2-124">此更改只影响函数的作用域。</span><span class="sxs-lookup"><span data-stu-id="512e2-124">This change only affects the scope of the function.</span></span> <span data-ttu-id="512e2-125">此值在函数之外不受影响。</span><span class="sxs-lookup"><span data-stu-id="512e2-125">The value is not affected outside the function.</span></span>

<span data-ttu-id="512e2-126">有关 **Debug** 通用参数的详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="512e2-126">For more information about the **Debug** common parameter, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="512e2-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="512e2-127">PARAMETERS</span></span>

### <span data-ttu-id="512e2-128">-Message</span><span class="sxs-lookup"><span data-stu-id="512e2-128">-Message</span></span>

<span data-ttu-id="512e2-129">指定要发送到控制台的调试消息。</span><span class="sxs-lookup"><span data-stu-id="512e2-129">Specifies the debug message to send to the console.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="512e2-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="512e2-130">CommonParameters</span></span>

<span data-ttu-id="512e2-131">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="512e2-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="512e2-132">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="512e2-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="512e2-133">输入</span><span class="sxs-lookup"><span data-stu-id="512e2-133">INPUTS</span></span>

### <span data-ttu-id="512e2-134">System.String</span><span class="sxs-lookup"><span data-stu-id="512e2-134">System.String</span></span>

<span data-ttu-id="512e2-135">可以通过管道将包含调试消息的字符串传递给 `Write-Debug` 。</span><span class="sxs-lookup"><span data-stu-id="512e2-135">You can pipe a string that contains a debug message to `Write-Debug`.</span></span>

## <span data-ttu-id="512e2-136">输出</span><span class="sxs-lookup"><span data-stu-id="512e2-136">OUTPUTS</span></span>

### <span data-ttu-id="512e2-137">无</span><span class="sxs-lookup"><span data-stu-id="512e2-137">None</span></span>

<span data-ttu-id="512e2-138">`Write-Debug` 仅写入到调试流。</span><span class="sxs-lookup"><span data-stu-id="512e2-138">`Write-Debug` only writes to the debug stream.</span></span> <span data-ttu-id="512e2-139">它不会将任何对象写入管道。</span><span class="sxs-lookup"><span data-stu-id="512e2-139">It does not write any objects to the pipeline.</span></span>

## <span data-ttu-id="512e2-140">注释</span><span class="sxs-lookup"><span data-stu-id="512e2-140">NOTES</span></span>

## <span data-ttu-id="512e2-141">相关链接</span><span class="sxs-lookup"><span data-stu-id="512e2-141">RELATED LINKS</span></span>

[<span data-ttu-id="512e2-142">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="512e2-142">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="512e2-143">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="512e2-143">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="512e2-144">写入错误</span><span class="sxs-lookup"><span data-stu-id="512e2-144">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="512e2-145">Write-Host</span><span class="sxs-lookup"><span data-stu-id="512e2-145">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="512e2-146">Write-Output</span><span class="sxs-lookup"><span data-stu-id="512e2-146">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="512e2-147">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="512e2-147">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="512e2-148">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="512e2-148">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="512e2-149">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="512e2-149">Write-Warning</span></span>](Write-Warning.md)
