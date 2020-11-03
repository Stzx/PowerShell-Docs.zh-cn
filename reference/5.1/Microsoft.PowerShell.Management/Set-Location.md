---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: 06b1596366c9c9e20857b55aa9a17342bab07028
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "93199318"
---
# <span data-ttu-id="65dae-103">Set-Location</span><span class="sxs-lookup"><span data-stu-id="65dae-103">Set-Location</span></span>

## <span data-ttu-id="65dae-104">摘要</span><span class="sxs-lookup"><span data-stu-id="65dae-104">SYNOPSIS</span></span>
<span data-ttu-id="65dae-105">将当前工作位置设置为指定的位置。</span><span class="sxs-lookup"><span data-stu-id="65dae-105">Sets the current working location to a specified location.</span></span>

## <span data-ttu-id="65dae-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="65dae-106">SYNTAX</span></span>

### <span data-ttu-id="65dae-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="65dae-107">Path (Default)</span></span>

```
Set-Location [[-Path] <String>] [-PassThru] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="65dae-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="65dae-108">LiteralPath</span></span>

```
Set-Location -LiteralPath <String> [-PassThru] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="65dae-109">堆栈</span><span class="sxs-lookup"><span data-stu-id="65dae-109">Stack</span></span>

```
Set-Location [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="65dae-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="65dae-110">DESCRIPTION</span></span>

<span data-ttu-id="65dae-111">`Set-Location`Cmdlet 将工作位置设置为指定的位置。</span><span class="sxs-lookup"><span data-stu-id="65dae-111">The `Set-Location` cmdlet sets the working location to a specified location.</span></span> <span data-ttu-id="65dae-112">该位置可以是目录、子目录、注册表位置或任何提供程序路径。</span><span class="sxs-lookup"><span data-stu-id="65dae-112">That location could be a directory, a subdirectory, a registry location, or any provider path.</span></span>

<span data-ttu-id="65dae-113">还可以使用 **StackName** 参数使命名位置堆栈成为当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="65dae-113">You can also use the **StackName** parameter to make a named location stack the current location stack.</span></span> <span data-ttu-id="65dae-114">有关位置堆栈的详细信息，请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="65dae-114">For more information about location stacks, see the Notes.</span></span>

## <span data-ttu-id="65dae-115">示例</span><span class="sxs-lookup"><span data-stu-id="65dae-115">EXAMPLES</span></span>

### <span data-ttu-id="65dae-116">示例1：设置当前位置</span><span class="sxs-lookup"><span data-stu-id="65dae-116">Example 1: Set the current location</span></span>

```powershell
PS C:\> Set-Location -Path "HKLM:\"
```

```output
PS HKLM:\>
```

<span data-ttu-id="65dae-117">此命令将当前位置设置为驱动器的根目录 `HKLM:` 。</span><span class="sxs-lookup"><span data-stu-id="65dae-117">This command sets the current location to the root of the `HKLM:` drive.</span></span>

### <span data-ttu-id="65dae-118">示例2：设置当前位置并显示该位置</span><span class="sxs-lookup"><span data-stu-id="65dae-118">Example 2: Set the current location and display that location</span></span>

```powershell
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```output
Path
----
Env:\

PS Env:\>
```

