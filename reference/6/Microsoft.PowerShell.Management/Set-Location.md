---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: e1432a8ae6826e7f2c47f35c9cc01df20edde85c
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "93199320"
---
# <span data-ttu-id="9dc9a-103">Set-Location</span><span class="sxs-lookup"><span data-stu-id="9dc9a-103">Set-Location</span></span>

## <span data-ttu-id="9dc9a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9dc9a-104">SYNOPSIS</span></span>
<span data-ttu-id="9dc9a-105">将当前工作位置设置为指定的位置。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-105">Sets the current working location to a specified location.</span></span>

## <span data-ttu-id="9dc9a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9dc9a-106">SYNTAX</span></span>

### <span data-ttu-id="9dc9a-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="9dc9a-107">Path (Default)</span></span>

```
Set-Location [[-Path] <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="9dc9a-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9dc9a-108">LiteralPath</span></span>

```
Set-Location -LiteralPath <String> [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="9dc9a-109">堆栈</span><span class="sxs-lookup"><span data-stu-id="9dc9a-109">Stack</span></span>

```
Set-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="9dc9a-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9dc9a-110">DESCRIPTION</span></span>

<span data-ttu-id="9dc9a-111">`Set-Location`Cmdlet 将工作位置设置为指定的位置。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-111">The `Set-Location` cmdlet sets the working location to a specified location.</span></span> <span data-ttu-id="9dc9a-112">该位置可以是目录、子目录、注册表位置或任何提供程序路径。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-112">That location could be a directory, a subdirectory, a registry location, or any provider path.</span></span>

<span data-ttu-id="9dc9a-113">PowerShell 6.2 添加了对 `-` 和的支持， `+` 作为 **Path** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-113">PowerShell 6.2 added support for `-` and `+` as a values for the **Path** parameter.</span></span> <span data-ttu-id="9dc9a-114">PowerShell 维护可使用和访问的最后20个位置的历史记录 `-` `+` 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-114">PowerShell maintains a history of the last 20 locations that can be accessed with `-` and `+`.</span></span> <span data-ttu-id="9dc9a-115">此列表独立于使用 **StackName** 参数访问的位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-115">This list is independent from the location stack that is accessed using the **StackName** parameter.</span></span>

## <span data-ttu-id="9dc9a-116">示例</span><span class="sxs-lookup"><span data-stu-id="9dc9a-116">EXAMPLES</span></span>

### <span data-ttu-id="9dc9a-117">示例1：设置当前位置</span><span class="sxs-lookup"><span data-stu-id="9dc9a-117">Example 1: Set the current location</span></span>

```
PS C:\> Set-Location -Path "HKLM:\"
PS HKLM:\>
```

<span data-ttu-id="9dc9a-118">此命令将当前位置设置为驱动器的根目录 `HKLM:` 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-118">This command sets the current location to the root of the `HKLM:` drive.</span></span>

### <span data-ttu-id="9dc9a-119">示例2：设置当前位置并显示该位置</span><span class="sxs-lookup"><span data-stu-id="9dc9a-119">Example 2: Set the current location and display that location</span></span>

```
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```Output
Path
----
Env:\

PS Env:\>
```

<span data-ttu-id="9dc9a-120">此命令将当前位置设置为驱动器的根目录 `Env:` 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-120">This command sets the current location to the root of the `Env:` drive.</span></span> <span data-ttu-id="9dc9a-121">它使用 **PassThru** 参数来指示 PowerShell 返回表示位置的 **PathInfo** 对象 `Env:\` 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-121">It uses the **PassThru** parameter to direct PowerShell to return a **PathInfo** object that represents the `Env:\` location.</span></span>

### <span data-ttu-id="9dc9a-122">示例3：将位置设置为 C：驱动器中的当前位置</span><span class="sxs-lookup"><span data-stu-id="9dc9a-122">Example 3: Set location to the current location in the C: drive</span></span>

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

<span data-ttu-id="9dc9a-123">第一个命令将位置设置为 `HKLM:` 注册表提供程序中驱动器的根目录。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-123">The first command sets the location to the root of the `HKLM:` drive in the Registry provider.</span></span>
<span data-ttu-id="9dc9a-124">第二个命令将位置设置为 `C:` FileSystem 提供程序中驱动器的当前位置。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-124">The second command sets the location to the current location of the `C:` drive in the FileSystem provider.</span></span>
<span data-ttu-id="9dc9a-125">如果以格式指定驱动器名称时 `<DriveName>:` (没有反斜杠) ，则该 cmdlet 会将该位置设置为 new-psdrive 中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-125">When the drive name is specified in the form `<DriveName>:` (without backslash), the cmdlet sets the location to the current location in the PSDrive.</span></span>
<span data-ttu-id="9dc9a-126">获取 New-psdrive use 命令中的当前位置 `Get-Location -PSDrive <DriveName>` 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-126">To get the current location in the PSDrive use `Get-Location -PSDrive <DriveName>` command.</span></span>

### <span data-ttu-id="9dc9a-127">示例4：将当前位置设置为命名堆栈</span><span class="sxs-lookup"><span data-stu-id="9dc9a-127">Example 4: Set the current location to a named stack</span></span>

```
PS C:\> Push-Location -Path 'C:\Program Files\PowerShell\' -StackName "Paths"
PS C:\Program Files\PowerShell\> Set-Location -StackName "Paths"
PS C:\Program Files\PowerShell\> Get-Location -Stack
```

```Output
Path
----
C:\
```

<span data-ttu-id="9dc9a-128">第一个命令将当前位置添加到路径堆栈。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-128">The first command adds the current location to the Paths stack.</span></span>
<span data-ttu-id="9dc9a-129">第二个命令使路径位置堆栈成为当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-129">The second command makes the Paths location stack the current location stack.</span></span>
<span data-ttu-id="9dc9a-130">第三个命令显示当前位置堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-130">The third command displays the locations in the current location stack.</span></span>

<span data-ttu-id="9dc9a-131">`*-Location`除非在命令中指定了其他位置堆栈，否则 cmdlet 将使用当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-131">The `*-Location` cmdlets use the current location stack unless a different location stack is specified in the command.</span></span> <span data-ttu-id="9dc9a-132">有关位置堆栈的信息，请参阅 [注释](#notes)。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-132">For information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="9dc9a-133">示例5：使用或导航位置历史记录 `+``-`</span><span class="sxs-lookup"><span data-stu-id="9dc9a-133">Example 5: Navigate location history using `+` or `-`</span></span>

```
PS C:\> Set-Location -Path $env:SystemRoot
PS C:\Windows> Set-Location -Path Cert:\
PS Cert:\> Set-Location -Path HKLM:\
PS HKLM:\>

# Navigate back through the history using "-"
PS HKLM:\> Set-Location -Path -
PS Cert:\> Set-Location -Path -
PS C:\Windows>

# Navigate using the Set-Location alias "cd" and the implicit positional Path parameter
PS C:\Windows> cd -
PS C:\> cd +
PS C:\Windows> cd +
PS Cert:\>
```

<span data-ttu-id="9dc9a-134">使用别名， `cd -` 或 `cd +` 在终端中导航到位置历史记录是一种简单的方法。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-134">Using the alias, `cd -` or `cd +` is an easy way to navigate through your location history while in your terminal.</span></span> <span data-ttu-id="9dc9a-135">有关导航的详细信息 `-` / `+` ，请参阅 **Path** 参数。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-135">For more information on navigating with `-`/`+`, see the **Path** parameter.</span></span>

## <span data-ttu-id="9dc9a-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9dc9a-136">PARAMETERS</span></span>

### <span data-ttu-id="9dc9a-137">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9dc9a-137">-LiteralPath</span></span>

<span data-ttu-id="9dc9a-138">指定位置的路径。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-138">Specifies a path of the location.</span></span> <span data-ttu-id="9dc9a-139">**LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-139">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="9dc9a-140">不会将任何字符解释为通配字符。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-140">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="9dc9a-141">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-141">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9dc9a-142">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-142">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9dc9a-143">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9dc9a-143">-PassThru</span></span>

<span data-ttu-id="9dc9a-144">返回表示位置的 **PathInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-144">Returns a **PathInfo** object that represents the location.</span></span> <span data-ttu-id="9dc9a-145">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-145">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="9dc9a-146">-Path</span><span class="sxs-lookup"><span data-stu-id="9dc9a-146">-Path</span></span>

<span data-ttu-id="9dc9a-147">指定新工作位置的路径。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-147">Specify the path of a new working location.</span></span> <span data-ttu-id="9dc9a-148">如果未提供路径，则 `Set-Location` 默认为当前用户的主目录。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-148">If no path is provided, `Set-Location` defaults to the current user's home directory.</span></span> <span data-ttu-id="9dc9a-149">使用通配符时，该 cmdlet 将选择与通配符模式匹配的第一个路径。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-149">When wildcards are used, the cmdlet chooses the first path that matches the wildcard pattern.</span></span>

<span data-ttu-id="9dc9a-150">PowerShell 会保留你已设置的最近20个位置的历史记录。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-150">PowerShell keeps a history of the last 20 locations you have set.</span></span> <span data-ttu-id="9dc9a-151">如果 **Path** 参数值为 `-` 字符，则新的工作位置将是历史记录中的上一个工作位置 (如果它存在) 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-151">If the **Path** parameter value is the `-` character, then the new working location will be the previous working location in history (if it exists).</span></span> <span data-ttu-id="9dc9a-152">同样，如果值为 `+` 字符，则新的工作位置将是历史记录中的下一个工作位置 (如果它存在) 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-152">Similarly, if the value is the `+` character, then the new working location will be the next working location in history (if it exists).</span></span> <span data-ttu-id="9dc9a-153">这类似于使用 `Pop-Location` 和， `Push-Location` 只不过历史记录是一个列表，而不是一个堆栈，并且是隐式跟踪的，而不是手动控制的。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-153">This is similar to using `Pop-Location` and `Push-Location` except that the history is a list, not a stack, and is implicitly tracked, not manually controlled.</span></span> <span data-ttu-id="9dc9a-154">目前没有办法查看历史记录列表。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-154">Currently, there is no way to view the history list.</span></span>

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

### <span data-ttu-id="9dc9a-155">-StackName</span><span class="sxs-lookup"><span data-stu-id="9dc9a-155">-StackName</span></span>

<span data-ttu-id="9dc9a-156">指定此 cmdlet 生成当前位置堆栈的现有位置堆栈名称。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-156">Specifies the existing location stack name that this cmdlet makes the current location stack.</span></span> <span data-ttu-id="9dc9a-157">输入位置堆栈名称。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-157">Enter a location stack name.</span></span> <span data-ttu-id="9dc9a-158">若要指明未命名的默认位置堆栈，请键入 `$null` 或 () 的空字符串 `""` 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-158">To indicate the unnamed default location stack, type `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="9dc9a-159">`*-Location`Cmdlet 将作用于当前堆栈，除非使用 **StackName** 参数指定其他堆栈。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-159">The `*-Location` cmdlets act on the current stack unless you use the **StackName** parameter to specify a different stack.</span></span> <span data-ttu-id="9dc9a-160">有关位置堆栈的详细信息，请参阅 [注释](#notes)。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-160">For more information about location stacks, see the [Notes](#notes).</span></span>

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

### <span data-ttu-id="9dc9a-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9dc9a-161">CommonParameters</span></span>

<span data-ttu-id="9dc9a-162">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9dc9a-163">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9dc9a-164">输入</span><span class="sxs-lookup"><span data-stu-id="9dc9a-164">INPUTS</span></span>

### <span data-ttu-id="9dc9a-165">System.String</span><span class="sxs-lookup"><span data-stu-id="9dc9a-165">System.String</span></span>

<span data-ttu-id="9dc9a-166">可以通过管道将包含路径（但不是文本路径）的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-166">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="9dc9a-167">输出</span><span class="sxs-lookup"><span data-stu-id="9dc9a-167">OUTPUTS</span></span>

### <span data-ttu-id="9dc9a-168">无、System.Management.Automation.PathInfo、System.Management.Automation.PathInfoStack</span><span class="sxs-lookup"><span data-stu-id="9dc9a-168">None, System.Management.Automation.PathInfo, System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="9dc9a-169">除非指定 **PassThru** 参数，否则此 cmdlet 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-169">This cmdlet does not generate any output unless you specify the **PassThru** parameter.</span></span> <span data-ttu-id="9dc9a-170">结合使用 **PassThru** 和 **Path** 或 **LiteralPath** 将生成一个表示新位置的 **PathInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-170">Using **PassThru** with **Path** or **LiteralPath** generates a **PathInfo** object that represents the new location.</span></span> <span data-ttu-id="9dc9a-171">结合使用 **PassThru** 和 **StackName** 将生成表示新堆栈上下文的 **system.management.automation.pathinfostack** 对象。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-171">Using **PassThru** with **StackName** generates a **PathInfoStack** object representing the new stack context.</span></span>

## <span data-ttu-id="9dc9a-172">注释</span><span class="sxs-lookup"><span data-stu-id="9dc9a-172">NOTES</span></span>

<span data-ttu-id="9dc9a-173">PowerShell 支持每个进程运行多个运行空间。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-173">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="9dc9a-174">每个运行空间都有其自己的 _当前目录_ 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-174">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="9dc9a-175">这与不相同 `[System.Environment]::CurrentDirectory` 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-175">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="9dc9a-176">调用 .NET Api 或运行本机应用程序时，如果不提供显式目录路径，则可能会出现这种问题。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-176">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="9dc9a-177">即使位置 cmdlet 设置了进程范围的当前目录，也不能依赖于该目录，因为另一个运行空间可能会随时更改该目录。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-177">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="9dc9a-178">应使用 location cmdlet，以使用当前特定于当前运行空间的工作目录执行基于路径的操作。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-178">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="9dc9a-179">`Set-Location`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-179">The `Set-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="9dc9a-180">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-180">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="9dc9a-181">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-181">For more information, see [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span></span>

<span data-ttu-id="9dc9a-182">堆栈是一种后进先出的列表，在其中只能访问最后添加的项。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-182">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="9dc9a-183">采用要使用项的顺序将这些项添加到堆栈，然后采用相反顺序检索这些项以供使用。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-183">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="9dc9a-184">PowerShell 使你能够在位置堆栈中存储提供程序位置。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-184">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="9dc9a-185">PowerShell 创建一个未命名的默认位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-185">PowerShell creates an unnamed default location stack.</span></span> <span data-ttu-id="9dc9a-186">可以创建多个命名的位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-186">You can create multiple named location stacks.</span></span> <span data-ttu-id="9dc9a-187">如果未指定堆栈名称，PowerShell 将使用当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-187">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="9dc9a-188">默认情况下，未命名的默认位置为当前位置堆栈，但你可以使用 `Set-Location` cmdlet 来更改当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-188">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="9dc9a-189">若要管理位置堆栈，请使用 `*-Location` cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9dc9a-189">To manage location stacks, use the `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="9dc9a-190">若要将位置添加到位置堆栈，请使用 `Push-Location` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-190">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="9dc9a-191">若要从位置堆栈获取位置，请使用 `Pop-Location` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-191">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="9dc9a-192">若要显示当前位置堆栈中的位置，请使用 cmdlet 的 **stack** 参数 `Get-Location` 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-192">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="9dc9a-193">若要显示命名位置堆栈中的位置，请使用的 **StackName** 参数 `Get-Location` 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-193">To display the locations in a named location stack, use the **StackName** parameter of `Get-Location`.</span></span>

- <span data-ttu-id="9dc9a-194">若要创建新的位置堆栈，请使用的 **StackName** 参数 `Push-Location` 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-194">To create a new location stack, use the **StackName** parameter of `Push-Location`.</span></span> <span data-ttu-id="9dc9a-195">如果指定不存在的堆栈， `Push-Location` 将创建堆栈。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-195">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="9dc9a-196">若要使某个位置堆栈成为当前位置堆栈，请使用的 **StackName** 参数 `Set-Location` 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-196">To make a location stack the current location stack, use the **StackName** parameter of `Set-Location`.</span></span>

<span data-ttu-id="9dc9a-197">未命名的默认位置堆栈仅在其是当前位置堆栈时处于完全可访问状态。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-197">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="9dc9a-198">如果使命名位置堆栈成为当前位置堆栈，则不能再使用 `Push-Location` 或 `Pop-Location` cmdlet 来添加或获取默认堆栈中的项，也不能使用 `Get-Location` cmdlet 来显示未命名堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-198">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="9dc9a-199">若要使未命名堆栈成为当前堆栈，请使用 cmdlet 的 **StackName** 参数，其 `Set-Location` 值为 `$null` 或空字符串 (`""`) 。</span><span class="sxs-lookup"><span data-stu-id="9dc9a-199">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="9dc9a-200">相关链接</span><span class="sxs-lookup"><span data-stu-id="9dc9a-200">RELATED LINKS</span></span>

[<span data-ttu-id="9dc9a-201">Get-Location</span><span class="sxs-lookup"><span data-stu-id="9dc9a-201">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="9dc9a-202">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="9dc9a-202">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="9dc9a-203">Push-Location</span><span class="sxs-lookup"><span data-stu-id="9dc9a-203">Push-Location</span></span>](Push-Location.md)
