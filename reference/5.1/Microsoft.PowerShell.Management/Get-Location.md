---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Location
ms.openlocfilehash: 647424d8148cad8830235abc7b238b79b552c4fb
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "93199322"
---
# <span data-ttu-id="3e247-103">Get-Location</span><span class="sxs-lookup"><span data-stu-id="3e247-103">Get-Location</span></span>

## <span data-ttu-id="3e247-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3e247-104">SYNOPSIS</span></span>
<span data-ttu-id="3e247-105">获取有关当前工作位置或某个位置堆栈的信息。</span><span class="sxs-lookup"><span data-stu-id="3e247-105">Gets information about the current working location or a location stack.</span></span>

## <span data-ttu-id="3e247-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3e247-106">SYNTAX</span></span>

### <span data-ttu-id="3e247-107">Location（默认值）</span><span class="sxs-lookup"><span data-stu-id="3e247-107">Location (Default)</span></span>

```
Get-Location [-PSProvider <String[]>] [-PSDrive <String[]>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="3e247-108">堆栈</span><span class="sxs-lookup"><span data-stu-id="3e247-108">Stack</span></span>

```
Get-Location [-Stack] [-StackName <String[]>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="3e247-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e247-109">DESCRIPTION</span></span>

<span data-ttu-id="3e247-110">该 `Get-Location` cmdlet 将获取表示当前目录的对象，这与打印工作目录 (pwd) 命令非常类似。</span><span class="sxs-lookup"><span data-stu-id="3e247-110">The `Get-Location` cmdlet gets an object that represents the current directory, much like the print working directory (pwd) command.</span></span>

<span data-ttu-id="3e247-111">当你在 PowerShell 驱动器间移动时，PowerShell 会保留你在每个驱动器中的位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-111">When you move between PowerShell drives, PowerShell retains your location in each drive.</span></span> <span data-ttu-id="3e247-112">可以使用此 cmdlet 查找每个驱动器中的位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-112">You can use this cmdlet to find your location in each drive.</span></span>

<span data-ttu-id="3e247-113">可以使用此 cmdlet 在运行时获取当前目录，并将其用于函数和脚本中，如在 PowerShell 提示符下显示当前目录的函数中。</span><span class="sxs-lookup"><span data-stu-id="3e247-113">You can use this cmdlet to get the current directory at run time and use it in functions and scripts, such as in a function that displays the current directory in the PowerShell prompt.</span></span>

<span data-ttu-id="3e247-114">你还可以使用此 cmdlet 显示位置堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-114">You can also use this cmdlet to display the locations in a location stack.</span></span> <span data-ttu-id="3e247-115">有关详细信息，请参阅 **Stack** 和 **StackName** 参数的说明和说明。</span><span class="sxs-lookup"><span data-stu-id="3e247-115">For more information, see the Notes and the descriptions of the **Stack** and **StackName** parameters.</span></span>

## <span data-ttu-id="3e247-116">示例</span><span class="sxs-lookup"><span data-stu-id="3e247-116">EXAMPLES</span></span>

### <span data-ttu-id="3e247-117">示例1：显示当前驱动器位置</span><span class="sxs-lookup"><span data-stu-id="3e247-117">Example 1: Display your current drive location</span></span>

<span data-ttu-id="3e247-118">此命令显示你在当前 PowerShell 驱动器中的位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-118">This command displays your location in the current PowerShell drive.</span></span>

```powershell
PS C:\Windows> Get-Location
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="3e247-119">例如，如果位于驱动器的目录中 `Windows` `C:` ，则会显示该目录的路径。</span><span class="sxs-lookup"><span data-stu-id="3e247-119">For instance, if you are in the `Windows` directory of the `C:` drive, it displays the path to that directory.</span></span>

### <span data-ttu-id="3e247-120">示例2：显示不同驱动器的当前位置</span><span class="sxs-lookup"><span data-stu-id="3e247-120">Example 2: Display your current location for different drives</span></span>

<span data-ttu-id="3e247-121">此示例演示 `Get-Location` 如何使用来显示你在不同 PowerShell 驱动器中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-121">This example demonstrates the use of `Get-Location` to display your current location in different PowerShell drives.</span></span> <span data-ttu-id="3e247-122">`Set-Location` 用于将位置更改为不同 PSDrives 上的多个不同路径。</span><span class="sxs-lookup"><span data-stu-id="3e247-122">`Set-Location` is used to change the location to several different paths on different PSDrives.</span></span>

```powershell
PS C:\> Set-Location C:\Windows
PS C:\Windows> Set-Location HKLM:\Software\Microsoft
PS HKLM:\Software\Microsoft> Set-Location "HKCU:\Control Panel\Input Method"
PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive C

Path
----
C:\Windows

PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive HKLM

Path
----
HKLM:\Software\Microsoft

PS HKCU:\Control Panel\Input Method> Set-Location C:
PS C:\Windows> Get-Location -PSProvider Registry

Path
----
HKCU:\Control Panel\Input Method
```

### <span data-ttu-id="3e247-123">示例3：使用堆栈获取位置</span><span class="sxs-lookup"><span data-stu-id="3e247-123">Example 3: Get locations using stacks</span></span>

<span data-ttu-id="3e247-124">此示例演示如何使用的 **Stack** 和 **StackName** 参数 `Get-Location` 来列出当前位置堆栈和备用位置堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-124">This example shows how to use the **Stack** and **StackName** parameters of `Get-Location` to list the locations in the current location stack and alternate location stacks.</span></span>

<span data-ttu-id="3e247-125">`Push-Location`Cmdlet 用于更改为三个不同的位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-125">The `Push-Location` cmdlet is used to change into three different locations.</span></span> <span data-ttu-id="3e247-126">第三个推送使用不同的堆栈名称。</span><span class="sxs-lookup"><span data-stu-id="3e247-126">The third push uses a different stack name.</span></span> <span data-ttu-id="3e247-127">的 **Stack** 参数 `Get-Location` 显示默认堆栈的内容。</span><span class="sxs-lookup"><span data-stu-id="3e247-127">The **Stack** parameter of `Get-Location` displays the contents of the default stack.</span></span> <span data-ttu-id="3e247-128">的 **StackName** 参数 `Get-Location` 显示名为的堆栈的内容 `Stack2` 。</span><span class="sxs-lookup"><span data-stu-id="3e247-128">The **StackName** parameter of `Get-Location` displays the contents of the stack named `Stack2`.</span></span>

```powershell
PS C:\> Push-Location C:\Windows
PS C:\Windows>Push-Location System32
PS C:\Windows\System32>Push-Location WindowsPowerShell -StackName Stack2
C:\Windows\System32\WindowsPowerShell>Get-Location -Stack

Path
----
C:\Windows
C:\

C:\Windows\System32\WindowsPowerShell>Get-Location -StackName Stack2

Path
----
C:\Windows\System32
```

### <span data-ttu-id="3e247-129">示例4：自定义 PowerShell 提示符</span><span class="sxs-lookup"><span data-stu-id="3e247-129">Example 4: Customize the PowerShell prompt</span></span>

<span data-ttu-id="3e247-130">此示例演示如何自定义 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="3e247-130">This example shows how to customize the PowerShell prompt.</span></span>

```powershell
PS C:\>
function prompt { 'PowerShell: ' + (Get-Location) + '> '}
PowerShell: C:\>
```

<span data-ttu-id="3e247-131">定义提示符的函数包含一个 `Get-Location` 命令，该命令在控制台中出现提示时运行。</span><span class="sxs-lookup"><span data-stu-id="3e247-131">The function that defines the prompt includes a `Get-Location` command, which is run whenever the prompt appears in the console.</span></span>

<span data-ttu-id="3e247-132">默认 PowerShell 提示符的格式由一个名为的特殊函数来定义 `prompt` 。</span><span class="sxs-lookup"><span data-stu-id="3e247-132">The format of the default PowerShell prompt is defined by a special function named `prompt`.</span></span> <span data-ttu-id="3e247-133">可以通过创建一个名为的新函数来更改控制台中的提示 `prompt` 。</span><span class="sxs-lookup"><span data-stu-id="3e247-133">You can change the prompt in your console by creating a new function named `prompt`.</span></span>

<span data-ttu-id="3e247-134">若要查看当前的 prompt 函数，请键入以下命令： `Get-Content Function:\prompt`</span><span class="sxs-lookup"><span data-stu-id="3e247-134">To see the current prompt function, type the following command: `Get-Content Function:\prompt`</span></span>

## <span data-ttu-id="3e247-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3e247-135">PARAMETERS</span></span>

### <span data-ttu-id="3e247-136">-PSDrive</span><span class="sxs-lookup"><span data-stu-id="3e247-136">-PSDrive</span></span>

<span data-ttu-id="3e247-137">获取指定 PowerShell 驱动器中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-137">Gets the current location in the specified PowerShell drive.</span></span>

<span data-ttu-id="3e247-138">例如，如果你位于 `Cert:` 驱动器中，则可以使用此参数来查找你在驱动器中的当前位置 `C:` 。</span><span class="sxs-lookup"><span data-stu-id="3e247-138">For instance, if you are in the `Cert:` drive, you can use this parameter to find your current location in the `C:` drive.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3e247-139">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="3e247-139">-PSProvider</span></span>

<span data-ttu-id="3e247-140">获取指定 PowerShell 提供程序支持的驱动器中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-140">Gets the current location in the drive supported by the specified PowerShell provider.</span></span>
<span data-ttu-id="3e247-141">如果指定的提供程序支持多个驱动器，则此 cmdlet 将返回最近访问过的驱动器上的位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-141">If the specified provider supports more than one drive, this cmdlet returns the location on the most recently accessed drive.</span></span>

<span data-ttu-id="3e247-142">例如，如果你位于 `C:` 驱动器中，则可以使用此参数来查找 PowerShell **注册表** 提供程序的驱动器中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-142">For example, if you are in the `C:` drive, you can use this parameter to find your current location in the drives of the PowerShell **Registry** provider.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3e247-143">-Stack</span><span class="sxs-lookup"><span data-stu-id="3e247-143">-Stack</span></span>

<span data-ttu-id="3e247-144">指示此 cmdlet 显示添加到当前位置堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-144">Indicates that this cmdlet displays the locations added to the current location stack.</span></span> <span data-ttu-id="3e247-145">您可以使用 cmdlet 将位置添加到堆栈 `Push-Location` 中。</span><span class="sxs-lookup"><span data-stu-id="3e247-145">You can add locations to stacks by using the `Push-Location` cmdlet.</span></span>

<span data-ttu-id="3e247-146">若要显示其他位置堆栈中的位置，请使用 **StackName** 参数。</span><span class="sxs-lookup"><span data-stu-id="3e247-146">To display the locations in a different location stack, use the **StackName** parameter.</span></span> <span data-ttu-id="3e247-147">有关位置堆栈的信息，请参阅 [注释](#notes)。</span><span class="sxs-lookup"><span data-stu-id="3e247-147">For information about location stacks, see the [Notes](#notes).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3e247-148">-StackName</span><span class="sxs-lookup"><span data-stu-id="3e247-148">-StackName</span></span>

<span data-ttu-id="3e247-149">指定作为字符串数组，即命名的位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="3e247-149">Specifies, as a string array, the named location stacks.</span></span> <span data-ttu-id="3e247-150">输入一个或多个位置堆栈名称。</span><span class="sxs-lookup"><span data-stu-id="3e247-150">Enter one or more location stack names.</span></span>

<span data-ttu-id="3e247-151">若要显示当前位置堆栈中的位置，请使用 **stack** 参数。</span><span class="sxs-lookup"><span data-stu-id="3e247-151">To display the locations in the current location stack, use the **Stack** parameter.</span></span> <span data-ttu-id="3e247-152">若要使某个位置堆栈成为当前位置堆栈，请使用 `Set-Location` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3e247-152">To make a location stack the current location stack, use the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="3e247-153">此 cmdlet 无法显示未命名的默认堆栈中的位置，除非该堆栈为当前堆栈。</span><span class="sxs-lookup"><span data-stu-id="3e247-153">This cmdlet cannot display the locations in the unnamed default stack unless it is the current stack.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3e247-154">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="3e247-154">-UseTransaction</span></span>
<span data-ttu-id="3e247-155">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="3e247-155">Includes the command in the active transaction.</span></span>
<span data-ttu-id="3e247-156">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="3e247-156">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="3e247-157">有关详细信息，请参阅 about_transactions。</span><span class="sxs-lookup"><span data-stu-id="3e247-157">For more information, see about_transactions.</span></span>

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

### <span data-ttu-id="3e247-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3e247-158">CommonParameters</span></span>

<span data-ttu-id="3e247-159">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="3e247-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3e247-160">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="3e247-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3e247-161">输入</span><span class="sxs-lookup"><span data-stu-id="3e247-161">INPUTS</span></span>

### <span data-ttu-id="3e247-162">无</span><span class="sxs-lookup"><span data-stu-id="3e247-162">None</span></span>

<span data-ttu-id="3e247-163">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3e247-163">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="3e247-164">输出</span><span class="sxs-lookup"><span data-stu-id="3e247-164">OUTPUTS</span></span>

### <span data-ttu-id="3e247-165">System.Management.Automation.PathInfo 或 System.Management.Automation.PathInfoStack</span><span class="sxs-lookup"><span data-stu-id="3e247-165">System.Management.Automation.PathInfo or System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="3e247-166">如果使用 **Stack** 或 **StackName** 参数，则此 cmdlet 将返回 **system.management.automation.pathinfostack** 对象。</span><span class="sxs-lookup"><span data-stu-id="3e247-166">If you use the **Stack** or **StackName** parameters, this cmdlet returns a **PathInfoStack** object.</span></span> <span data-ttu-id="3e247-167">否则，它将返回 **PathInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="3e247-167">Otherwise, it returns a **PathInfo** object.</span></span>

## <span data-ttu-id="3e247-168">注释</span><span class="sxs-lookup"><span data-stu-id="3e247-168">NOTES</span></span>

<span data-ttu-id="3e247-169">PowerShell 支持每个进程运行多个运行空间。</span><span class="sxs-lookup"><span data-stu-id="3e247-169">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="3e247-170">每个运行空间都有其自己的 _当前目录_ 。</span><span class="sxs-lookup"><span data-stu-id="3e247-170">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="3e247-171">这与不相同 `[System.Environment]::CurrentDirectory` 。</span><span class="sxs-lookup"><span data-stu-id="3e247-171">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="3e247-172">调用 .NET Api 或运行本机应用程序时，如果不提供显式目录路径，则可能会出现这种问题。</span><span class="sxs-lookup"><span data-stu-id="3e247-172">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>
<span data-ttu-id="3e247-173">`Get-Location`Cmdlet 返回当前 PowerShell 运行空间的当前目录。</span><span class="sxs-lookup"><span data-stu-id="3e247-173">The `Get-Location` cmdlet returns the current directory of the current PowerShell runspace.</span></span>

<span data-ttu-id="3e247-174">此 cmdlet 用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="3e247-174">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="3e247-175">若要列出会话中的提供程序，请键入 `Get-PSProvider` 。</span><span class="sxs-lookup"><span data-stu-id="3e247-175">To list the providers in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="3e247-176">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="3e247-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="3e247-177">**PSProvider** 、 **new-psdrive** 、 **Stack** 和 **StackName** 参数的交互方式取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="3e247-177">The ways that the **PSProvider** , **PSDrive** , **Stack** , and **StackName** parameters interact depends on the provider.</span></span> <span data-ttu-id="3e247-178">某些组合将会导致错误，例如，指定驱动器以及没有公开该驱动器的提供程序。</span><span class="sxs-lookup"><span data-stu-id="3e247-178">Some combinations will result in errors, such as specifying both a drive and a provider that does not expose that drive.</span></span> <span data-ttu-id="3e247-179">如果未指定参数，则此 cmdlet 将返回包含当前工作位置的提供程序的 **PathInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="3e247-179">If no parameters are specified, this cmdlet returns the **PathInfo** object for the provider that contains the current working location.</span></span>

<span data-ttu-id="3e247-180">堆栈是后进先出的列表，其中只有最近添加的项是可访问的。</span><span class="sxs-lookup"><span data-stu-id="3e247-180">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span> <span data-ttu-id="3e247-181">采用要使用项的顺序将这些项添加到堆栈，然后采用相反顺序检索这些项以供使用。</span><span class="sxs-lookup"><span data-stu-id="3e247-181">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="3e247-182">PowerShell 使你能够在位置堆栈中存储提供程序位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-182">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="3e247-183">PowerShell 创建一个未命名的默认位置堆栈，你可以创建多个命名的位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="3e247-183">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="3e247-184">如果未指定堆栈名称，PowerShell 将使用当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="3e247-184">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="3e247-185">默认情况下，未命名的默认位置为当前位置堆栈，但你可以使用 `Set-Location` cmdlet 来更改当前位置堆栈。</span><span class="sxs-lookup"><span data-stu-id="3e247-185">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="3e247-186">若要管理位置堆栈，请使用 PowerShell `*-Location` cmdlet，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3e247-186">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows.</span></span>

- <span data-ttu-id="3e247-187">若要将位置添加到位置堆栈，请使用 `Push-Location` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3e247-187">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="3e247-188">若要从位置堆栈获取位置，请使用 `Pop-Location` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3e247-188">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="3e247-189">若要显示当前位置堆栈中的位置，请使用 cmdlet 的 **stack** 参数 `Get-Location` 。</span><span class="sxs-lookup"><span data-stu-id="3e247-189">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="3e247-190">若要显示命名位置堆栈中的位置，请使用 cmdlet 的 **StackName** 参数 `Get-Location` 。</span><span class="sxs-lookup"><span data-stu-id="3e247-190">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="3e247-191">若要创建新的位置堆栈，请使用 cmdlet 的 **StackName** 参数 `Push-Location` 。</span><span class="sxs-lookup"><span data-stu-id="3e247-191">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span>
  <span data-ttu-id="3e247-192">如果指定不存在的堆栈， `Push-Location` 将创建堆栈。</span><span class="sxs-lookup"><span data-stu-id="3e247-192">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="3e247-193">若要使位置堆栈成为当前位置堆栈，请使用 cmdlet 的 **StackName** 参数 `Set-Location` 。</span><span class="sxs-lookup"><span data-stu-id="3e247-193">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="3e247-194">未命名的默认位置堆栈仅在其是当前位置堆栈时处于完全可访问状态。</span><span class="sxs-lookup"><span data-stu-id="3e247-194">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="3e247-195">如果使命名位置堆栈成为当前位置堆栈，则不能再使用 `Push-Location` 或 `Pop-Location` cmdlet 来添加或获取默认堆栈中的项，也不能使用此 cmdlet 显示未命名堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="3e247-195">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use this cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="3e247-196">若要使未命名堆栈成为当前堆栈，请使用 cmdlet 的 **StackName** 参数，其 `Set-Location` 值为 `$null` 或空字符串 (`""`) 。</span><span class="sxs-lookup"><span data-stu-id="3e247-196">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="3e247-197">相关链接</span><span class="sxs-lookup"><span data-stu-id="3e247-197">RELATED LINKS</span></span>

[<span data-ttu-id="3e247-198">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="3e247-198">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="3e247-199">Push-Location</span><span class="sxs-lookup"><span data-stu-id="3e247-199">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="3e247-200">Set-Location</span><span class="sxs-lookup"><span data-stu-id="3e247-200">Set-Location</span></span>](Set-Location.md)
