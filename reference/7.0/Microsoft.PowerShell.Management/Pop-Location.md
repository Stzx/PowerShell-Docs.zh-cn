---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/pop-location?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Pop-Location
ms.openlocfilehash: 4f5dffdc942112672c3a193fd1fef49b3b5c15d6
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "93199223"
---
# <span data-ttu-id="4535e-103">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="4535e-103">Pop-Location</span></span>

## <span data-ttu-id="4535e-104">摘要</span><span class="sxs-lookup"><span data-stu-id="4535e-104">SYNOPSIS</span></span>
<span data-ttu-id="4535e-105">将当前位置更改为最近推入到堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="4535e-105">Changes the current location to the location most recently pushed onto the stack.</span></span>

## <span data-ttu-id="4535e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4535e-106">SYNTAX</span></span>

```
Pop-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="4535e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4535e-107">DESCRIPTION</span></span>

<span data-ttu-id="4535e-108">`Pop-Location`Cmdlet 使用 cmdlet 将当前位置更改为最近推入堆栈的位置 `Push-Location` 。</span><span class="sxs-lookup"><span data-stu-id="4535e-108">The `Pop-Location` cmdlet changes the current location to the location most recently pushed onto the stack by using the `Push-Location` cmdlet.</span></span> <span data-ttu-id="4535e-109">你可以从默认堆栈或使用命令创建的堆栈中弹出位置 `Push-Location` 。</span><span class="sxs-lookup"><span data-stu-id="4535e-109">You can pop a location from the default stack or from a stack that you create by using a `Push-Location` command.</span></span>

## <span data-ttu-id="4535e-110">示例</span><span class="sxs-lookup"><span data-stu-id="4535e-110">EXAMPLES</span></span>

### <span data-ttu-id="4535e-111">示例 1：更改为最近位置</span><span class="sxs-lookup"><span data-stu-id="4535e-111">Example 1: Change to most recent location</span></span>

```
PS C:\> Pop-Location
```

<span data-ttu-id="4535e-112">此命令将你的位置更改为最近添加到当前堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="4535e-112">This command changes your location to the location most recently added to the current stack.</span></span>

### <span data-ttu-id="4535e-113">示例 2：更改为命名堆栈中的最近位置</span><span class="sxs-lookup"><span data-stu-id="4535e-113">Example 2: Change to most recent location in a named stack</span></span>

```
PS C:\> Pop-Location -StackName "Stack2"
```

<span data-ttu-id="4535e-114">此命令将你的位置更改为最近添加到 Stack2 位置堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="4535e-114">This command changes your location to the location most recently added to the Stack2 location stack.</span></span>

<span data-ttu-id="4535e-115">有关位置堆栈的详细信息，请参阅 [注释](#notes)。</span><span class="sxs-lookup"><span data-stu-id="4535e-115">For more information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="4535e-116">示例 3：在不同提供程序的位置之间移动</span><span class="sxs-lookup"><span data-stu-id="4535e-116">Example 3: Move between locations for different providers</span></span>

```
PS C:\> pushd HKLM:\Software\Microsoft\PowerShell
PS HKLM:\Software\Microsoft\PowerShell> pushd Cert:\LocalMachine\TrustedPublisher
PS cert:\LocalMachine\TrustedPublisher> popd
PS HKLM:\Software\Microsoft\PowerShell> popd
PS C:\>
```

<span data-ttu-id="4535e-117">这些命令使用 `Push-Location` 和 `Pop-Location` cmdlet 在不同 PowerShell 提供程序支持的位置之间移动。</span><span class="sxs-lookup"><span data-stu-id="4535e-117">These commands use the `Push-Location` and `Pop-Location` cmdlets to move between locations supported by different PowerShell providers.</span></span> <span data-ttu-id="4535e-118">命令使用的 `pushd` 别名 `Push-Location` 和的 `popd` 别名 `Pop-Location` 。</span><span class="sxs-lookup"><span data-stu-id="4535e-118">The commands use the `pushd` alias for `Push-Location` and the `popd` alias for `Pop-Location`.</span></span>

<span data-ttu-id="4535e-119">第一个命令将当前文件系统位置推送到堆栈上，并移到 PowerShell 注册表提供程序支持的 HKLM 驱动器。</span><span class="sxs-lookup"><span data-stu-id="4535e-119">The first command pushes the current file system location onto the stack and moves to the HKLM drive supported by the PowerShell Registry provider.</span></span>

<span data-ttu-id="4535e-120">第二个命令将注册表位置推送到堆栈上，并移到 PowerShell 证书提供程序支持的位置。</span><span class="sxs-lookup"><span data-stu-id="4535e-120">The second command pushes the registry location onto the stack and moves to a location supported by the PowerShell certificate provider.</span></span>

<span data-ttu-id="4535e-121">最后两个命令将这些位置弹出堆栈。</span><span class="sxs-lookup"><span data-stu-id="4535e-121">The last two commands pop those locations off the stack.</span></span> <span data-ttu-id="4535e-122">第一个 `popd` 命令返回到注册表驱动器，第二个命令返回到文件系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="4535e-122">The first `popd` command returns to the Registry drive, and the second command returns to the file system drive.</span></span>

## <span data-ttu-id="4535e-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4535e-123">PARAMETERS</span></span>

### <span data-ttu-id="4535e-124">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4535e-124">-PassThru</span></span>

<span data-ttu-id="4535e-125">将表示位置的对象传递到管道。</span><span class="sxs-lookup"><span data-stu-id="4535e-125">Passes an object that represents the location to the pipeline.</span></span> <span data-ttu-id="4535e-126">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="4535e-126">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="4535e-127">-StackName</span><span class="sxs-lookup"><span data-stu-id="4535e-127">-StackName</span></span>

<span data-ttu-id="4535e-128">指定弹出位置的位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="4535e-128">Specifies the location stack from which the location is popped.</span></span> <span data-ttu-id="4535e-129">输入位置堆栈名称。</span><span class="sxs-lookup"><span data-stu-id="4535e-129">Enter a location stack name.</span></span>

<span data-ttu-id="4535e-130">如果没有此参数，则 `Pop-Location` 从当前位置堆栈中弹出位置。</span><span class="sxs-lookup"><span data-stu-id="4535e-130">Without this parameter, `Pop-Location` pops a location from the current location stack.</span></span> <span data-ttu-id="4535e-131">默认情况下，当前位置堆栈是 PowerShell 创建的未命名的默认位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="4535e-131">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span> <span data-ttu-id="4535e-132">若要使位置堆栈成为当前位置堆栈，请使用 cmdlet 的 **StackName** 参数 `Set-Location` 。</span><span class="sxs-lookup"><span data-stu-id="4535e-132">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="4535e-133">有关位置堆栈的详细信息，请参阅 [注释](#notes)。</span><span class="sxs-lookup"><span data-stu-id="4535e-133">For more information about location stacks, see the [Notes](#notes).</span></span>

<span data-ttu-id="4535e-134">`Pop-Location` 无法从未命名的默认堆栈中弹出位置，除非该堆栈为当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="4535e-134">`Pop-Location` cannot pop a location from the unnamed default stack unless it is the current location stack.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4535e-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4535e-135">CommonParameters</span></span>

<span data-ttu-id="4535e-136">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="4535e-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4535e-137">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="4535e-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4535e-138">输入</span><span class="sxs-lookup"><span data-stu-id="4535e-138">INPUTS</span></span>

### <span data-ttu-id="4535e-139">无</span><span class="sxs-lookup"><span data-stu-id="4535e-139">None</span></span>

<span data-ttu-id="4535e-140">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4535e-140">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4535e-141">输出</span><span class="sxs-lookup"><span data-stu-id="4535e-141">OUTPUTS</span></span>

### <span data-ttu-id="4535e-142">无，System.Management.Automation.PathInfo</span><span class="sxs-lookup"><span data-stu-id="4535e-142">None, System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="4535e-143">如果指定 **PassThru** 参数，则此 cmdlet 生成表示位置的 **System.Management.Automation.PathInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="4535e-143">This cmdlet generates a **System.Management.Automation.PathInfo** object that represents the location, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="4535e-144">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="4535e-144">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4535e-145">注释</span><span class="sxs-lookup"><span data-stu-id="4535e-145">NOTES</span></span>

<span data-ttu-id="4535e-146">PowerShell 支持每个进程运行多个运行空间。</span><span class="sxs-lookup"><span data-stu-id="4535e-146">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="4535e-147">每个运行空间都有其自己的 _当前目录_ 。</span><span class="sxs-lookup"><span data-stu-id="4535e-147">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="4535e-148">这与不相同 `[System.Environment]::CurrentDirectory` 。</span><span class="sxs-lookup"><span data-stu-id="4535e-148">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="4535e-149">调用 .NET Api 或运行本机应用程序时，如果不提供显式目录路径，则可能会出现这种问题。</span><span class="sxs-lookup"><span data-stu-id="4535e-149">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="4535e-150">即使位置 cmdlet 设置了进程范围的当前目录，也不能依赖于该目录，因为另一个运行空间可能会随时更改该目录。</span><span class="sxs-lookup"><span data-stu-id="4535e-150">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="4535e-151">应使用 location cmdlet，以使用当前特定于当前运行空间的工作目录执行基于路径的操作。</span><span class="sxs-lookup"><span data-stu-id="4535e-151">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="4535e-152">堆栈是一种后进先出的列表，在其中只能访问最后添加的项。</span><span class="sxs-lookup"><span data-stu-id="4535e-152">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="4535e-153">采用要使用项的顺序将这些项添加到堆栈，然后采用相反顺序检索这些项以供使用。</span><span class="sxs-lookup"><span data-stu-id="4535e-153">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="4535e-154">PowerShell 使你能够在位置堆栈中存储提供程序位置。</span><span class="sxs-lookup"><span data-stu-id="4535e-154">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="4535e-155">PowerShell 创建一个未命名的默认位置堆栈，你可以创建多个命名的位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="4535e-155">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="4535e-156">如果未指定堆栈名称，PowerShell 将使用当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="4535e-156">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="4535e-157">默认情况下，未命名的默认位置为当前位置堆栈，但你可以使用 `Set-Location` cmdlet 来更改当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="4535e-157">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="4535e-158">若要管理位置堆栈，请使用 PowerShell `*-Location` cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4535e-158">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="4535e-159">若要将位置添加到位置堆栈，请使用 `Push-Location` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4535e-159">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="4535e-160">若要从位置堆栈获取位置，请使用 `Pop-Location` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4535e-160">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="4535e-161">若要显示当前位置堆栈中的位置，请使用 cmdlet 的 **stack** 参数 `Get-Location` 。</span><span class="sxs-lookup"><span data-stu-id="4535e-161">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="4535e-162">若要显示命名位置堆栈中的位置，请使用 cmdlet 的 **StackName** 参数 `Get-Location` 。</span><span class="sxs-lookup"><span data-stu-id="4535e-162">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="4535e-163">若要创建新的位置堆栈，请使用 cmdlet 的 **StackName** 参数 `Push-Location` 。</span><span class="sxs-lookup"><span data-stu-id="4535e-163">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="4535e-164">如果指定不存在的堆栈， `Push-Location` 将创建堆栈。</span><span class="sxs-lookup"><span data-stu-id="4535e-164">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="4535e-165">若要使位置堆栈成为当前位置堆栈，请使用 cmdlet 的 **StackName** 参数 `Set-Location` 。</span><span class="sxs-lookup"><span data-stu-id="4535e-165">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="4535e-166">未命名的默认位置堆栈仅在其是当前位置堆栈时处于完全可访问状态。</span><span class="sxs-lookup"><span data-stu-id="4535e-166">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="4535e-167">如果使命名位置堆栈成为当前位置堆栈，则不能再使用 `Push-Location` 或 `Pop-Location` cmdlet 来添加或获取默认堆栈中的项，也不能使用 `Get-Location` cmdlet 来显示未命名堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="4535e-167">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="4535e-168">若要使未命名堆栈成为当前堆栈，请使用 cmdlet 的 **StackName** 参数，其 `Set-Location` 值为 `$Null` 或空字符串 (`""`) 。</span><span class="sxs-lookup"><span data-stu-id="4535e-168">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$Null` or an empty string (`""`).</span></span>

<span data-ttu-id="4535e-169">还可以 `Pop-Location` 通过其内置别名来引用 `popd` 。</span><span class="sxs-lookup"><span data-stu-id="4535e-169">You can also refer to `Pop-Location` by its built-in alias, `popd`.</span></span> <span data-ttu-id="4535e-170">有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="4535e-170">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="4535e-171">`Pop-Location` 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="4535e-171">`Pop-Location` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="4535e-172">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="4535e-172">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="4535e-173">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="4535e-173">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="4535e-174">相关链接</span><span class="sxs-lookup"><span data-stu-id="4535e-174">RELATED LINKS</span></span>

[<span data-ttu-id="4535e-175">Get-Location</span><span class="sxs-lookup"><span data-stu-id="4535e-175">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="4535e-176">Push-Location</span><span class="sxs-lookup"><span data-stu-id="4535e-176">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="4535e-177">Set-Location</span><span class="sxs-lookup"><span data-stu-id="4535e-177">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="4535e-178">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="4535e-178">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="4535e-179">about_Providers</span><span class="sxs-lookup"><span data-stu-id="4535e-179">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
