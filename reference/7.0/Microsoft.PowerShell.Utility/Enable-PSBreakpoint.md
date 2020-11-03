---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-psbreakpoint?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSBreakpoint
ms.openlocfilehash: 606ac3205dae254c7f1290f51f80b61e472fbece
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197304"
---
# <span data-ttu-id="dcf05-103">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="dcf05-103">Enable-PSBreakpoint</span></span>

## <span data-ttu-id="dcf05-104">摘要</span><span class="sxs-lookup"><span data-stu-id="dcf05-104">SYNOPSIS</span></span>
<span data-ttu-id="dcf05-105">启用当前控制台中的断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-105">Enables the breakpoints in the current console.</span></span>

## <span data-ttu-id="dcf05-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dcf05-106">SYNTAX</span></span>

### <span data-ttu-id="dcf05-107">ID（默认值）</span><span class="sxs-lookup"><span data-stu-id="dcf05-107">Id (Default)</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="dcf05-108">断点</span><span class="sxs-lookup"><span data-stu-id="dcf05-108">Breakpoint</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="dcf05-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dcf05-109">DESCRIPTION</span></span>

<span data-ttu-id="dcf05-110">`Enable-PSBreakpoint`Cmdlet 可重新启用已禁用的断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-110">The `Enable-PSBreakpoint` cmdlet re-enables disabled breakpoints.</span></span> <span data-ttu-id="dcf05-111">您可以通过提供断点对象或 Id，使用它来启用所有断点或特定断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-111">You can use it to enable all breakpoints, or specific breakpoints by providing breakpoint objects or IDs.</span></span>

<span data-ttu-id="dcf05-112">断点是脚本中的一个点，其中的执行暂时停止，以便您可以检查脚本的状态。</span><span class="sxs-lookup"><span data-stu-id="dcf05-112">A breakpoint is a point in a script where execution stops temporarily so that you can examine the state of the script.</span></span> <span data-ttu-id="dcf05-113">新创建的断点将自动启用，但可以使用禁用 `Disable-PSBreakpoint` 。</span><span class="sxs-lookup"><span data-stu-id="dcf05-113">Newly created breakpoints are automatically enabled, but can be disabled using `Disable-PSBreakpoint`.</span></span>

<span data-ttu-id="dcf05-114">在技术上，此 cmdlet 将断点对象的 **Enabled** 属性值更改为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="dcf05-114">Technically, this cmdlet changes the value of the **Enabled** property of a breakpoint object to **True** .</span></span>

<span data-ttu-id="dcf05-115">`Enable-PSBreakpoint` 是旨在调试 PowerShell 脚本的多个 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="dcf05-115">`Enable-PSBreakpoint` is one of several cmdlets designed for debugging PowerShell scripts.</span></span> <span data-ttu-id="dcf05-116">有关 PowerShell 调试器的详细信息，请参阅 [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md)。</span><span class="sxs-lookup"><span data-stu-id="dcf05-116">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="dcf05-117">示例</span><span class="sxs-lookup"><span data-stu-id="dcf05-117">EXAMPLES</span></span>

### <span data-ttu-id="dcf05-118">示例1：启用所有断点</span><span class="sxs-lookup"><span data-stu-id="dcf05-118">Example 1: Enable all breakpoints</span></span>

<span data-ttu-id="dcf05-119">此示例将启用当前会话中的所有断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-119">This example enables all breakpoints in the current session.</span></span>

```powershell
Get-PSBreakpoint | Enable-PSBreakpoint
```

<span data-ttu-id="dcf05-120">使用别名，此示例可以缩写为 `gbp | ebp` 。</span><span class="sxs-lookup"><span data-stu-id="dcf05-120">Using aliases, this example can be abbreviated as `gbp | ebp`.</span></span>

### <span data-ttu-id="dcf05-121">示例2：按 ID 启用断点</span><span class="sxs-lookup"><span data-stu-id="dcf05-121">Example 2: Enable breakpoints by ID</span></span>

<span data-ttu-id="dcf05-122">此示例使用断点 Id 启用多个断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-122">This example enables multiple breakpoints using their breakpoint IDs.</span></span>

```powershell
Enable-PSBreakpoint -Id 0, 1, 5
```

### <span data-ttu-id="dcf05-123">示例3：启用已禁用的断点</span><span class="sxs-lookup"><span data-stu-id="dcf05-123">Example 3: Enable a disabled breakpoint</span></span>

