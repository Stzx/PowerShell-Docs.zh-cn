---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/push-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Push-Location
ms.openlocfilehash: abc40f3ae388a915c9df42d0c2df24f848e45e73
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "93199226"
---
# <span data-ttu-id="471e5-103">Push-Location</span><span class="sxs-lookup"><span data-stu-id="471e5-103">Push-Location</span></span>

## <span data-ttu-id="471e5-104">摘要</span><span class="sxs-lookup"><span data-stu-id="471e5-104">SYNOPSIS</span></span>
<span data-ttu-id="471e5-105">将当前位置添加到位置堆栈的顶部。</span><span class="sxs-lookup"><span data-stu-id="471e5-105">Adds the current location to the top of a location stack.</span></span>

## <span data-ttu-id="471e5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="471e5-106">SYNTAX</span></span>

### <span data-ttu-id="471e5-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="471e5-107">Path (Default)</span></span>

```
Push-Location [[-Path] <String>] [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="471e5-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="471e5-108">LiteralPath</span></span>

```
Push-Location [-LiteralPath <String>] [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="471e5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="471e5-109">DESCRIPTION</span></span>

<span data-ttu-id="471e5-110">`Push-Location`Cmdlet 将 ( "推送" ) 当前位置添加到位置堆栈上。</span><span class="sxs-lookup"><span data-stu-id="471e5-110">The `Push-Location` cmdlet adds ("pushes") the current location onto a location stack.</span></span> <span data-ttu-id="471e5-111">如果指定路径，则 `Push-Location` 将当前位置推送到位置堆栈上，然后将当前位置更改为路径指定的位置。</span><span class="sxs-lookup"><span data-stu-id="471e5-111">If you specify a path, `Push-Location` pushes the current location onto a location stack and then changes the current location to the location specified by the path.</span></span> <span data-ttu-id="471e5-112">可以使用 `Pop-Location` cmdlet 从位置堆栈中获取位置。</span><span class="sxs-lookup"><span data-stu-id="471e5-112">You can use the `Pop-Location` cmdlet to get locations from the location stack.</span></span>

<span data-ttu-id="471e5-113">默认情况下，该 `Push-Location` cmdlet 将当前位置推入当前位置堆栈，但你可以使用 **StackName** 参数来指定备用位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="471e5-113">By default, the `Push-Location` cmdlet pushes the current location onto the current location stack, but you can use the **StackName** parameter to specify an alternate location stack.</span></span> <span data-ttu-id="471e5-114">如果堆栈不存在，则 `Push-Location` 创建它。</span><span class="sxs-lookup"><span data-stu-id="471e5-114">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="471e5-115">有关位置堆栈的详细信息，请参阅 [注释](#notes)。</span><span class="sxs-lookup"><span data-stu-id="471e5-115">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="471e5-116">示例</span><span class="sxs-lookup"><span data-stu-id="471e5-116">EXAMPLES</span></span>

### <span data-ttu-id="471e5-117">示例 1</span><span class="sxs-lookup"><span data-stu-id="471e5-117">Example 1</span></span>

<span data-ttu-id="471e5-118">此示例将当前位置推入到默认位置堆栈中，然后将位置更改为 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="471e5-118">This example pushes the current location onto the default location stack and then changes the location to `C:\Windows`.</span></span>

```
PS C:\> Push-Location C:\Windows
```

### <span data-ttu-id="471e5-119">示例 2</span><span class="sxs-lookup"><span data-stu-id="471e5-119">Example 2</span></span>

<span data-ttu-id="471e5-120">此示例将当前位置推送到 RegFunction 堆栈上，并将当前位置更改为该 `HKLM:\Software\Policies` 位置。</span><span class="sxs-lookup"><span data-stu-id="471e5-120">This example pushes the current location onto the RegFunction stack and changes the current location to the `HKLM:\Software\Policies` location.</span></span>

```
PS C:\> Push-Location HKLM:\Software\Policies -StackName RegFunction
```

<span data-ttu-id="471e5-121">可以在任何 PowerShell 驱动器中使用 Location cmdlet (New-psdrive) 。</span><span class="sxs-lookup"><span data-stu-id="471e5-121">You can use the Location cmdlets in any PowerShell drive (PSDrive).</span></span>

### <span data-ttu-id="471e5-122">示例 3</span><span class="sxs-lookup"><span data-stu-id="471e5-122">Example 3</span></span>

<span data-ttu-id="471e5-123">此命令将当前位置推入到默认堆栈中。</span><span class="sxs-lookup"><span data-stu-id="471e5-123">This command pushes the current location onto the default stack.</span></span> <span data-ttu-id="471e5-124">它不会更改位置。</span><span class="sxs-lookup"><span data-stu-id="471e5-124">It does not change the location.</span></span>

```
PS C:\> Push-Location
```

### <span data-ttu-id="471e5-125">示例 4-创建并使用命名堆栈</span><span class="sxs-lookup"><span data-stu-id="471e5-125">Example 4 - Create and use a named stack</span></span>

<span data-ttu-id="471e5-126">这些命令展示了如何创建和使用已命名的位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="471e5-126">These commands show how to create and use a named location stack.</span></span>

```
PS C:\> Push-Location ~ -StackName Stack2
PS C:\Users\User01> Pop-Location -StackName Stack2
PS C:\>
```

<span data-ttu-id="471e5-127">第一个命令将当前位置推入到名为 Stack2 的新堆栈中，然后将当前位置更改为主目录，该目录在命令中用颚化符符号 (`~`) ，在 FileSystem 提供程序驱动器上使用的是与 `$HOME` 和等效的 `$env:USERPROFILE` 。</span><span class="sxs-lookup"><span data-stu-id="471e5-127">The first command pushes the current location onto a new stack named Stack2, and then changes the current location to the home directory, represented in the command by the tilde symbol (`~`), which when used on a FileSystem provider drives is equivalent to `$HOME` and `$env:USERPROFILE`.</span></span>

<span data-ttu-id="471e5-128">如果会话中尚不存在 Stack2，则将 `Push-Location` 创建它。</span><span class="sxs-lookup"><span data-stu-id="471e5-128">If Stack2 does not already exist in the session, `Push-Location` creates it.</span></span> <span data-ttu-id="471e5-129">第二个命令使用 `Pop-Location` cmdlet `C:\` 从 Stack2 堆栈中弹出原始位置 () 。</span><span class="sxs-lookup"><span data-stu-id="471e5-129">The second command uses the `Pop-Location` cmdlet to pop the original location (`C:\`) from the Stack2 stack.</span></span> <span data-ttu-id="471e5-130">如果没有 **StackName** 参数，则 `Pop-Location` 将从未命名的默认堆栈中弹出位置。</span><span class="sxs-lookup"><span data-stu-id="471e5-130">Without the **StackName** parameter, `Pop-Location` would pop the location from the unnamed default stack.</span></span>

<span data-ttu-id="471e5-131">有关位置堆栈的详细信息，请参阅 [注释](#notes)。</span><span class="sxs-lookup"><span data-stu-id="471e5-131">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="471e5-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="471e5-132">PARAMETERS</span></span>

### <span data-ttu-id="471e5-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="471e5-133">-LiteralPath</span></span>

<span data-ttu-id="471e5-134">指定新位置的路径。</span><span class="sxs-lookup"><span data-stu-id="471e5-134">Specifies the path to the new location.</span></span> <span data-ttu-id="471e5-135">与 **Path** 参数不同， **LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="471e5-135">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="471e5-136">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="471e5-136">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="471e5-137">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="471e5-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="471e5-138">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="471e5-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="471e5-139">-PassThru</span><span class="sxs-lookup"><span data-stu-id="471e5-139">-PassThru</span></span>

<span data-ttu-id="471e5-140">将表示位置的对象传递到管道。</span><span class="sxs-lookup"><span data-stu-id="471e5-140">Passes an object representing the location to the pipeline.</span></span> <span data-ttu-id="471e5-141">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="471e5-141">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471e5-142">-Path</span><span class="sxs-lookup"><span data-stu-id="471e5-142">-Path</span></span>

<span data-ttu-id="471e5-143">在此命令将当前位置添加（推入）到堆栈顶部之后，将把你的位置更改到由此路径指定的位置。</span><span class="sxs-lookup"><span data-stu-id="471e5-143">Changes your location to the location specified by this path after it adds (pushes) the current location onto the top of the stack.</span></span> <span data-ttu-id="471e5-144">输入其提供程序支持此 cmdlet 的任何位置的路径。</span><span class="sxs-lookup"><span data-stu-id="471e5-144">Enter a path to any location whose provider supports this cmdlet.</span></span> <span data-ttu-id="471e5-145">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="471e5-145">Wildcards are permitted.</span></span> <span data-ttu-id="471e5-146">参数名为可选项。</span><span class="sxs-lookup"><span data-stu-id="471e5-146">The parameter name is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="471e5-147">-StackName</span><span class="sxs-lookup"><span data-stu-id="471e5-147">-StackName</span></span>

<span data-ttu-id="471e5-148">指定要将当前位置添加到的位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="471e5-148">Specifies the location stack to which the current location is added.</span></span> <span data-ttu-id="471e5-149">输入位置堆栈名称。</span><span class="sxs-lookup"><span data-stu-id="471e5-149">Enter a location stack name.</span></span>
<span data-ttu-id="471e5-150">如果堆栈不存在，则 `Push-Location` 创建它。</span><span class="sxs-lookup"><span data-stu-id="471e5-150">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="471e5-151">如果没有此参数， `Push-Location` 则会将位置添加到当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="471e5-151">Without this parameter, `Push-Location` adds the location to the current location stack.</span></span> <span data-ttu-id="471e5-152">默认情况下，当前位置堆栈是 PowerShell 创建的未命名的默认位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="471e5-152">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span>
<span data-ttu-id="471e5-153">若要使位置堆栈成为当前位置堆栈，请使用 cmdlet 的 **StackName** 参数 `Set-Location` 。</span><span class="sxs-lookup"><span data-stu-id="471e5-153">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="471e5-154">有关位置堆栈的详细信息，请参阅 [注释](#notes)。</span><span class="sxs-lookup"><span data-stu-id="471e5-154">For more information about location stacks, see the [Notes](#notes).</span></span>

> [!NOTE]
> <span data-ttu-id="471e5-155">`Push-Location` 无法将某个位置添加到未命名的默认堆栈中，除非该堆栈为当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="471e5-155">`Push-Location` cannot add a location to the unnamed default stack unless it is the current location stack.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default stack
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="471e5-156">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="471e5-156">-UseTransaction</span></span>

<span data-ttu-id="471e5-157">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="471e5-157">Includes the command in the active transaction.</span></span> <span data-ttu-id="471e5-158">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="471e5-158">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="471e5-159">有关详细信息，请参阅 [about_Transactions](../Microsoft.PowerShell.Core/About/about_transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="471e5-159">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="471e5-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="471e5-160">CommonParameters</span></span>

<span data-ttu-id="471e5-161">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="471e5-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="471e5-162">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="471e5-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="471e5-163">输入</span><span class="sxs-lookup"><span data-stu-id="471e5-163">INPUTS</span></span>

### <span data-ttu-id="471e5-164">System.String</span><span class="sxs-lookup"><span data-stu-id="471e5-164">System.String</span></span>

<span data-ttu-id="471e5-165">你可以通过管道将包含路径 (但不) 文本路径的字符串传递给 `Push-Location` 。</span><span class="sxs-lookup"><span data-stu-id="471e5-165">You can pipe a string that contains a path (but not a literal path) to `Push-Location`.</span></span>

## <span data-ttu-id="471e5-166">输出</span><span class="sxs-lookup"><span data-stu-id="471e5-166">OUTPUTS</span></span>

### <span data-ttu-id="471e5-167">无或 System.Management.Automation.PathInfo</span><span class="sxs-lookup"><span data-stu-id="471e5-167">None or System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="471e5-168">当使用 **PassThru** 参数时，将 `Push-Location` 生成表示位置的 **PathInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="471e5-168">When you use the **PassThru** parameter, `Push-Location` generates a **System.Management.Automation.PathInfo** object that represents the location.</span></span> <span data-ttu-id="471e5-169">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="471e5-169">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="471e5-170">注释</span><span class="sxs-lookup"><span data-stu-id="471e5-170">NOTES</span></span>

<span data-ttu-id="471e5-171">PowerShell 支持每个进程运行多个运行空间。</span><span class="sxs-lookup"><span data-stu-id="471e5-171">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="471e5-172">每个运行空间都有其自己的 _当前目录_ 。</span><span class="sxs-lookup"><span data-stu-id="471e5-172">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="471e5-173">这与不相同 `[System.Environment]::CurrentDirectory` 。</span><span class="sxs-lookup"><span data-stu-id="471e5-173">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="471e5-174">调用 .NET Api 或运行本机应用程序时，如果不提供显式目录路径，则可能会出现这种问题。</span><span class="sxs-lookup"><span data-stu-id="471e5-174">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="471e5-175">即使位置 cmdlet 设置了进程范围的当前目录，也不能依赖于该目录，因为另一个运行空间可能会随时更改该目录。</span><span class="sxs-lookup"><span data-stu-id="471e5-175">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="471e5-176">应使用 location cmdlet，以使用当前特定于当前运行空间的工作目录执行基于路径的操作。</span><span class="sxs-lookup"><span data-stu-id="471e5-176">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="471e5-177">堆栈是后进先出的列表，其中只有最近添加的项是可访问的。</span><span class="sxs-lookup"><span data-stu-id="471e5-177">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span>
<span data-ttu-id="471e5-178">采用要使用项的顺序将这些项添加到堆栈，然后采用相反顺序检索这些项以供使用。</span><span class="sxs-lookup"><span data-stu-id="471e5-178">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="471e5-179">PowerShell 使你能够在位置堆栈中存储提供程序位置。</span><span class="sxs-lookup"><span data-stu-id="471e5-179">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="471e5-180">PowerShell 创建一个未命名的默认位置堆栈，你可以创建多个命名的位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="471e5-180">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="471e5-181">如果未指定堆栈名称，PowerShell 将使用当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="471e5-181">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="471e5-182">默认情况下，未命名的默认位置为当前位置堆栈，但你可以使用 `Set-Location` cmdlet 来更改当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="471e5-182">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="471e5-183">若要管理位置堆栈，请使用 PowerShell 位置 cmdlet，如下所示。</span><span class="sxs-lookup"><span data-stu-id="471e5-183">To manage location stacks, use the PowerShell Location cmdlets, as follows.</span></span>

- <span data-ttu-id="471e5-184">若要将位置添加到位置堆栈，请使用 `Push-Location` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="471e5-184">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="471e5-185">若要从位置堆栈获取位置，请使用 `Pop-Location` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="471e5-185">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="471e5-186">若要显示当前位置堆栈中的位置，请使用 cmdlet 的 **stack** 参数 `Get-Location` 。</span><span class="sxs-lookup"><span data-stu-id="471e5-186">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="471e5-187">若要显示命名位置堆栈中的位置，请使用 cmdlet 的 **StackName** 参数 `Get-Location` 。</span><span class="sxs-lookup"><span data-stu-id="471e5-187">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="471e5-188">若要创建新的位置堆栈，请使用 cmdlet 的 StackName 参数 `Push-Location` 。</span><span class="sxs-lookup"><span data-stu-id="471e5-188">To create a new location stack, use the StackName parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="471e5-189">如果指定不存在的堆栈， `Push-Location` 将创建堆栈。</span><span class="sxs-lookup"><span data-stu-id="471e5-189">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="471e5-190">若要使位置堆栈成为当前位置堆栈，请使用 cmdlet 的 StackName 参数 `Set-Location` 。</span><span class="sxs-lookup"><span data-stu-id="471e5-190">To make a location stack the current location stack, use the StackName parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="471e5-191">未命名的默认位置堆栈仅在其是当前位置堆栈时处于完全可访问状态。</span><span class="sxs-lookup"><span data-stu-id="471e5-191">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="471e5-192">如果使命名位置堆栈成为当前位置堆栈，则不能再使用 `Push-Location` 或 `Pop-Location` cmdlet 来添加或获取默认堆栈中的项，也不能使用 `Get-Location` cmdlet 来显示未命名堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="471e5-192">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="471e5-193">若要使未命名堆栈成为当前堆栈，请使用 cmdlet 的 **StackName** 参数，其 `Set-Location` 值为 `$null` 或空字符串 (`""`) 。</span><span class="sxs-lookup"><span data-stu-id="471e5-193">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="471e5-194">还可以 `Push-Location` 通过其内置别名来引用 `pushd` 。</span><span class="sxs-lookup"><span data-stu-id="471e5-194">You can also refer to `Push-Location` by its built-in alias, `pushd`.</span></span> <span data-ttu-id="471e5-195">有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="471e5-195">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="471e5-196">`Push-Location`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="471e5-196">The `Push-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="471e5-197">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="471e5-197">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="471e5-198">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="471e5-198">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="471e5-199">相关链接</span><span class="sxs-lookup"><span data-stu-id="471e5-199">RELATED LINKS</span></span>

[<span data-ttu-id="471e5-200">Get-Location</span><span class="sxs-lookup"><span data-stu-id="471e5-200">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="471e5-201">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="471e5-201">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="471e5-202">Set-Location</span><span class="sxs-lookup"><span data-stu-id="471e5-202">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="471e5-203">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="471e5-203">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="471e5-204">about_Providers</span><span class="sxs-lookup"><span data-stu-id="471e5-204">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