<span data-ttu-id="65dae-119">此命令将当前位置设置为驱动器的根目录 `Env:` 。</span><span class="sxs-lookup"><span data-stu-id="65dae-119">This command sets the current location to the root of the `Env:` drive.</span></span> <span data-ttu-id="65dae-120">它使用 **PassThru** 参数来指示 PowerShell 返回表示位置的 **PathInfo** 对象 `Env:\` 。</span><span class="sxs-lookup"><span data-stu-id="65dae-120">It uses the **PassThru** parameter to direct PowerShell to return a **PathInfo** object that represents the `Env:\` location.</span></span>

### <span data-ttu-id="65dae-121">示例3：将位置设置为 C：驱动器中的当前位置</span><span class="sxs-lookup"><span data-stu-id="65dae-121">Example 3: Set location to the current location in the C: drive</span></span>

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

<span data-ttu-id="65dae-122">第一个命令将位置设置为 `HKLM:` 注册表提供程序中驱动器的根目录。</span><span class="sxs-lookup"><span data-stu-id="65dae-122">The first command sets the location to the root of the `HKLM:` drive in the Registry provider.</span></span>
<span data-ttu-id="65dae-123">第二个命令将位置设置为 `C:` FileSystem 提供程序中驱动器的当前位置。</span><span class="sxs-lookup"><span data-stu-id="65dae-123">The second command sets the location to the current location of the `C:` drive in the FileSystem provider.</span></span>
<span data-ttu-id="65dae-124">如果以格式指定驱动器名称时 `<DriveName>:` (没有反斜杠) ，则该 cmdlet 会将该位置设置为 new-psdrive 中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="65dae-124">When the drive name is specified in the form `<DriveName>:` (without backslash), the cmdlet sets the location to the current location in the PSDrive.</span></span>
<span data-ttu-id="65dae-125">获取 New-psdrive use 命令中的当前位置 `Get-Location -PSDrive <DriveName>` 。</span><span class="sxs-lookup"><span data-stu-id="65dae-125">To get the current location in the PSDrive use `Get-Location -PSDrive <DriveName>` command.</span></span>

### <span data-ttu-id="65dae-126">示例4：将当前位置设置为命名堆栈</span><span class="sxs-lookup"><span data-stu-id="65dae-126">Example 4: Set the current location to a named stack</span></span>

```powershell
PS C:\> Push-Location -Path 'C:\Program Files\PowerShell\' -StackName "Paths"
PS C:\Program Files\PowerShell\> Set-Location -StackName "Paths"
PS C:\Program Files\PowerShell\> Get-Location -Stack
```

```Output
Path
----
C:\
```

<span data-ttu-id="65dae-127">第一个命令将当前位置添加到路径堆栈。</span><span class="sxs-lookup"><span data-stu-id="65dae-127">The first command adds the current location to the Paths stack.</span></span>
<span data-ttu-id="65dae-128">第二个命令使路径位置堆栈成为当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="65dae-128">The second command makes the Paths location stack the current location stack.</span></span>
<span data-ttu-id="65dae-129">第三个命令显示当前位置堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="65dae-129">The third command displays the locations in the current location stack.</span></span>

<span data-ttu-id="65dae-130">`*-Location`除非在命令中指定了其他位置堆栈，否则 cmdlet 将使用当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="65dae-130">The `*-Location` cmdlets use the current location stack unless a different location stack is specified in the command.</span></span> <span data-ttu-id="65dae-131">有关位置堆栈的信息，请参阅 [注释](#notes)。</span><span class="sxs-lookup"><span data-stu-id="65dae-131">For information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="65dae-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="65dae-132">PARAMETERS</span></span>

### <span data-ttu-id="65dae-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="65dae-133">-LiteralPath</span></span>

<span data-ttu-id="65dae-134">指定位置的路径。</span><span class="sxs-lookup"><span data-stu-id="65dae-134">Specifies a path of the location.</span></span> <span data-ttu-id="65dae-135">**LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="65dae-135">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="65dae-136">不会将任何字符解释为通配字符。</span><span class="sxs-lookup"><span data-stu-id="65dae-136">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="65dae-137">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="65dae-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="65dae-138">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="65dae-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="65dae-139">单引号会告知 Windows PowerShell 不要将所有字符都解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="65dae-139">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65dae-140">-PassThru</span><span class="sxs-lookup"><span data-stu-id="65dae-140">-PassThru</span></span>

<span data-ttu-id="65dae-141">返回表示位置的 **PathInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="65dae-141">Returns a **PathInfo** object that represents the location.</span></span> <span data-ttu-id="65dae-142">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="65dae-142">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="65dae-143">-Path</span><span class="sxs-lookup"><span data-stu-id="65dae-143">-Path</span></span>

<span data-ttu-id="65dae-144">指定新工作位置的路径。</span><span class="sxs-lookup"><span data-stu-id="65dae-144">Specify the path of a new working location.</span></span> <span data-ttu-id="65dae-145">如果未提供路径，则 `Set-Location` 默认为当前用户的主目录。</span><span class="sxs-lookup"><span data-stu-id="65dae-145">If no path is provided, `Set-Location` defaults to the current user's home directory.</span></span> <span data-ttu-id="65dae-146">使用通配符时，该 cmdlet 将选择与通配符模式匹配的第一个路径。</span><span class="sxs-lookup"><span data-stu-id="65dae-146">When wildcards are used, the cmdlet chooses the first path that matches the wildcard pattern.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="65dae-147">-StackName</span><span class="sxs-lookup"><span data-stu-id="65dae-147">-StackName</span></span>

<span data-ttu-id="65dae-148">指定此 cmdlet 生成当前位置堆栈的现有位置堆栈名称。</span><span class="sxs-lookup"><span data-stu-id="65dae-148">Specifies the existing location stack name that this cmdlet makes the current location stack.</span></span> <span data-ttu-id="65dae-149">输入位置堆栈名称。</span><span class="sxs-lookup"><span data-stu-id="65dae-149">Enter a location stack name.</span></span> <span data-ttu-id="65dae-150">若要指明未命名的默认位置堆栈，请键入 `$null` 或 () 的空字符串 `""` 。</span><span class="sxs-lookup"><span data-stu-id="65dae-150">To indicate the unnamed default location stack, type `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="65dae-151">`*-Location`Cmdlet 将作用于当前堆栈，除非使用 **StackName** 参数指定其他堆栈。</span><span class="sxs-lookup"><span data-stu-id="65dae-151">The `*-Location` cmdlets act on the current stack unless you use the **StackName** parameter to specify a different stack.</span></span>

