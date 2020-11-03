---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-psdebug?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSDebug
ms.openlocfilehash: a0b5d7e86f9d63b487bc093feb18ecc7a4496999
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198681"
---
# <span data-ttu-id="0aef3-103">Set-PSDebug</span><span class="sxs-lookup"><span data-stu-id="0aef3-103">Set-PSDebug</span></span>

## <span data-ttu-id="0aef3-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0aef3-104">SYNOPSIS</span></span>
<span data-ttu-id="0aef3-105">启用和禁用脚本调试功能、设置跟踪级别和切换严格模式。</span><span class="sxs-lookup"><span data-stu-id="0aef3-105">Turns script debugging features on and off, sets the trace level, and toggles strict mode.</span></span>

## <span data-ttu-id="0aef3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0aef3-106">SYNTAX</span></span>

### <span data-ttu-id="0aef3-107">on</span><span class="sxs-lookup"><span data-stu-id="0aef3-107">on</span></span>

```
Set-PSDebug [-Trace <Int32>] [-Step] [-Strict] [<CommonParameters>]
```

### <span data-ttu-id="0aef3-108">关闭</span><span class="sxs-lookup"><span data-stu-id="0aef3-108">off</span></span>

```
Set-PSDebug [-Off] [<CommonParameters>]
```

## <span data-ttu-id="0aef3-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0aef3-109">DESCRIPTION</span></span>

<span data-ttu-id="0aef3-110">此 `Set-PSDebug` cmdlet 将启用和禁用脚本调试功能、设置跟踪级别和切换严格模式。</span><span class="sxs-lookup"><span data-stu-id="0aef3-110">The `Set-PSDebug` cmdlet turns script debugging features on and off, sets the trace level, and toggles strict mode.</span></span> <span data-ttu-id="0aef3-111">默认情况下，PowerShell 调试功能处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="0aef3-111">By default, the PowerShell debug features are off.</span></span>

<span data-ttu-id="0aef3-112">如果 **Trace** 参数的值为，则 `1` 会在运行时跟踪脚本的每一行。</span><span class="sxs-lookup"><span data-stu-id="0aef3-112">When the **Trace** parameter has a value of `1`, each line of script is traced as it runs.</span></span> <span data-ttu-id="0aef3-113">当参数的值为时 `2` ，还将跟踪变量赋值、函数调用和脚本调用。</span><span class="sxs-lookup"><span data-stu-id="0aef3-113">When the parameter has a value of `2`, variable assignments, function calls, and script calls are also traced.</span></span> <span data-ttu-id="0aef3-114">如果指定了 **Step** 参数，将在每个脚本行运行之前提示您。</span><span class="sxs-lookup"><span data-stu-id="0aef3-114">If the **Step** parameter is specified, you're prompted before each line of the script runs.</span></span>

## <span data-ttu-id="0aef3-115">示例</span><span class="sxs-lookup"><span data-stu-id="0aef3-115">EXAMPLES</span></span>

### <span data-ttu-id="0aef3-116">示例1：设置跟踪级别</span><span class="sxs-lookup"><span data-stu-id="0aef3-116">Example 1: Set the trace level</span></span>

<span data-ttu-id="0aef3-117">此示例将跟踪级别设置为 `2` ，然后运行一个显示数字1、2和</span><span class="sxs-lookup"><span data-stu-id="0aef3-117">This example sets the trace level to `2`, and then runs a script that displays the numbers 1, 2, and</span></span>
3.

```powershell
Set-PSDebug -Trace 2; foreach ($i in 1..3) {$i}
```

```Output
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in  >>>> 1..3) {$i}
DEBUG:     ! SET $foreach = 'IEnumerator'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '1'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
1
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '2'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
2
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '3'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
3
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $foreach = ''.
```

### <span data-ttu-id="0aef3-118">示例2：打开单步执行</span><span class="sxs-lookup"><span data-stu-id="0aef3-118">Example 2: Turn on stepping</span></span>

