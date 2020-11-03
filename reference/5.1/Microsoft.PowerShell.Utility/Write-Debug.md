---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 7e622367f1753fc15bed26fe083e9f343fd82b85
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "93200517"
---
# <span data-ttu-id="363fe-103">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="363fe-103">Write-Debug</span></span>

## <span data-ttu-id="363fe-104">摘要</span><span class="sxs-lookup"><span data-stu-id="363fe-104">SYNOPSIS</span></span>
<span data-ttu-id="363fe-105">将调试消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="363fe-105">Writes a debug message to the console.</span></span>

## <span data-ttu-id="363fe-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="363fe-106">SYNTAX</span></span>

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="363fe-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="363fe-107">DESCRIPTION</span></span>

<span data-ttu-id="363fe-108">该 `Write-Debug` cmdlet 从脚本或命令中将调试消息写入主机。</span><span class="sxs-lookup"><span data-stu-id="363fe-108">The `Write-Debug` cmdlet writes debug messages to the host from a script or command.</span></span>

<span data-ttu-id="363fe-109">默认情况下，调试消息不会显示在控制台中，但可以使用 **debug** 参数或变量显示它们 `$DebugPreference` 。</span><span class="sxs-lookup"><span data-stu-id="363fe-109">By default, debug messages are not displayed in the console, but you can display them by using the **Debug** parameter or the `$DebugPreference` variable.</span></span>

## <span data-ttu-id="363fe-110">示例</span><span class="sxs-lookup"><span data-stu-id="363fe-110">EXAMPLES</span></span>

### <span data-ttu-id="363fe-111">示例 1：了解 $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="363fe-111">Example 1: Understand $DebugPreference</span></span>

<span data-ttu-id="363fe-112">此示例编写调试消息。</span><span class="sxs-lookup"><span data-stu-id="363fe-112">This example writes a debug message.</span></span>

```powershell
Write-Debug "Cannot open file."
```

<span data-ttu-id="363fe-113">的默认值 `$DebugPreference` 为 **SilentlyContinue** 。</span><span class="sxs-lookup"><span data-stu-id="363fe-113">The default value of `$DebugPreference` is **SilentlyContinue** .</span></span> <span data-ttu-id="363fe-114">因此，该消息不会显示在控制台中。</span><span class="sxs-lookup"><span data-stu-id="363fe-114">Therefore, the message is not displayed in the console.</span></span>

### <span data-ttu-id="363fe-115">示例2：更改 $DebugPreference 的值</span><span class="sxs-lookup"><span data-stu-id="363fe-115">Example 2: Change the value of $DebugPreference</span></span>

<span data-ttu-id="363fe-116">此示例演示更改变量的值的效果 `$DebugPreference` 。</span><span class="sxs-lookup"><span data-stu-id="363fe-116">This example shows the effect of changing the value of the `$DebugPreference` variable.</span></span> <span data-ttu-id="363fe-117">首先，我们显示的当前值 `$DebugPreference` ，并尝试编写调试消息。</span><span class="sxs-lookup"><span data-stu-id="363fe-117">First, we display the current value of `$DebugPreference` and attempt to write a debug message.</span></span> <span data-ttu-id="363fe-118">然后，将的值更改 `$DebugPreference` 为 **Continue** ，这允许显示调试消息。</span><span class="sxs-lookup"><span data-stu-id="363fe-118">Then we change the value of `$DebugPreference` to **Continue** , which allows debug messages to be displayed.</span></span>

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