```yaml
Type: System.String
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65dae-152">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="65dae-152">-UseTransaction</span></span>

<span data-ttu-id="65dae-153">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="65dae-153">Includes the command in the active transaction.</span></span>
<span data-ttu-id="65dae-154">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="65dae-154">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="65dae-155">有关详细信息，请参阅 about_Transactions。</span><span class="sxs-lookup"><span data-stu-id="65dae-155">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="65dae-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="65dae-156">CommonParameters</span></span>

<span data-ttu-id="65dae-157">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="65dae-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="65dae-158">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="65dae-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="65dae-159">输入</span><span class="sxs-lookup"><span data-stu-id="65dae-159">INPUTS</span></span>

### <span data-ttu-id="65dae-160">System.String</span><span class="sxs-lookup"><span data-stu-id="65dae-160">System.String</span></span>

<span data-ttu-id="65dae-161">可以通过管道将包含路径（但不是文本路径）的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="65dae-161">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="65dae-162">输出</span><span class="sxs-lookup"><span data-stu-id="65dae-162">OUTPUTS</span></span>

### <span data-ttu-id="65dae-163">无、System.Management.Automation.PathInfo、System.Management.Automation.PathInfoStack</span><span class="sxs-lookup"><span data-stu-id="65dae-163">None, System.Management.Automation.PathInfo, System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="65dae-164">除非指定 **PassThru** 参数，否则此 cmdlet 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="65dae-164">This cmdlet does not generate any output unless you specify the **PassThru** parameter.</span></span> <span data-ttu-id="65dae-165">结合使用 **PassThru** 和 **Path** 或 **LiteralPath** 将生成一个表示新位置的 **PathInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="65dae-165">Using **PassThru** with **Path** or **LiteralPath** generates a **PathInfo** object that represents the new location.</span></span> <span data-ttu-id="65dae-166">结合使用 **PassThru** 和 **StackName** 将生成表示新堆栈上下文的 **system.management.automation.pathinfostack** 对象。</span><span class="sxs-lookup"><span data-stu-id="65dae-166">Using **PassThru** with **StackName** generates a **PathInfoStack** object representing the new stack context.</span></span>

## <span data-ttu-id="65dae-167">注释</span><span class="sxs-lookup"><span data-stu-id="65dae-167">NOTES</span></span>

<span data-ttu-id="65dae-168">PowerShell 支持每个进程运行多个运行空间。</span><span class="sxs-lookup"><span data-stu-id="65dae-168">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="65dae-169">每个运行空间都有其自己的 _当前目录_ 。</span><span class="sxs-lookup"><span data-stu-id="65dae-169">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="65dae-170">这与不相同 `[System.Environment]::CurrentDirectory` 。</span><span class="sxs-lookup"><span data-stu-id="65dae-170">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="65dae-171">调用 .NET Api 或运行本机应用程序时，如果不提供显式目录路径，则可能会出现这种问题。</span><span class="sxs-lookup"><span data-stu-id="65dae-171">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="65dae-172">即使位置 cmdlet 设置了进程范围的当前目录，也不能依赖于该目录，因为另一个运行空间可能会随时更改该目录。</span><span class="sxs-lookup"><span data-stu-id="65dae-172">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="65dae-173">应使用 location cmdlet，以使用当前特定于当前运行空间的工作目录执行基于路径的操作。</span><span class="sxs-lookup"><span data-stu-id="65dae-173">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="65dae-174">`Set-Location`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="65dae-174">The `Set-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="65dae-175">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="65dae-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="65dae-176">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="65dae-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span></span>

