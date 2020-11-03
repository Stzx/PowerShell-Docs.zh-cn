---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-psbreakpoint?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSBreakpoint
ms.openlocfilehash: 80d0c77e4c54dbc7e501339f5550c87f5f1ddbed
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197113"
---
# <span data-ttu-id="d15cf-103">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d15cf-103">Disable-PSBreakpoint</span></span>

## <span data-ttu-id="d15cf-104">摘要</span><span class="sxs-lookup"><span data-stu-id="d15cf-104">SYNOPSIS</span></span>
<span data-ttu-id="d15cf-105">禁用当前控制台中的断点。</span><span class="sxs-lookup"><span data-stu-id="d15cf-105">Disables the breakpoints in the current console.</span></span>

## <span data-ttu-id="d15cf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d15cf-106">SYNTAX</span></span>

### <span data-ttu-id="d15cf-107">Breakpoint（默认值）</span><span class="sxs-lookup"><span data-stu-id="d15cf-107">Breakpoint (Default)</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d15cf-108">ID</span><span class="sxs-lookup"><span data-stu-id="d15cf-108">Id</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d15cf-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d15cf-109">DESCRIPTION</span></span>

<span data-ttu-id="d15cf-110">**Set-psbreakpoint** cmdlet 禁用断点，以确保在脚本运行时不会命中断点。</span><span class="sxs-lookup"><span data-stu-id="d15cf-110">The **Disable-PSBreakpoint** cmdlet disables breakpoints, which assures that they are not hit when the script runs.</span></span>
<span data-ttu-id="d15cf-111">可使用它来禁用所有断点，或者可通过提交断点对象或断点 ID 来指定断点。</span><span class="sxs-lookup"><span data-stu-id="d15cf-111">You can use it to disable all breakpoints, or you can specify breakpoints by submitting breakpoint objects or breakpoint IDs.</span></span>

<span data-ttu-id="d15cf-112">在技术上，该 cmdlet 将断点对象的 Enabled 属性值更改为 False。</span><span class="sxs-lookup"><span data-stu-id="d15cf-112">Technically, this cmdlet changes the value of the Enabled property of a breakpoint object to False.</span></span>
<span data-ttu-id="d15cf-113">若要重新启用断点，请使用 Enable-PSBreakpoint cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d15cf-113">To re-enable a breakpoint, use the Enable-PSBreakpoint cmdlet.</span></span>
<span data-ttu-id="d15cf-114">当使用 Set-PSBreakpoint cmdlet 来创建断点时，将默认启用断点。</span><span class="sxs-lookup"><span data-stu-id="d15cf-114">Breakpoints are enabled by default when you create them by using the Set-PSBreakpoint cmdlet.</span></span>

<span data-ttu-id="d15cf-115">断点是脚本中的一个点，将在其中暂时停止执行脚本，从而使你可以检查脚本中的指令。</span><span class="sxs-lookup"><span data-stu-id="d15cf-115">A breakpoint is a point in a script where execution stops temporarily so that you can examine the instructions in the script.</span></span>
<span data-ttu-id="d15cf-116">**Set-psbreakpoint** 是设计用于调试 PowerShell 脚本的多个 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="d15cf-116">**Disable-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="d15cf-117">有关 PowerShell 调试器的详细信息，请参阅 about_Debuggers。</span><span class="sxs-lookup"><span data-stu-id="d15cf-117">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="d15cf-118">示例</span><span class="sxs-lookup"><span data-stu-id="d15cf-118">EXAMPLES</span></span>