<span data-ttu-id="dcf05-124">此示例将重新启用已禁用的断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-124">This example re-enables a breakpoint that has been disabled.</span></span>

```powershell
$B = Set-PSBreakpoint -Script "sample.ps1" -Variable Name -PassThru
$B | Enable-PSBreakpoint -PassThru
```

```Output
AccessMode : Write
Variable   : Name
Action     :
Enabled    : False
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1

AccessMode : Write
Variable   : Name
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="dcf05-125">`Set-PSBreakpoint` 在脚本中的 **名称** 变量上创建一个断点，该断点将 `Sample.ps1` 断点对象保存在 `$B` 变量中。</span><span class="sxs-lookup"><span data-stu-id="dcf05-125">`Set-PSBreakpoint` creates a breakpoint on the **Name** variable in the `Sample.ps1` script saving the breakpoint object in the `$B` variable.</span></span> <span data-ttu-id="dcf05-126">**PassThru** 参数显示断点的 **Enabled** 属性的值为 **False** 。</span><span class="sxs-lookup"><span data-stu-id="dcf05-126">The **PassThru** parameter displays the value of the **Enabled** property of the breakpoint is **False** .</span></span>

<span data-ttu-id="dcf05-127">`Enable-PSBreakpoint` 重新启用断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-127">`Enable-PSBreakpoint` re-enables the breakpoint.</span></span> <span data-ttu-id="dcf05-128">再次强调，使用 **PassThru** 参数会看到 **Enabled** 属性的值为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="dcf05-128">Again, using the **PassThru** parameter we see that the value of the **Enabled** property is **True** .</span></span>

### <span data-ttu-id="dcf05-129">示例4：使用变量启用断点</span><span class="sxs-lookup"><span data-stu-id="dcf05-129">Example 4: Enable breakpoints using a variable</span></span>

<span data-ttu-id="dcf05-130">此示例使用断点对象启用一组断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-130">This example enables a set of breakpoints using the breakpoint objects.</span></span>

```powershell
$B = Get-PSBreakpoint -Id 3, 5
Enable-PSBreakpoint -Breakpoint $B
```

<span data-ttu-id="dcf05-131">`Get-PSBreakpoint` 获取断点，并将它们保存在 `$B` 变量中。</span><span class="sxs-lookup"><span data-stu-id="dcf05-131">`Get-PSBreakpoint` gets the breakpoints and saves them in the `$B` variable.</span></span> <span data-ttu-id="dcf05-132">使用 **断点** 参数 `Enable-PSBreakpoint` 启用断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-132">Using the **Breakpoint** parameter, `Enable-PSBreakpoint` enables the breakpoints.</span></span>

<span data-ttu-id="dcf05-133">此示例等效于运行 `Enable-PSBreakpoint -Id 3, 5` 。</span><span class="sxs-lookup"><span data-stu-id="dcf05-133">This example is equivalent to running `Enable-PSBreakpoint -Id 3, 5`.</span></span>

## <span data-ttu-id="dcf05-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dcf05-134">PARAMETERS</span></span>

### <span data-ttu-id="dcf05-135">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="dcf05-135">-Breakpoint</span></span>

<span data-ttu-id="dcf05-136">指定要启用的断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-136">Specifies the breakpoints to enable.</span></span> <span data-ttu-id="dcf05-137">提供一个包含断点的变量或一个可获取断点对象的命令，例如 `Get-PSBreakpoint` 。</span><span class="sxs-lookup"><span data-stu-id="dcf05-137">Provide a variable containing breakpoints or a command that gets breakpoint objects, such as `Get-PSBreakpoint`.</span></span> <span data-ttu-id="dcf05-138">还可以通过管道将断点对象传递给 `Enable-PSBreakpoint` 。</span><span class="sxs-lookup"><span data-stu-id="dcf05-138">You can also pipe breakpoint objects to `Enable-PSBreakpoint`.</span></span>

```yaml
Type: System.Management.Automation.Breakpoint[]
Parameter Sets: Breakpoint
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="dcf05-139">-Id</span><span class="sxs-lookup"><span data-stu-id="dcf05-139">-Id</span></span>

