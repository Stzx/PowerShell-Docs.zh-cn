---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-psbreakpoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSBreakpoint
ms.openlocfilehash: 030f96cc99e42e19e78e1be2c4f913889d0567b6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197920"
---
# <span data-ttu-id="ded75-103">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ded75-103">Get-PSBreakpoint</span></span>

## <span data-ttu-id="ded75-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ded75-104">SYNOPSIS</span></span>
<span data-ttu-id="ded75-105">获取在当前会话中设置的断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-105">Gets the breakpoints that are set in the current session.</span></span>

## <span data-ttu-id="ded75-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ded75-106">SYNTAX</span></span>

### <span data-ttu-id="ded75-107">脚本 (默认值) </span><span class="sxs-lookup"><span data-stu-id="ded75-107">Script (Default)</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="ded75-108">变量</span><span class="sxs-lookup"><span data-stu-id="ded75-108">Variable</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Variable <String[]> [<CommonParameters>]
```

### <span data-ttu-id="ded75-109">命令</span><span class="sxs-lookup"><span data-stu-id="ded75-109">Command</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Command <String[]> [<CommonParameters>]
```

### <span data-ttu-id="ded75-110">类型</span><span class="sxs-lookup"><span data-stu-id="ded75-110">Type</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [-Type] <BreakpointType[]> [<CommonParameters>]
```

### <span data-ttu-id="ded75-111">ID</span><span class="sxs-lookup"><span data-stu-id="ded75-111">Id</span></span>

```
Get-PSBreakpoint [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="ded75-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ded75-112">DESCRIPTION</span></span>

<span data-ttu-id="ded75-113">**Set-psbreakpoint** cmdlet 获取在当前会话中设置的断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-113">The **Get-PSBreakPoint** cmdlet gets the breakpoints that are set in the current session.</span></span>
<span data-ttu-id="ded75-114">可以使用该 cmdlet 参数获取特定断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-114">You can use the cmdlet parameters to get particular breakpoints.</span></span>

<span data-ttu-id="ded75-115">断点是命令或脚本中的一个点，在该点处将暂时停止执行，以便你可以检查指令。</span><span class="sxs-lookup"><span data-stu-id="ded75-115">A breakpoint is a point in a command or script where execution stops temporarily so that you can examine the instructions.</span></span>
<span data-ttu-id="ded75-116">**Set-psbreakpoint** 是专门用于调试 Windows PowerShell 脚本和命令的几个 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="ded75-116">**Get-PSBreakpoint** is one of several cmdlets designed for debugging Windows PowerShell scripts and commands.</span></span> <span data-ttu-id="ded75-117">有关 Windows PowerShell 调试程序的详细信息，请参阅 about_Debuggers。</span><span class="sxs-lookup"><span data-stu-id="ded75-117">For more information about the Windows PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="ded75-118">示例</span><span class="sxs-lookup"><span data-stu-id="ded75-118">EXAMPLES</span></span>

### <span data-ttu-id="ded75-119">示例1：获取所有脚本和函数的所有断点</span><span class="sxs-lookup"><span data-stu-id="ded75-119">Example 1: Get all breakpoints for all scripts and functions</span></span>

```
PS C:\> Get-PSBreakpoint
```

<span data-ttu-id="ded75-120">此命令获取在当前会话中所有脚本和函数上设置的所有断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-120">This command gets all breakpoints set on all scripts and functions in the current session.</span></span>

### <span data-ttu-id="ded75-121">示例2：按 ID 获取断点</span><span class="sxs-lookup"><span data-stu-id="ded75-121">Example 2: Get breakpoints by ID</span></span>

```
PS C:\> Get-PSBreakpoint -Id 2
Function   :
IncrementAction     :
Enabled    :
TrueHitCount   : 0
Id         : 2
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="ded75-122">此命令获取断点 ID 为 2 的断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-122">This command gets the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="ded75-123">示例3：通过管道将 ID 发送到 Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ded75-123">Example 3: Pipe an ID to Get-PSBreakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Command "Increment"
PS C:\> $B.Id | Get-PSBreakpoint
```

<span data-ttu-id="ded75-124">这些命令演示如何通过将断点 ID 通过管道传递给 **set-psbreakpoint** 来获取断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-124">These commands show how to get a breakpoint by piping a breakpoint ID to **Get-PSBreakpoint** .</span></span>

<span data-ttu-id="ded75-125">第一个命令使用 Set-PSBreakpoint cmdlet 在 Sample.ps1 脚本中的 Increment 函数上创建断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-125">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Increment function in the Sample.ps1 script.</span></span> <span data-ttu-id="ded75-126">它将断点对象保存在 $B 变量中。</span><span class="sxs-lookup"><span data-stu-id="ded75-126">It saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="ded75-127">第二个命令使用点运算符 ( ) 获取 $B 变量中断点对象的 Id 属性。</span><span class="sxs-lookup"><span data-stu-id="ded75-127">The second command uses the dot operator (.) to get the Id property of the breakpoint object in the $B variable.</span></span> <span data-ttu-id="ded75-128">它使用管道运算符 (|) 将 ID 发送到 **set-psbreakpoint** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ded75-128">It uses a pipeline operator (|) to send the ID to the **Get-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="ded75-129">因此， **set-psbreakpoint** 将获取具有指定 ID 的断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-129">As a result, **Get-PSBreakpoint** gets the breakpoint with the specified ID.</span></span>

### <span data-ttu-id="ded75-130">示例4：获取指定脚本文件中的断点</span><span class="sxs-lookup"><span data-stu-id="ded75-130">Example 4: Get breakpoints in specified script files</span></span>

```
PS C:\> Get-PSBreakpoint -Script "Sample.ps1, SupportScript.ps1"
```

<span data-ttu-id="ded75-131">此命令获取 Sample.ps1 和 SupportScript.ps1 文件中的所有断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-131">This command gets all of the breakpoints in the Sample.ps1 and SupportScript.ps1 files.</span></span>

<span data-ttu-id="ded75-132">此命令不会获取可能在会话中的其他脚本或函数上设置的其他断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-132">This command does not get other breakpoints that might be set in other scripts or on functions in the session.</span></span>

### <span data-ttu-id="ded75-133">示例5：在指定的 cmdlet 中获取断点</span><span class="sxs-lookup"><span data-stu-id="ded75-133">Example 5: Get breakpoints in specified cmdlets</span></span>

```
PS C:\> Get-PSBreakpoint -Command "Read-Host, Write-Host" -Script "Sample.ps1"
```

<span data-ttu-id="ded75-134">此命令获取在 Sample.ps1 文件中的 Read-Host 或 Write-Host 命令上设置的所有 Command 断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-134">This command gets all Command breakpoints that are set on Read-Host or Write-Host commands in the Sample.ps1 file.</span></span>

### <span data-ttu-id="ded75-135">示例6：在指定的文件中获取命令断点</span><span class="sxs-lookup"><span data-stu-id="ded75-135">Example 6: Get Command breakpoints in a specified file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Command -Script "Sample.ps1"
```

<span data-ttu-id="ded75-136">此命令获取 Sample.ps1 文件中的所有 Command 断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-136">This command gets all Command breakpoints in the Sample.ps1 file.</span></span>

### <span data-ttu-id="ded75-137">示例7：按变量获取断点</span><span class="sxs-lookup"><span data-stu-id="ded75-137">Example 7: Get breakpoints by variable</span></span>

```
PS C:\> Get-PSBreakpoint -Variable "Index, Swap"
```

<span data-ttu-id="ded75-138">此命令获取在当前会话中的 $Index 和 $Swap 变量上设置的断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-138">This command gets breakpoints that are set on the $Index and $Swap variables in the current session.</span></span>

### <span data-ttu-id="ded75-139">示例8：获取文件中的所有行断点和变量断点</span><span class="sxs-lookup"><span data-stu-id="ded75-139">Example 8: Get all Line and Variable breakpoints in a file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Line, Variable -Script "Sample.ps1"
```

<span data-ttu-id="ded75-140">此命令获取 Sample.ps1 脚本中的所有行断点和变量断点。</span><span class="sxs-lookup"><span data-stu-id="ded75-140">This command gets all line and variable breakpoints in the Sample.ps1 script.</span></span>

## <span data-ttu-id="ded75-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ded75-141">PARAMETERS</span></span>

### <span data-ttu-id="ded75-142">-Command</span><span class="sxs-lookup"><span data-stu-id="ded75-142">-Command</span></span>

<span data-ttu-id="ded75-143">指定在指定命令名称上设置的命令断点的数组。</span><span class="sxs-lookup"><span data-stu-id="ded75-143">Specifies an array of command breakpoints that are set on the specified command names.</span></span>
<span data-ttu-id="ded75-144">输入命令名称，例如 cmdlet 或函数的名称。</span><span class="sxs-lookup"><span data-stu-id="ded75-144">Enter the command names, such as the name of a cmdlet or function.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ded75-145">-Id</span><span class="sxs-lookup"><span data-stu-id="ded75-145">-Id</span></span>

<span data-ttu-id="ded75-146">指定此 cmdlet 获取的断点 Id。</span><span class="sxs-lookup"><span data-stu-id="ded75-146">Specifies the breakpoint IDs that this cmdlet gets.</span></span>
<span data-ttu-id="ded75-147">将 ID 输入以逗号分隔的列表中。</span><span class="sxs-lookup"><span data-stu-id="ded75-147">Enter the IDs in a comma-separated list.</span></span>
<span data-ttu-id="ded75-148">还可以通过管道将断点 Id 传递给 **set-psbreakpoint** 。</span><span class="sxs-lookup"><span data-stu-id="ded75-148">You can also pipe breakpoint IDs to **Get-PSBreakpoint** .</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ded75-149">-Script</span><span class="sxs-lookup"><span data-stu-id="ded75-149">-Script</span></span>

<span data-ttu-id="ded75-150">指定包含断点的脚本数组。</span><span class="sxs-lookup"><span data-stu-id="ded75-150">Specifies an array of scripts that contain the breakpoints.</span></span>
<span data-ttu-id="ded75-151">输入一个或多个脚本文件的路径 (可选) 和名称。</span><span class="sxs-lookup"><span data-stu-id="ded75-151">Enter the path (optional) and names of one or more script files.</span></span>
<span data-ttu-id="ded75-152">如果省略路径，则默认位置为当前目录。</span><span class="sxs-lookup"><span data-stu-id="ded75-152">If you omit the path, the default location is the current directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Script, Variable, Command, Type
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ded75-153">-Type</span><span class="sxs-lookup"><span data-stu-id="ded75-153">-Type</span></span>

<span data-ttu-id="ded75-154">指定此 cmdlet 获取的断点类型的数组。</span><span class="sxs-lookup"><span data-stu-id="ded75-154">Specifies an array of breakpoint types that this cmdlet gets.</span></span>
<span data-ttu-id="ded75-155">输入一个或多个类型。</span><span class="sxs-lookup"><span data-stu-id="ded75-155">Enter one or more types.</span></span>
<span data-ttu-id="ded75-156">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="ded75-156">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ded75-157">Line</span><span class="sxs-lookup"><span data-stu-id="ded75-157">Line</span></span>
- <span data-ttu-id="ded75-158">命令</span><span class="sxs-lookup"><span data-stu-id="ded75-158">Command</span></span>
- <span data-ttu-id="ded75-159">变量</span><span class="sxs-lookup"><span data-stu-id="ded75-159">Variable</span></span>

<span data-ttu-id="ded75-160">还可以通过管道将断点类型传递给 **set-psbreakpoint** 。</span><span class="sxs-lookup"><span data-stu-id="ded75-160">You can also pipe breakpoint types to **Get-PSBreakPoint** .</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.BreakpointType[]
Parameter Sets: Type
Aliases:
Accepted values: Line, Variable, Command

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ded75-161">-Variable</span><span class="sxs-lookup"><span data-stu-id="ded75-161">-Variable</span></span>

<span data-ttu-id="ded75-162">指定在指定变量名称上设置的变量断点数组。</span><span class="sxs-lookup"><span data-stu-id="ded75-162">Specifies an array of variable breakpoints that are set on the specified variable names.</span></span>
<span data-ttu-id="ded75-163">输入不带美元符号的变量名称。</span><span class="sxs-lookup"><span data-stu-id="ded75-163">Enter the variable names without dollar signs.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ded75-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ded75-164">CommonParameters</span></span>

<span data-ttu-id="ded75-165">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ded75-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ded75-166">有关详细信息，请参阅 about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216) 。</span><span class="sxs-lookup"><span data-stu-id="ded75-166">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ded75-167">输入</span><span class="sxs-lookup"><span data-stu-id="ded75-167">INPUTS</span></span>

### <span data-ttu-id="ded75-168">System.object、BreakpointType 的命令</span><span class="sxs-lookup"><span data-stu-id="ded75-168">System.Int32, Microsoft.PowerShell.Commands.BreakpointType</span></span>

<span data-ttu-id="ded75-169">可以通过管道将断点 Id 和断点类型传递给 **set-psbreakpoint** 。</span><span class="sxs-lookup"><span data-stu-id="ded75-169">You can pipe breakpoint IDs and breakpoint types to **Get-PSBreakPoint** .</span></span>

## <span data-ttu-id="ded75-170">输出</span><span class="sxs-lookup"><span data-stu-id="ded75-170">OUTPUTS</span></span>

### <span data-ttu-id="ded75-171">System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="ded75-171">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="ded75-172">**Set-psbreakpoint** 返回表示会话中的断点的对象。</span><span class="sxs-lookup"><span data-stu-id="ded75-172">**Get-PSBreakPoint** returns objects that represent the breakpoints in the session.</span></span>

## <span data-ttu-id="ded75-173">注释</span><span class="sxs-lookup"><span data-stu-id="ded75-173">NOTES</span></span>

* <span data-ttu-id="ded75-174">可以使用 **set-psbreakpoint** 或其别名 "gbp"。</span><span class="sxs-lookup"><span data-stu-id="ded75-174">You can use **Get-PSBreakpoint** or its alias, "gbp".</span></span>

## <span data-ttu-id="ded75-175">相关链接</span><span class="sxs-lookup"><span data-stu-id="ded75-175">RELATED LINKS</span></span>

[<span data-ttu-id="ded75-176">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ded75-176">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="ded75-177">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ded75-177">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="ded75-178">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="ded75-178">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="ded75-179">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ded75-179">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="ded75-180">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ded75-180">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