### <span data-ttu-id="d15cf-119">示例1：设置断点并禁用它</span><span class="sxs-lookup"><span data-stu-id="d15cf-119">Example 1: Set a breakpoint and disable it</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "name"
PS C:\> $B | Disable-PSBreakpoint
```

<span data-ttu-id="d15cf-120">这些命令禁用新创建的断点。</span><span class="sxs-lookup"><span data-stu-id="d15cf-120">These commands disable a newly-created breakpoint.</span></span>

<span data-ttu-id="d15cf-121">第一个命令使用 Set-PSBreakpoint cmdlet 在 Sample.ps1 脚本中的 *Name* 变量上创建断点。</span><span class="sxs-lookup"><span data-stu-id="d15cf-121">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the *Name* variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="d15cf-122">然后，它将断点对象保存在 $B 变量中。</span><span class="sxs-lookup"><span data-stu-id="d15cf-122">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="d15cf-123">第二个命令使用 **set-psbreakpoint** cmdlet 来禁用新断点。</span><span class="sxs-lookup"><span data-stu-id="d15cf-123">The second command uses the **Disable-PSBreakpoint** cmdlet to disable the new breakpoint.</span></span>
<span data-ttu-id="d15cf-124">它使用管道运算符 (|) 将 $B 中的断点对象发送到 **set-psbreakpoint** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d15cf-124">It uses a pipeline operator (|) to send the breakpoint object in $B to the **Disable-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="d15cf-125">此命令的结果是，$B 中的断点对象的 Enabled 属性的值为 False。</span><span class="sxs-lookup"><span data-stu-id="d15cf-125">As a result of this command, the value of the Enabled property of the breakpoint object in $B is False.</span></span>

### <span data-ttu-id="d15cf-126">示例2：禁用断点</span><span class="sxs-lookup"><span data-stu-id="d15cf-126">Example 2: Disable a breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Id 0
```

<span data-ttu-id="d15cf-127">此命令禁用断点 ID 为 0 的断点。</span><span class="sxs-lookup"><span data-stu-id="d15cf-127">This command disables the breakpoint with breakpoint ID 0.</span></span>