<span data-ttu-id="dcf05-140">指定要启用的断点的 **Id** 号。</span><span class="sxs-lookup"><span data-stu-id="dcf05-140">Specifies the **Id** numbers of the breakpoints to enable.</span></span> <span data-ttu-id="dcf05-141">默认值为所有断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-141">The default value is all breakpoints.</span></span>
<span data-ttu-id="dcf05-142">按数字或变量提供 **Id** 。</span><span class="sxs-lookup"><span data-stu-id="dcf05-142">Provide the **Id** by number or in a variable.</span></span> <span data-ttu-id="dcf05-143">不能通过管道将 **Id** 号传递给 `Enable-PSBreakpoint` 。</span><span class="sxs-lookup"><span data-stu-id="dcf05-143">You can't pipe **Id** numbers to `Enable-PSBreakpoint`.</span></span> <span data-ttu-id="dcf05-144">若要查找断点的 **Id** ，请使用 `Get-PSBreakpoint` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dcf05-144">To find the **Id** of a breakpoint, use the `Get-PSBreakpoint` cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dcf05-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="dcf05-145">-PassThru</span></span>

<span data-ttu-id="dcf05-146">返回一个对象，该对象表示正在启用的断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-146">Returns an object representing the breakpoint being enabled.</span></span> <span data-ttu-id="dcf05-147">默认情况下，此 cmdlet 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="dcf05-147">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="dcf05-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="dcf05-148">-Confirm</span></span>

<span data-ttu-id="dcf05-149">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="dcf05-149">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dcf05-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="dcf05-150">-WhatIf</span></span>

<span data-ttu-id="dcf05-151">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="dcf05-151">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="dcf05-152">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="dcf05-152">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dcf05-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dcf05-153">CommonParameters</span></span>

<span data-ttu-id="dcf05-154">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="dcf05-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dcf05-155">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="dcf05-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dcf05-156">输入</span><span class="sxs-lookup"><span data-stu-id="dcf05-156">INPUTS</span></span>

### <span data-ttu-id="dcf05-157">System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="dcf05-157">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="dcf05-158">可以通过管道将断点对象传递给 `Enable-PSBreakpoint` 。</span><span class="sxs-lookup"><span data-stu-id="dcf05-158">You can pipe a breakpoint object to `Enable-PSBreakpoint`.</span></span>

## <span data-ttu-id="dcf05-159">输出</span><span class="sxs-lookup"><span data-stu-id="dcf05-159">OUTPUTS</span></span>

### <span data-ttu-id="dcf05-160">无或 System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="dcf05-160">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="dcf05-161">当使用 **PassThru** 参数时，将 `Enable-PSBreakpoint` 返回一个断点对象，该对象表示已启用的断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-161">When you use the **PassThru** parameter, `Enable-PSBreakpoint` returns a breakpoint object that represents that breakpoint that was enabled.</span></span> <span data-ttu-id="dcf05-162">否则，此 cmdlet 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="dcf05-162">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="dcf05-163">注释</span><span class="sxs-lookup"><span data-stu-id="dcf05-163">NOTES</span></span>

- <span data-ttu-id="dcf05-164">`Enable-PSBreakpoint`如果尝试启用已启用的断点，则该 cmdlet 不会生成错误。</span><span class="sxs-lookup"><span data-stu-id="dcf05-164">The `Enable-PSBreakpoint` cmdlet doesn't generate an error if you try to enable a breakpoint that is already enabled.</span></span> <span data-ttu-id="dcf05-165">因此，即使仅有少数断点处于禁用状态，你也可以启用所有断点而不发生错误。</span><span class="sxs-lookup"><span data-stu-id="dcf05-165">As such, you can enable all breakpoints without error, even when only a few are disabled.</span></span>

- <span data-ttu-id="dcf05-166">使用 cmdlet 创建断点时，会启用断点 `Set-PSBreakpoint` 。</span><span class="sxs-lookup"><span data-stu-id="dcf05-166">Breakpoints are enabled when you create them by using the `Set-PSBreakpoint` cmdlet.</span></span> <span data-ttu-id="dcf05-167">不需要启用新创建的断点。</span><span class="sxs-lookup"><span data-stu-id="dcf05-167">You don't need to enable newly created breakpoints.</span></span>

## <span data-ttu-id="dcf05-168">相关链接</span><span class="sxs-lookup"><span data-stu-id="dcf05-168">RELATED LINKS</span></span>

[<span data-ttu-id="dcf05-169">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="dcf05-169">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="dcf05-170">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="dcf05-170">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="dcf05-171">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="dcf05-171">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="dcf05-172">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="dcf05-172">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="dcf05-173">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="dcf05-173">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
