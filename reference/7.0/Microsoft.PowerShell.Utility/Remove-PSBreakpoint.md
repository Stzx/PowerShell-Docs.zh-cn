---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-psbreakpoint?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSBreakpoint
ms.openlocfilehash: 04f8da7042d6bf07c6af893aa3601ed572c94e38
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197000"
---
# <span data-ttu-id="08a67-103">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="08a67-103">Remove-PSBreakpoint</span></span>

## <span data-ttu-id="08a67-104">摘要</span><span class="sxs-lookup"><span data-stu-id="08a67-104">SYNOPSIS</span></span>
<span data-ttu-id="08a67-105">从当前控制台中删除断点。</span><span class="sxs-lookup"><span data-stu-id="08a67-105">Deletes breakpoints from the current console.</span></span>

## <span data-ttu-id="08a67-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="08a67-106">SYNTAX</span></span>

### <span data-ttu-id="08a67-107">Breakpoint（默认值）</span><span class="sxs-lookup"><span data-stu-id="08a67-107">Breakpoint (Default)</span></span>

```
Remove-PSBreakpoint [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="08a67-108">ID</span><span class="sxs-lookup"><span data-stu-id="08a67-108">Id</span></span>

```
Remove-PSBreakpoint [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="08a67-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08a67-109">DESCRIPTION</span></span>
<span data-ttu-id="08a67-110">**Remove-PSBreakpoint** cmdlet 可删除断点。</span><span class="sxs-lookup"><span data-stu-id="08a67-110">The **Remove-PSBreakpoint** cmdlet deletes a breakpoint.</span></span>
<span data-ttu-id="08a67-111">输入一个断点对象或断点 ID。</span><span class="sxs-lookup"><span data-stu-id="08a67-111">Enter a breakpoint object or a breakpoint ID.</span></span>

<span data-ttu-id="08a67-112">当你删除断点时，断点对象将不再可用或无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="08a67-112">When you remove a breakpoint, the breakpoint object is no longer available or functional.</span></span>
<span data-ttu-id="08a67-113">如果你已将断点对象保存在变量中，则引用仍然存在，但该断点无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="08a67-113">If you have saved a breakpoint object in a variable, the reference still exists, but the breakpoint does not function.</span></span>

<span data-ttu-id="08a67-114">**Set-psbreakpoint** 是设计用于调试 PowerShell 脚本的多个 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="08a67-114">**Remove-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="08a67-115">有关 PowerShell 调试器的详细信息，请参阅 about_Debuggers。</span><span class="sxs-lookup"><span data-stu-id="08a67-115">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="08a67-116">示例</span><span class="sxs-lookup"><span data-stu-id="08a67-116">EXAMPLES</span></span>

### <span data-ttu-id="08a67-117">示例 1：删除所有断点</span><span class="sxs-lookup"><span data-stu-id="08a67-117">Example 1: Remove all breakpoints</span></span>

```
PS C:\> Get-PSBreakpoint | Remove-PSBreakpoint
```

<span data-ttu-id="08a67-118">此命令将删除当前控制台中的所有断点。</span><span class="sxs-lookup"><span data-stu-id="08a67-118">This command deletes all of the breakpoints in the current console.</span></span>

### <span data-ttu-id="08a67-119">示例 2：删除指定断点</span><span class="sxs-lookup"><span data-stu-id="08a67-119">Example 2: Remove a specified breakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "Name"
PS C:\> $B | Remove-PSBreakpoint
```

<span data-ttu-id="08a67-120">此命令将删除断点。</span><span class="sxs-lookup"><span data-stu-id="08a67-120">This command deletes a breakpoint.</span></span>

<span data-ttu-id="08a67-121">第一个命令使用 Set-PSBreakpoint cmdlet 在 Sample.ps1 脚本中的 Name 变量上创建断点。</span><span class="sxs-lookup"><span data-stu-id="08a67-121">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Name variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="08a67-122">然后，它将断点对象保存在 $B 变量中。</span><span class="sxs-lookup"><span data-stu-id="08a67-122">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="08a67-123">第二个命令使用 **Remove-PSBreakpoint** cmdlet 删除新断点。</span><span class="sxs-lookup"><span data-stu-id="08a67-123">The second command uses the **Remove-PSBreakpoint** cmdlet to delete the new breakpoint.</span></span>
<span data-ttu-id="08a67-124">它使用管道运算符 (|) 将 $B 变量中的断点对象发送到 **Remove-PSBreakpoint** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="08a67-124">It uses a pipeline operator (|) to send the breakpoint object in the $B variable to the **Remove-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="08a67-125">此命令的结果是：如果你运行该脚本，则它将一直运行直至完成。</span><span class="sxs-lookup"><span data-stu-id="08a67-125">As a result of this command, if you run the script, it runs to completion without stopping.</span></span>
<span data-ttu-id="08a67-126">此外， **Get-PSBreakpoint** 不会返回此断点。</span><span class="sxs-lookup"><span data-stu-id="08a67-126">Also, the **Get-PSBreakpoint** cmdlet does not return this breakpoint.</span></span>

### <span data-ttu-id="08a67-127">示例 3：按 ID 删除断点</span><span class="sxs-lookup"><span data-stu-id="08a67-127">Example 3: Remove a breakpoint by ID</span></span>

```
PS C:\> Remove-PSBreakpoint -Id 2
```

<span data-ttu-id="08a67-128">此命令将删除断点 ID 为 2 的断点。</span><span class="sxs-lookup"><span data-stu-id="08a67-128">This command deletes the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="08a67-129">示例 4：使用函数删除所有断点</span><span class="sxs-lookup"><span data-stu-id="08a67-129">Example 4: Use a function to remove all breakpoints</span></span>

```
PS C:\> function del-psb { get-psbreakpoint | remove-psbreakpoint }
```

<span data-ttu-id="08a67-130">此简单函数将删除当前控制台中的所有断点。</span><span class="sxs-lookup"><span data-stu-id="08a67-130">This simple function deletes all of the breakpoints in the current console.</span></span>
<span data-ttu-id="08a67-131">它使用 Get-PSBreakpoint 来获取这些断点。</span><span class="sxs-lookup"><span data-stu-id="08a67-131">It uses the Get-PSBreakpoint cmdlet to get the breakpoints.</span></span>
<span data-ttu-id="08a67-132">然后，它使用管道运算符 (|) 将这些断点发送到 **Remove-PSBreakpoint** cmdlet，后者再将删除它们。</span><span class="sxs-lookup"><span data-stu-id="08a67-132">Then, it uses a pipeline operator (|) to send the breakpoints to the **Remove-PSBreakpoint** cmdlet, which deletes them.</span></span>

<span data-ttu-id="08a67-133">因此，你可以输入 `del-psb`，而不是输入更长的命令。</span><span class="sxs-lookup"><span data-stu-id="08a67-133">As a result, you can type `del-psb` instead of the longer command.</span></span>

<span data-ttu-id="08a67-134">若要保存该函数，请将其添加到 PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="08a67-134">To save the function, add it to your PowerShell profile.</span></span>

## <span data-ttu-id="08a67-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="08a67-135">PARAMETERS</span></span>

### <span data-ttu-id="08a67-136">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="08a67-136">-Breakpoint</span></span>
<span data-ttu-id="08a67-137">指定要删除的断点。</span><span class="sxs-lookup"><span data-stu-id="08a67-137">Specifies the breakpoints to delete.</span></span>
<span data-ttu-id="08a67-138">输入一个包含断点对象的变量，或可获取断点对象的命令（如 **Get-PSBreakpoint** 命令）。</span><span class="sxs-lookup"><span data-stu-id="08a67-138">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a **Get-PSBreakpoint** command.</span></span>
<span data-ttu-id="08a67-139">你还可以通过管道将断点对象传递给 **Remove-PSBreakpoint** 。</span><span class="sxs-lookup"><span data-stu-id="08a67-139">You can also pipe breakpoint objects to **Remove-PSBreakpoint** .</span></span>

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

### <span data-ttu-id="08a67-140">-Id</span><span class="sxs-lookup"><span data-stu-id="08a67-140">-Id</span></span>
<span data-ttu-id="08a67-141">指定此 cmdlet 为其删除断点的断点 ID。</span><span class="sxs-lookup"><span data-stu-id="08a67-141">Specifies breakpoint IDs for which this cmdlet deletes breakpoints.</span></span>

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

### <span data-ttu-id="08a67-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="08a67-142">-Confirm</span></span>
<span data-ttu-id="08a67-143">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="08a67-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="08a67-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="08a67-144">-WhatIf</span></span>
<span data-ttu-id="08a67-145">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="08a67-145">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="08a67-146">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="08a67-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="08a67-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="08a67-147">CommonParameters</span></span>
<span data-ttu-id="08a67-148">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="08a67-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="08a67-149">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="08a67-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="08a67-150">输入</span><span class="sxs-lookup"><span data-stu-id="08a67-150">INPUTS</span></span>

### <span data-ttu-id="08a67-151">System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="08a67-151">System.Management.Automation.Breakpoint</span></span>
<span data-ttu-id="08a67-152">可以通过管道将断点对象传递给 **Remove-PSBreakpoint** 。</span><span class="sxs-lookup"><span data-stu-id="08a67-152">You can pipe breakpoint objects to **Remove-PSBreakpoint** .</span></span>

## <span data-ttu-id="08a67-153">输出</span><span class="sxs-lookup"><span data-stu-id="08a67-153">OUTPUTS</span></span>

### <span data-ttu-id="08a67-154">无</span><span class="sxs-lookup"><span data-stu-id="08a67-154">None</span></span>
<span data-ttu-id="08a67-155">该 cmdlet 不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="08a67-155">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="08a67-156">注释</span><span class="sxs-lookup"><span data-stu-id="08a67-156">NOTES</span></span>

## <span data-ttu-id="08a67-157">相关链接</span><span class="sxs-lookup"><span data-stu-id="08a67-157">RELATED LINKS</span></span>

[<span data-ttu-id="08a67-158">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="08a67-158">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="08a67-159">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="08a67-159">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="08a67-160">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="08a67-160">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="08a67-161">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="08a67-161">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="08a67-162">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="08a67-162">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