<span data-ttu-id="363fe-119">有关的详细信息 `$DebugPreference` ，请参阅 [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables)。</span><span class="sxs-lookup"><span data-stu-id="363fe-119">For more information about `$DebugPreference`, see [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span></span>

### <span data-ttu-id="363fe-120">示例3：使用 Debug 参数覆盖 $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="363fe-120">Example 3: Use the Debug parameter to override $DebugPreference</span></span>

<span data-ttu-id="363fe-121">`Test-Debug`函数将变量的值写入 `$DebugPreference` PowerShell 主机和调试流。</span><span class="sxs-lookup"><span data-stu-id="363fe-121">The `Test-Debug` function writes the value of the `$DebugPreference` variable to the PowerShell host and to the Debug stream.</span></span> <span data-ttu-id="363fe-122">在此示例中，我们使用 **Debug** 参数重写 `$DebugPreference` 该值。</span><span class="sxs-lookup"><span data-stu-id="363fe-122">In this example, we use the **Debug** parameter to override the `$DebugPreference` value.</span></span>

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
DEBUG: $DebugPreference is Inquire

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
$DebugPreference is Inquire
PS> $DebugPreference
SilentlyContinue
```

<span data-ttu-id="363fe-123">请注意， `$DebugPreference` 当你使用 **Debug** 参数时，的值将更改。</span><span class="sxs-lookup"><span data-stu-id="363fe-123">Notice that the value of `$DebugPreference` changes when you use the **Debug** parameter.</span></span> <span data-ttu-id="363fe-124">此更改只影响函数的作用域。</span><span class="sxs-lookup"><span data-stu-id="363fe-124">This change only affects the scope of the function.</span></span> <span data-ttu-id="363fe-125">此值在函数之外不受影响。</span><span class="sxs-lookup"><span data-stu-id="363fe-125">The value is not affected outside the function.</span></span>

> [!NOTE]
> <span data-ttu-id="363fe-126">如果的值 `$DebugPreference` 为 **Inquire** ，则 PowerShell 将暂停执行，以询问是否应继续执行。</span><span class="sxs-lookup"><span data-stu-id="363fe-126">When the value of `$DebugPreference` is **Inquire** , PowerShell halts execution to ask if execution should continue.</span></span>

<span data-ttu-id="363fe-127">有关 **Debug** 通用参数的详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="363fe-127">For more information about the **Debug** common parameter, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="363fe-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="363fe-128">PARAMETERS</span></span>

### <span data-ttu-id="363fe-129">-Message</span><span class="sxs-lookup"><span data-stu-id="363fe-129">-Message</span></span>

<span data-ttu-id="363fe-130">指定要发送到控制台的调试消息。</span><span class="sxs-lookup"><span data-stu-id="363fe-130">Specifies the debug message to send to the console.</span></span>

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

### <span data-ttu-id="363fe-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="363fe-131">CommonParameters</span></span>

<span data-ttu-id="363fe-132">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="363fe-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="363fe-133">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="363fe-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="363fe-134">输入</span><span class="sxs-lookup"><span data-stu-id="363fe-134">INPUTS</span></span>

### <span data-ttu-id="363fe-135">System.String</span><span class="sxs-lookup"><span data-stu-id="363fe-135">System.String</span></span>

<span data-ttu-id="363fe-136">可以通过管道将包含调试消息的字符串传递给 `Write-Debug` 。</span><span class="sxs-lookup"><span data-stu-id="363fe-136">You can pipe a string that contains a debug message to `Write-Debug`.</span></span>

## <span data-ttu-id="363fe-137">输出</span><span class="sxs-lookup"><span data-stu-id="363fe-137">OUTPUTS</span></span>

### <span data-ttu-id="363fe-138">无</span><span class="sxs-lookup"><span data-stu-id="363fe-138">None</span></span>

<span data-ttu-id="363fe-139">`Write-Debug` 仅写入到调试流。</span><span class="sxs-lookup"><span data-stu-id="363fe-139">`Write-Debug` only writes to the debug stream.</span></span> <span data-ttu-id="363fe-140">它不会将任何对象写入管道。</span><span class="sxs-lookup"><span data-stu-id="363fe-140">It does not write any objects to the pipeline.</span></span>

## <span data-ttu-id="363fe-141">注释</span><span class="sxs-lookup"><span data-stu-id="363fe-141">NOTES</span></span>

## <span data-ttu-id="363fe-142">相关链接</span><span class="sxs-lookup"><span data-stu-id="363fe-142">RELATED LINKS</span></span>

[<span data-ttu-id="363fe-143">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="363fe-143">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="363fe-144">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="363fe-144">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="363fe-145">写入错误</span><span class="sxs-lookup"><span data-stu-id="363fe-145">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="363fe-146">Write-Host</span><span class="sxs-lookup"><span data-stu-id="363fe-146">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="363fe-147">Write-Output</span><span class="sxs-lookup"><span data-stu-id="363fe-147">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="363fe-148">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="363fe-148">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="363fe-149">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="363fe-149">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="363fe-150">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="363fe-150">Write-Warning</span></span>](Write-Warning.md)