<span data-ttu-id="0aef3-119">此示例将启用 "单步执行"，然后运行显示数字1、2和3的脚本。</span><span class="sxs-lookup"><span data-stu-id="0aef3-119">This example turns on stepping, and then runs a script that displays the numbers 1, 2, and 3.</span></span>

```powershell
Set-PSDebug -Step; foreach ($i in 1..3) {$i}
```

```Output
Continue with this operation?
   1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): A
DEBUG:    1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
1
2
3
```

### <span data-ttu-id="0aef3-120">示例3：使用严格模式</span><span class="sxs-lookup"><span data-stu-id="0aef3-120">Example 3: Use strict mode</span></span>

<span data-ttu-id="0aef3-121">此示例将 PowerShell 置于严格模式下，并尝试访问不具有赋值的变量。</span><span class="sxs-lookup"><span data-stu-id="0aef3-121">This example puts PowerShell in strict mode and attempts to access a variable that doesn't have an assigned value.</span></span>

```powershell
Set-PSDebug -Strict; $NewVar
```

```Output
The variable '$NewVar' cannot be retrieved because it has not been set.
At line:1 char:22
+ Set-PSDebug -Strict; $NewVar
```

### <span data-ttu-id="0aef3-122">示例4：关闭调试功能</span><span class="sxs-lookup"><span data-stu-id="0aef3-122">Example 4: Turn off debug features</span></span>

<span data-ttu-id="0aef3-123">此示例关闭所有调试功能，然后运行一个显示数字1、2和3的脚本。</span><span class="sxs-lookup"><span data-stu-id="0aef3-123">This example turns off all debugging features, and then runs a script that displays the numbers 1, 2, and 3.</span></span>

```powershell
Set-PSDebug -Off; foreach ($i in 1..3) {$i}
```

```Output
1
2
3
```

## <span data-ttu-id="0aef3-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0aef3-124">PARAMETERS</span></span>

### <span data-ttu-id="0aef3-125">-Off</span><span class="sxs-lookup"><span data-stu-id="0aef3-125">-Off</span></span>

<span data-ttu-id="0aef3-126">禁用所有脚本调试功能。</span><span class="sxs-lookup"><span data-stu-id="0aef3-126">Turns off all script debugging features.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: off
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0aef3-127">-Step</span><span class="sxs-lookup"><span data-stu-id="0aef3-127">-Step</span></span>

<span data-ttu-id="0aef3-128">启用脚本步进。</span><span class="sxs-lookup"><span data-stu-id="0aef3-128">Turns on script stepping.</span></span> <span data-ttu-id="0aef3-129">在每行运行之前，PowerShell 会提示你停止、继续或输入新的解释器级别来检查脚本的状态。</span><span class="sxs-lookup"><span data-stu-id="0aef3-129">Before each line runs, PowerShell prompts you to stop, continue, or enter a new interpreter level to inspect the state of the script.</span></span>

<span data-ttu-id="0aef3-130">指定 **Step** 参数会自动将跟踪级别设置为 `1` 。</span><span class="sxs-lookup"><span data-stu-id="0aef3-130">Specifying the **Step** parameter automatically sets a trace level of `1`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0aef3-131">-Strict</span><span class="sxs-lookup"><span data-stu-id="0aef3-131">-Strict</span></span>