### <span data-ttu-id="d15cf-128">示例3：创建已禁用的断点</span><span class="sxs-lookup"><span data-stu-id="d15cf-128">Example 3: Create a disabled breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Breakpoint ($B = Set-PSBreakpoint -Script "sample.ps1" -Line 5)
PS C:\> $B
```

<span data-ttu-id="d15cf-129">此命令创建新断点，在你启用该断点之前，该断点将一直禁用。</span><span class="sxs-lookup"><span data-stu-id="d15cf-129">This command creates a new breakpoint that is disabled until you enable it.</span></span>

<span data-ttu-id="d15cf-130">它使用 **set-psbreakpoint** cmdlet 禁用断点。</span><span class="sxs-lookup"><span data-stu-id="d15cf-130">It uses the **Disable-PSBreakpoint** cmdlet to disable the breakpoint.</span></span>
<span data-ttu-id="d15cf-131">*断点* 参数的值是一个 Set-PSBreakpoint 命令，该命令设置新断点，生成一个断点对象，并将该对象保存在 $B 变量中。</span><span class="sxs-lookup"><span data-stu-id="d15cf-131">The value of the *Breakpoint* parameter is a Set-PSBreakpoint command that sets a new breakpoint, generates a breakpoint object, and saves the object in the $B variable.</span></span>

<span data-ttu-id="d15cf-132">Cmdlet 参数将对象用作值，可接受包含对象的变量或者可获取或生成对象的命令。</span><span class="sxs-lookup"><span data-stu-id="d15cf-132">Cmdlet parameters that take objects as their values can accept a variable that contains the object or a command that gets or generates the object.</span></span>
<span data-ttu-id="d15cf-133">在这种情况下，因为 **Set-psbreakpoint 将** 生成一个断点对象，所以它可用作 *断点* 参数的值。</span><span class="sxs-lookup"><span data-stu-id="d15cf-133">In this case, because **Set-PSBreakpoint** generates a breakpoint object, it can be used as the value of the *Breakpoint* parameter.</span></span>

<span data-ttu-id="d15cf-134">第二个命令在 $B 变量的值中显示断点对象。</span><span class="sxs-lookup"><span data-stu-id="d15cf-134">The second command displays the breakpoint object in the value of the $B variable.</span></span>

### <span data-ttu-id="d15cf-135">示例4：禁用当前控制台中的所有断点</span><span class="sxs-lookup"><span data-stu-id="d15cf-135">Example 4: Disable all breakpoints in the current console</span></span>

```
PS C:\> Get-PSBreakpoint | Disable-PSBreakpoint
```

<span data-ttu-id="d15cf-136">此命令禁用当前控制台中的所有断点。</span><span class="sxs-lookup"><span data-stu-id="d15cf-136">This command disables all breakpoints in the current console.</span></span>
<span data-ttu-id="d15cf-137">可将此命令缩写为：“gbp | dbp”。</span><span class="sxs-lookup"><span data-stu-id="d15cf-137">You can abbreviate this command as: "gbp | dbp".</span></span>

## <span data-ttu-id="d15cf-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d15cf-138">PARAMETERS</span></span>

### <span data-ttu-id="d15cf-139">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="d15cf-139">-Breakpoint</span></span>

<span data-ttu-id="d15cf-140">指定要禁用的断点。</span><span class="sxs-lookup"><span data-stu-id="d15cf-140">Specifies the breakpoints to disable.</span></span>
<span data-ttu-id="d15cf-141">输入一个包含断点对象的变量，或可获取断点对象的命令（如 Get-PSBreakpoint 命令）。</span><span class="sxs-lookup"><span data-stu-id="d15cf-141">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a Get-PSBreakpoint command.</span></span>
<span data-ttu-id="d15cf-142">还可以通过管道将断点对象传递到 **set-psbreakpoint** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d15cf-142">You can also pipe breakpoint objects to the **Disable-PSBreakpoint** cmdlet.</span></span>

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

### <span data-ttu-id="d15cf-143">-Id</span><span class="sxs-lookup"><span data-stu-id="d15cf-143">-Id</span></span>

<span data-ttu-id="d15cf-144">禁用具有指定断点 ID 的断点。</span><span class="sxs-lookup"><span data-stu-id="d15cf-144">Disables the breakpoints with the specified breakpoint IDs.</span></span>
<span data-ttu-id="d15cf-145">输入 ID 或包含 ID 的变量。</span><span class="sxs-lookup"><span data-stu-id="d15cf-145">Enter the IDs or a variable that contains the IDs.</span></span>
<span data-ttu-id="d15cf-146">不能通过管道将 Id 传递到 **set-psbreakpoint** 。</span><span class="sxs-lookup"><span data-stu-id="d15cf-146">You cannot pipe IDs to **Disable-PSBreakpoint** .</span></span>

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

### <span data-ttu-id="d15cf-147">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d15cf-147">-PassThru</span></span>

<span data-ttu-id="d15cf-148">返回表示已启用的断点的对象。</span><span class="sxs-lookup"><span data-stu-id="d15cf-148">Returns an object representing the enabled breakpoints.</span></span>
<span data-ttu-id="d15cf-149">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="d15cf-149">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d15cf-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d15cf-150">-Confirm</span></span>

<span data-ttu-id="d15cf-151">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="d15cf-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d15cf-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d15cf-152">-WhatIf</span></span>

<span data-ttu-id="d15cf-153">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="d15cf-153">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d15cf-154">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="d15cf-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d15cf-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d15cf-155">CommonParameters</span></span>

<span data-ttu-id="d15cf-156">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="d15cf-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d15cf-157">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="d15cf-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d15cf-158">输入</span><span class="sxs-lookup"><span data-stu-id="d15cf-158">INPUTS</span></span>

### <span data-ttu-id="d15cf-159">System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="d15cf-159">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="d15cf-160">可以通过管道将断点对象传递给 **set-psbreakpoint** 。</span><span class="sxs-lookup"><span data-stu-id="d15cf-160">You can pipe a breakpoint object to **Disable-PSBreakpoint** .</span></span>

## <span data-ttu-id="d15cf-161">输出</span><span class="sxs-lookup"><span data-stu-id="d15cf-161">OUTPUTS</span></span>

### <span data-ttu-id="d15cf-162">无或 System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="d15cf-162">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="d15cf-163">当使用 *PassThru* 参数时， **set-psbreakpoint** 将返回一个表示已禁用的断点的对象。</span><span class="sxs-lookup"><span data-stu-id="d15cf-163">When you use the *PassThru* parameter, **Disable-PSBreakpoint** returns an object that represents the disabled breakpoint.</span></span>
<span data-ttu-id="d15cf-164">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="d15cf-164">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d15cf-165">注释</span><span class="sxs-lookup"><span data-stu-id="d15cf-165">NOTES</span></span>

## <span data-ttu-id="d15cf-166">相关链接</span><span class="sxs-lookup"><span data-stu-id="d15cf-166">RELATED LINKS</span></span>

[<span data-ttu-id="d15cf-167">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d15cf-167">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="d15cf-168">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d15cf-168">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="d15cf-169">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="d15cf-169">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="d15cf-170">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d15cf-170">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="d15cf-171">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d15cf-171">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