<span data-ttu-id="65dae-177">堆栈是一种后进先出的列表，在其中只能访问最后添加的项。</span><span class="sxs-lookup"><span data-stu-id="65dae-177">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="65dae-178">采用要使用项的顺序将这些项添加到堆栈，然后采用相反顺序检索这些项以供使用。</span><span class="sxs-lookup"><span data-stu-id="65dae-178">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="65dae-179">PowerShell 使你能够在位置堆栈中存储提供程序位置。</span><span class="sxs-lookup"><span data-stu-id="65dae-179">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="65dae-180">PowerShell 创建一个未命名的默认位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="65dae-180">PowerShell creates an unnamed default location stack.</span></span> <span data-ttu-id="65dae-181">可以创建多个命名的位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="65dae-181">You can create multiple named location stacks.</span></span> <span data-ttu-id="65dae-182">如果未指定堆栈名称，PowerShell 将使用当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="65dae-182">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="65dae-183">默认情况下，未命名的默认位置为当前位置堆栈，但你可以使用 `Set-Location` cmdlet 来更改当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="65dae-183">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="65dae-184">若要管理位置堆栈，请使用 `*-Location` cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="65dae-184">To manage location stacks, use the `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="65dae-185">若要将位置添加到位置堆栈，请使用 `Push-Location` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="65dae-185">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="65dae-186">若要从位置堆栈获取位置，请使用 `Pop-Location` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="65dae-186">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="65dae-187">若要显示当前位置堆栈中的位置，请使用 cmdlet 的 **stack** 参数 `Get-Location` 。</span><span class="sxs-lookup"><span data-stu-id="65dae-187">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="65dae-188">若要显示命名位置堆栈中的位置，请使用的 **StackName** 参数 `Get-Location` 。</span><span class="sxs-lookup"><span data-stu-id="65dae-188">To display the locations in a named location stack, use the **StackName** parameter of `Get-Location`.</span></span>

- <span data-ttu-id="65dae-189">若要创建新的位置堆栈，请使用的 **StackName** 参数 `Push-Location` 。</span><span class="sxs-lookup"><span data-stu-id="65dae-189">To create a new location stack, use the **StackName** parameter of `Push-Location`.</span></span> <span data-ttu-id="65dae-190">如果指定不存在的堆栈， `Push-Location` 将创建堆栈。</span><span class="sxs-lookup"><span data-stu-id="65dae-190">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="65dae-191">若要使某个位置堆栈成为当前位置堆栈，请使用的 **StackName** 参数 `Set-Location` 。</span><span class="sxs-lookup"><span data-stu-id="65dae-191">To make a location stack the current location stack, use the **StackName** parameter of `Set-Location`.</span></span>

<span data-ttu-id="65dae-192">未命名的默认位置堆栈仅在其是当前位置堆栈时处于完全可访问状态。</span><span class="sxs-lookup"><span data-stu-id="65dae-192">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="65dae-193">如果使命名位置堆栈成为当前位置堆栈，则不能再使用 `Push-Location` 或 `Pop-Location` cmdlet 来添加或获取默认堆栈中的项，也不能使用 `Get-Location` cmdlet 来显示未命名堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="65dae-193">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="65dae-194">若要使未命名堆栈成为当前堆栈，请使用 cmdlet 的 **StackName** 参数，其 `Set-Location` 值为 `$null` 或空字符串 (`""`) 。</span><span class="sxs-lookup"><span data-stu-id="65dae-194">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="65dae-195">相关链接</span><span class="sxs-lookup"><span data-stu-id="65dae-195">RELATED LINKS</span></span>

[<span data-ttu-id="65dae-196">Get-Location</span><span class="sxs-lookup"><span data-stu-id="65dae-196">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="65dae-197">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="65dae-197">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="65dae-198">Push-Location</span><span class="sxs-lookup"><span data-stu-id="65dae-198">Push-Location</span></span>](Push-Location.md)