<span data-ttu-id="0aef3-132">指定在脚本中引用变量之前，必须先为其赋值。</span><span class="sxs-lookup"><span data-stu-id="0aef3-132">Specifies that variables must be assigned a value before being referenced in a script.</span></span> <span data-ttu-id="0aef3-133">如果在分配值之前引用变量，则 PowerShell 将返回异常错误。</span><span class="sxs-lookup"><span data-stu-id="0aef3-133">If a variable is referenced before a value is assigned, PowerShell returns an exception error.</span></span> <span data-ttu-id="0aef3-134">这等效于 `Set-StrictMode -Version 1`。</span><span class="sxs-lookup"><span data-stu-id="0aef3-134">This is equivalent to `Set-StrictMode -Version 1`.</span></span> <span data-ttu-id="0aef3-135">有关详细信息，请参阅 [set-strictmode](Set-StrictMode.md)。</span><span class="sxs-lookup"><span data-stu-id="0aef3-135">For more information, see [Set-StrictMode](Set-StrictMode.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0aef3-136">-Trace</span><span class="sxs-lookup"><span data-stu-id="0aef3-136">-Trace</span></span>

<span data-ttu-id="0aef3-137">为脚本中的每一行指定跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="0aef3-137">Specifies the trace level for each line in a script.</span></span> <span data-ttu-id="0aef3-138">每行在运行时都会被跟踪。</span><span class="sxs-lookup"><span data-stu-id="0aef3-138">Each line is traced as it's run.</span></span>

<span data-ttu-id="0aef3-139">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="0aef3-139">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="0aef3-140">0：关闭脚本跟踪。</span><span class="sxs-lookup"><span data-stu-id="0aef3-140">0: Turn script tracing off.</span></span>
- <span data-ttu-id="0aef3-141">1：跟踪运行的脚本行。</span><span class="sxs-lookup"><span data-stu-id="0aef3-141">1: Trace script lines as they run.</span></span>
- <span data-ttu-id="0aef3-142">2：跟踪脚本行、变量赋值、函数调用和脚本。</span><span class="sxs-lookup"><span data-stu-id="0aef3-142">2: Trace script lines, variable assignments, function calls, and scripts.</span></span>

```yaml
Type: System.Int32
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0aef3-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0aef3-143">CommonParameters</span></span>

<span data-ttu-id="0aef3-144">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0aef3-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0aef3-145">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0aef3-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0aef3-146">输入</span><span class="sxs-lookup"><span data-stu-id="0aef3-146">INPUTS</span></span>

### <span data-ttu-id="0aef3-147">无</span><span class="sxs-lookup"><span data-stu-id="0aef3-147">None</span></span>

<span data-ttu-id="0aef3-148">不能通过管道将输入用于此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0aef3-148">You can't pipeline input to this cmdlet.</span></span>

## <span data-ttu-id="0aef3-149">输出</span><span class="sxs-lookup"><span data-stu-id="0aef3-149">OUTPUTS</span></span>

### <span data-ttu-id="0aef3-150">无</span><span class="sxs-lookup"><span data-stu-id="0aef3-150">None</span></span>

<span data-ttu-id="0aef3-151">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="0aef3-151">This cmdlet doesn't return any output.</span></span>

## <span data-ttu-id="0aef3-152">注释</span><span class="sxs-lookup"><span data-stu-id="0aef3-152">NOTES</span></span>

## <span data-ttu-id="0aef3-153">相关链接</span><span class="sxs-lookup"><span data-stu-id="0aef3-153">RELATED LINKS</span></span>

[<span data-ttu-id="0aef3-154">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="0aef3-154">about_Debuggers</span></span>](./About/about_Debuggers.md)

[<span data-ttu-id="0aef3-155">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="0aef3-155">Debug-Process</span></span>](../Microsoft.PowerShell.Management/Debug-Process.md)

[<span data-ttu-id="0aef3-156">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="0aef3-156">Set-PSBreakpoint</span></span>](../Microsoft.PowerShell.Utility/Set-PSBreakpoint.md)

[<span data-ttu-id="0aef3-157">Set-StrictMode</span><span class="sxs-lookup"><span data-stu-id="0aef3-157">Set-StrictMode</span></span>](Set-StrictMode.md)

[<span data-ttu-id="0aef3-158">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="0aef3-158">Write-Debug</span></span>](../Microsoft.PowerShell.Utility/Write-Debug.md)

