---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PSSession
ms.openlocfilehash: ef5bf676e261e7a4267980a3e87753724ca9bf42
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198173"
---
# <span data-ttu-id="9470d-103">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="9470d-103">Import-PSSession</span></span>

## <span data-ttu-id="9470d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9470d-104">SYNOPSIS</span></span>
<span data-ttu-id="9470d-105">将另一个会话中的命令导入当前会话中。</span><span class="sxs-lookup"><span data-stu-id="9470d-105">Imports commands from another session into the current session.</span></span>

## <span data-ttu-id="9470d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9470d-106">SYNTAX</span></span>

```
Import-PSSession [-Prefix <String>] [-DisableNameChecking] [[-CommandName] <String[]>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-FormatTypeName] <String[]>]
 [-Certificate <X509Certificate2>] [-Session] <PSSession> [<CommonParameters>]
```

## <span data-ttu-id="9470d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9470d-107">DESCRIPTION</span></span>

<span data-ttu-id="9470d-108">**Import-module** cmdlet 从本地或远程计算机上的 PSSession 导入到当前会话中的命令，例如 cmdlet、函数和别名。</span><span class="sxs-lookup"><span data-stu-id="9470d-108">The **Import-PSSession** cmdlet imports commands , such as cmdlets, functions, and aliases, from a PSSession on a local or remote computer into the current session.</span></span>
<span data-ttu-id="9470d-109">可以导入 Get-Command cmdlet 可在 PSSession 中找到的任何命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-109">You can import any command that the Get-Command cmdlet can find in the PSSession.</span></span>

<span data-ttu-id="9470d-110">使用 **import-PSSession** 命令从自定义 shell （如 Microsoft Exchange Server shell）或包含 PowerShell 模块和管理单元或其他不在当前会话中的元素的会话导入命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-110">Use an **Import-PSSession** command to import commands from a customized shell, such as a Microsoft Exchange Server shell, or from a session that includes PowerShell modules and snap-ins or other elements that are not in the current session.</span></span>

<span data-ttu-id="9470d-111">若要导入命令，请先使用 New-PSSession cmdlet 来创建 PSSession。</span><span class="sxs-lookup"><span data-stu-id="9470d-111">To import commands, first use the New-PSSession cmdlet to create a PSSession.</span></span>
<span data-ttu-id="9470d-112">然后，使用 **Import-PSSession** cmdlet 导入命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-112">Then, use the **Import-PSSession** cmdlet to import the commands.</span></span>
<span data-ttu-id="9470d-113">默认情况下， **Import-PSSession** 导入所有命令，与当前会话中的命令具有相同的名称的命令除外。</span><span class="sxs-lookup"><span data-stu-id="9470d-113">By default, **Import-PSSession** imports all commands except for commands that have the same names as commands in the current session.</span></span>
<span data-ttu-id="9470d-114">若要导入所有命令，请使用 *AllowClobber* 参数。</span><span class="sxs-lookup"><span data-stu-id="9470d-114">To import all the commands, use the *AllowClobber* parameter.</span></span>

<span data-ttu-id="9470d-115">你可以使用导入的命令，如同你在会话中使用的任何命令一样。</span><span class="sxs-lookup"><span data-stu-id="9470d-115">You can use imported commands just as you would use any command in the session.</span></span>
<span data-ttu-id="9470d-116">当使用导入的命令时，命令的导入部分将在导出该命令的会话中隐式运行。</span><span class="sxs-lookup"><span data-stu-id="9470d-116">When you use an imported command, the imported part of the command runs implicitly in the session from which it was imported.</span></span>
<span data-ttu-id="9470d-117">但是，远程操作完全由 PowerShell 处理。</span><span class="sxs-lookup"><span data-stu-id="9470d-117">However, the remote operations are handled entirely by PowerShell.</span></span>
<span data-ttu-id="9470d-118">你甚至不需要注意它们，只不过必须使与另一个会话 （PSSession) 的连接保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="9470d-118">You need not even be aware of them, except that you must keep the connection to the other session (PSSession) open.</span></span>
<span data-ttu-id="9470d-119">如果关闭该链接，则导入的命令将不再可用。</span><span class="sxs-lookup"><span data-stu-id="9470d-119">If you close it, the imported commands are no longer available.</span></span>

<span data-ttu-id="9470d-120">由于导入的命令可能比本地命令需要更长的运行时间，因此 **Import-PSSession** 将 *AsJob* 参数添加到每个导入的命令中。</span><span class="sxs-lookup"><span data-stu-id="9470d-120">Because imported commands might take longer to run than local commands, **Import-PSSession** adds an *AsJob* parameter to every imported command.</span></span>
<span data-ttu-id="9470d-121">此参数允许你将命令作为 PowerShell 后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="9470d-121">This parameter allows you to run the command as a PowerShell background job.</span></span>
<span data-ttu-id="9470d-122">有关详细信息，请参阅 about_Jobs。</span><span class="sxs-lookup"><span data-stu-id="9470d-122">For more information, see about_Jobs.</span></span>

<span data-ttu-id="9470d-123">使用 **import-module** 时，PowerShell 会将导入的命令添加到仅存在于会话中的临时模块，并返回表示该模块的对象。</span><span class="sxs-lookup"><span data-stu-id="9470d-123">When you use **Import-PSSession** , PowerShell adds the imported commands to a temporary module that exists only in your session and returns an object that represents the module.</span></span>
<span data-ttu-id="9470d-124">若要创建可在将来的会话中使用的持久性模块，请使用 Export-PSSession cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-124">To create a persistent module that you can use in future sessions, use the Export-PSSession cmdlet.</span></span>

<span data-ttu-id="9470d-125">**Import-module** Cmdlet 使用 PowerShell 的隐式远程处理功能。</span><span class="sxs-lookup"><span data-stu-id="9470d-125">The **Import-PSSession** cmdlet uses the implicit remoting feature of PowerShell.</span></span>
<span data-ttu-id="9470d-126">将命令导入到当前会话中时，它们将在原始会话或原始计算机上的类似会话中隐式运行。</span><span class="sxs-lookup"><span data-stu-id="9470d-126">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

<span data-ttu-id="9470d-127">从 Windows PowerShell 3.0 开始，可以使用 Import-Module cmdlet 将模块从远程会话导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="9470d-127">Beginning in Windows PowerShell 3.0, you can use the Import-Module cmdlet to import modules from a remote session into the current session.</span></span>
<span data-ttu-id="9470d-128">此功能使用隐式远程处理。</span><span class="sxs-lookup"><span data-stu-id="9470d-128">This feature uses implicit remoting.</span></span>
<span data-ttu-id="9470d-129">它相当于使用 **Import-PSSession** 将选定的模块从远程会话导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="9470d-129">It is equivalent to using **Import-PSSession** to import selected modules from a remote session into the current session.</span></span>

## <span data-ttu-id="9470d-130">示例</span><span class="sxs-lookup"><span data-stu-id="9470d-130">EXAMPLES</span></span>

### <span data-ttu-id="9470d-131">示例1：从 PSSession 导入所有命令</span><span class="sxs-lookup"><span data-stu-id="9470d-131">Example 1: Import all commands from a PSSession</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S
```

<span data-ttu-id="9470d-132">此命令将所有命令从 Server01 计算机上的 PSSession 导入到当前会话中，与当前会话中的命令具有相同名称的命令除外。</span><span class="sxs-lookup"><span data-stu-id="9470d-132">This command imports all commands from a PSSession on the Server01 computer into the current session, except for commands that have the same names as commands in the current session.</span></span>

<span data-ttu-id="9470d-133">因为此命令不使用 *CommandName* 参数，所以它还会导入已导入命令所需的所有格式设置数据。</span><span class="sxs-lookup"><span data-stu-id="9470d-133">Because this command does not use the *CommandName* parameter, it also imports all of the formatting data required for the imported commands.</span></span>

### <span data-ttu-id="9470d-134">示例2：导入以特定字符串结尾的命令</span><span class="sxs-lookup"><span data-stu-id="9470d-134">Example 2: Import commands that end with a specific string</span></span>

```
PS C:\> $S = New-PSSession https://ps.testlabs.com/powershell
PS C:\> Import-PSSession -Session $S -CommandName *-test -FormatTypeName *
PS C:\> New-Test -Name Test1
PS C:\> Get-Test test1 | Run-Test
```

<span data-ttu-id="9470d-135">这些命令会将 PSSession 中名称以“-test”结尾的命令导入本地会话，然后显示如何使用导入的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-135">These commands import the commands with names that end in "-test" from a PSSession into the local session, and then they show how to use an imported cmdlet.</span></span>

<span data-ttu-id="9470d-136">第一个命令使用 New-PSSession cmdlet 来创建 PSSession。</span><span class="sxs-lookup"><span data-stu-id="9470d-136">The first command uses the New-PSSession cmdlet to create a PSSession.</span></span>
<span data-ttu-id="9470d-137">它将 PSSession 保存在 $S 的变量中。</span><span class="sxs-lookup"><span data-stu-id="9470d-137">It saves the PSSession in the $S variable.</span></span>

<span data-ttu-id="9470d-138">第二个命令使用 **import-module** cmdlet 将命令从 $S 中的 PSSession 导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="9470d-138">The second command uses the **Import-PSSession** cmdlet to import commands from the PSSession in $S into the current session.</span></span>
<span data-ttu-id="9470d-139">它使用 *CommandName* 参数指定带有名词 Test 的命令，使用 *FormatTypeName* 参数来导入这些命令的格式设置数据。</span><span class="sxs-lookup"><span data-stu-id="9470d-139">It uses the *CommandName* parameter to specify commands with the Test noun and the *FormatTypeName* parameter to import the formatting data for the Test commands.</span></span>

<span data-ttu-id="9470d-140">第三个和第四个命令使用当前会话中导入的命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-140">The third and fourth commands use the imported commands in the current session.</span></span>
<span data-ttu-id="9470d-141">由于导入的命令实际添加到当前会话中，因此你将使用本地语法来运行它们。</span><span class="sxs-lookup"><span data-stu-id="9470d-141">Because imported commands are actually added to the current session, you use the local syntax to run them.</span></span>
<span data-ttu-id="9470d-142">无需使用 Invoke-Command cmdlet 即可运行导入的命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-142">You do not need to use the Invoke-Command cmdlet to run an imported command.</span></span>

### <span data-ttu-id="9470d-143">示例3：从 PSSession 导入 cmdlet</span><span class="sxs-lookup"><span data-stu-id="9470d-143">Example 3: Import cmdlets from a PSSession</span></span>

```
PS C:\> $S1 = New-PSSession -ComputerName s1
PS C:\> $S2 = New-PSSession -ComputerName s2
PS C:\> Import-PSSession -Session s1 -Type cmdlet -Name New-Test, Get-Test -FormatTypeName *
PS C:\> Import-PSSession -Session s2 -Type Cmdlet -Name Set-Test -FormatTypeName *
PS C:\> New-Test Test1 | Set-Test -RunType Full
```

<span data-ttu-id="9470d-144">此示例演示可以像使用本地 cmdlet 一样使用导入的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-144">This example shows that you can use imported cmdlets just as you would use local cmdlets.</span></span>

<span data-ttu-id="9470d-145">这些命令从 Server01 计算机上的 PSSession 中导入 New-Test 和 Get-Test cmdlet，从 Server02 计算机上的 PSSession 中导入 Set-Test cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-145">These commands import the New-Test and Get-Test cmdlets from a PSSession on the Server01 computer and the Set-Test cmdlet from a PSSession on the Server02 computer.</span></span>

<span data-ttu-id="9470d-146">尽管这些 cmdlet 从不同的 PSSession 中导入，但是可以通过管道将来自一个 cmdlet 的对象无误地传递到另一个 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-146">Even though the cmdlets were imported from different PSSessions, you can pipe an object from one cmdlet to another without error.</span></span>

### <span data-ttu-id="9470d-147">示例4：将导入的命令作为后台作业运行</span><span class="sxs-lookup"><span data-stu-id="9470d-147">Example 4: Run an imported command as a background job</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S -CommandName *-test* -FormatTypeName *
PS C:\> $batch = New-Test -Name Batch -AsJob
PS C:\> Receive-Job $batch
```

<span data-ttu-id="9470d-148">此示例演示了如何将导入的命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="9470d-148">This example shows how to run an imported command as a background job.</span></span>

<span data-ttu-id="9470d-149">由于导入的命令可能比本地命令需要更长的运行时间，因此 **Import-PSSession** 将 *AsJob* 参数添加到每个导入的命令中。</span><span class="sxs-lookup"><span data-stu-id="9470d-149">Because imported commands might take longer to run than local commands, **Import-PSSession** adds an *AsJob* parameter to every imported command.</span></span>
<span data-ttu-id="9470d-150">*AsJob* 参数允许你将该命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="9470d-150">The *AsJob* parameter lets you run the command as a background job.</span></span>

<span data-ttu-id="9470d-151">第一个命令在 Server01 计算机上创建 PSSession，并将 PSSession 对象保存在 $S 的变量中。</span><span class="sxs-lookup"><span data-stu-id="9470d-151">The first command creates a PSSession on the Server01 computer and saves the PSSession object in the $S variable.</span></span>

<span data-ttu-id="9470d-152">第二个命令使用 **import-module** 将 $S 中的 PSSession 的测试 cmdlet 导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="9470d-152">The second command uses **Import-PSSession** to import the Test cmdlets from the PSSession in $S into the current session.</span></span>

<span data-ttu-id="9470d-153">第三个命令使用导入的 New-Test cmdlet 的 *AsJob* 参数，将 New-Test 命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="9470d-153">The third command uses the *AsJob* parameter of the imported New-Test cmdlet to run a New-Test command as a background job.</span></span>
<span data-ttu-id="9470d-154">该命令将 New-Test 返回的作业对象保存在 $batch 变量中。</span><span class="sxs-lookup"><span data-stu-id="9470d-154">The command saves the job object that New-Test returns in the $batch variable.</span></span>

<span data-ttu-id="9470d-155">第四个命令使用 Receive-Job cmdlet 获取 $batch 变量中的作业的结果。</span><span class="sxs-lookup"><span data-stu-id="9470d-155">The fourth command uses the Receive-Job cmdlet to get the results of the job in the $batch variable.</span></span>

### <span data-ttu-id="9470d-156">示例5：从 PowerShell 模块导入 cmdlet 和函数</span><span class="sxs-lookup"><span data-stu-id="9470d-156">Example 5: Import cmdlets and functions from a PowerShell module</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Invoke-Command -Session $S {Import-Module TestManagement}
PS C:\> Import-PSSession -Session $S -Module TestManagement
```

<span data-ttu-id="9470d-157">此示例显示了如何将远程计算机上的 PowerShell 模块中的 cmdlet 和函数导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="9470d-157">This example shows how to import the cmdlets and functions from a PowerShell module on a remote computer into the current session.</span></span>

<span data-ttu-id="9470d-158">第一个命令在 Server01 计算机上创建 PSSession，并将其保存在 $S 变量中。</span><span class="sxs-lookup"><span data-stu-id="9470d-158">The first command creates a PSSession on the Server01 computer and saves it in the $S variable.</span></span>

<span data-ttu-id="9470d-159">第二个命令使用 **调用-command** cmdlet 在 $S 中的 PSSession 中运行 Import-Module 命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-159">The second command uses the **Invoke-Command** cmdlet to run an Import-Module command in the PSSession in $S.</span></span>

<span data-ttu-id="9470d-160">通常，该模块将通过 PowerShell 配置文件中的 **import-module** 命令添加到所有会话，但配置文件不会在 pssession 中运行。</span><span class="sxs-lookup"><span data-stu-id="9470d-160">Typically, the module would be added to all sessions by an **Import-Module** command in a PowerShell profile, but profiles are not run in PSSessions.</span></span>

<span data-ttu-id="9470d-161">第三个命令使用 **import-module** 的 *module* 参数将模块中的 cmdlet 和函数导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="9470d-161">The third command uses the *Module*  parameter of **Import-PSSession** to import the cmdlets and functions in the module into the current session.</span></span>

### <span data-ttu-id="9470d-162">示例6：在临时文件中创建模块</span><span class="sxs-lookup"><span data-stu-id="9470d-162">Example 6: Create a module in a temporary file</span></span>

```
PS C:\> Import-PSSession $S -CommandName Get-Date, SearchHelp -FormatTypeName * -AllowClobber

Name              : tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
Path              : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf\tmp_79468106-4e1d-4d90-af97-1154f9317239_
tcw1zunz.ttf.psm1
Description       : Implicit remoting for http://server01.corp.fabrikam.com/wsman
Guid              : 79468106-4e1d-4d90-af97-1154f9317239
Version           : 1.0
ModuleBase        : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
ModuleType        : Script
PrivateData       : {ImplicitRemoting}
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Get-Date, Get-Date], [SearchHelp, SearchHelp]}
ExportedVariables : {}
NestedModules     : {}
```

<span data-ttu-id="9470d-163">此示例显示 **Import-PSSession** 在磁盘上的临时文件中创建一个模块。</span><span class="sxs-lookup"><span data-stu-id="9470d-163">This example shows that **Import-PSSession** creates a module in a temporary file on disk.</span></span>
<span data-ttu-id="9470d-164">它还显示所有命令在导入当前会话之前都已转换为函数。</span><span class="sxs-lookup"><span data-stu-id="9470d-164">It also shows that all commands are converted into functions before they are imported into the current session.</span></span>

<span data-ttu-id="9470d-165">该命令使用 **import-module** cmdlet 将 Get-Date Cmdlet 和 SearchHelp 函数导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="9470d-165">The command uses the **Import-PSSession** cmdlet to import a Get-Date cmdlet and a SearchHelp function into the current session.</span></span>

<span data-ttu-id="9470d-166">**Import-PSSession** cmdlet 将返回表示临时模块的 **PSModuleInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="9470d-166">The **Import-PSSession** cmdlet returns a **PSModuleInfo** object that represents the temporary module.</span></span>
<span data-ttu-id="9470d-167">**Path** 属性的值显示 **Import-PSSession** 在一个临时位置上创建了脚本模块 (.psm1) 文件。</span><span class="sxs-lookup"><span data-stu-id="9470d-167">The value of the **Path** property shows that **Import-PSSession** created a script module (.psm1) file in a temporary location.</span></span>
<span data-ttu-id="9470d-168">**ExportedFunctions** 属性显示 **Get-Date** cmdlet 和 SearchHelp 函数都已作为函数导入。</span><span class="sxs-lookup"><span data-stu-id="9470d-168">The **ExportedFunctions** property shows that the **Get-Date** cmdlet and the SearchHelp function were both imported as functions.</span></span>

### <span data-ttu-id="9470d-169">示例7：运行由导入的命令隐藏的命令</span><span class="sxs-lookup"><span data-stu-id="9470d-169">Example 7: Run a command that is hidden by an imported command</span></span>

```
PS C:\> Import-PSSession $S -CommandName Get-Date -FormatTypeName * -AllowClobber

PS C:\> Get-Command Get-Date -All

CommandType   Name       Definition
-----------   ----       ----------
Function      Get-Date   ...
Cmdlet        Get-Date   Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>]

PS C:\> Get-Date
09074

PS C:\> (Get-Command -Type Cmdlet -Name Get-Date).PSSnapin.Name
Microsoft.PowerShell.Utility

PS C:\> Microsoft.PowerShell.Utility\Get-Date
Sunday, March 15, 2009 2:08:26 PM
```

<span data-ttu-id="9470d-170">此示例演示如何运行导入的命令隐藏的命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-170">This example shows how to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="9470d-171">第一个命令从 $S 变量的 PSSession 中导入 Get-Date cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-171">The first command imports a Get-Date cmdlet from the PSSession in the $S variable.</span></span>
<span data-ttu-id="9470d-172">因为当前会话包括 **Get-Date** cmdlet，所以在该命令中 *AllowClobber* 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="9470d-172">Because the current session includes a **Get-Date** cmdlet, the *AllowClobber* parameter is required in the command.</span></span>

<span data-ttu-id="9470d-173">第二个命令使用 Get-Command cmdlet 的 **all** 参数获取当前会话中的所有 **获取日期** 命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-173">The second command uses the **All** parameter of the Get-Command cmdlet to get all **Get-Date** commands in the current session.</span></span>
<span data-ttu-id="9470d-174">输出显示会话包括原始 **Get-Date** cmdlet 和一个 **Get-Date** 函数。</span><span class="sxs-lookup"><span data-stu-id="9470d-174">The output shows that the session includes the original **Get-Date** cmdlet and a **Get-Date** function.</span></span>
<span data-ttu-id="9470d-175">**获取日期** 函数在 $S 的 PSSession 中运行导入的 **获取日期** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-175">The **Get-Date** function runs the imported **Get-Date** cmdlet in the PSSession in $S.</span></span>

<span data-ttu-id="9470d-176">第三个命令将运行 **Get-Date** 命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-176">The third command runs a **Get-Date** command.</span></span>
<span data-ttu-id="9470d-177">由于函数优先于 cmdlet，因此 PowerShell 会运行导入的 **获取日期** 函数，该函数将返回 Julian 日期。</span><span class="sxs-lookup"><span data-stu-id="9470d-177">Because functions take precedence over cmdlets, PowerShell runs the imported **Get-Date** function, which returns a Julian date.</span></span>

<span data-ttu-id="9470d-178">第四个和第五个命令显示如何使用限定的名称来运行由导入的命令隐藏的命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-178">The fourth and fifth commands show how to use a qualified name to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="9470d-179">第四个命令获取将原始的 **获取日期** cmdlet 添加到当前会话的 PowerShell 管理单元的名称。</span><span class="sxs-lookup"><span data-stu-id="9470d-179">The fourth command gets the name of the PowerShell snap-in that added the original **Get-Date** cmdlet to the current session.</span></span>

<span data-ttu-id="9470d-180">第五个命令使用 **Get-Date** cmdlet 的管理单元限定的名称来运行 **Get-Date** 命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-180">The fifth command uses the snap-in-qualified name of the **Get-Date** cmdlet to run a **Get-Date** command.</span></span>

<span data-ttu-id="9470d-181">有关命令优先级和隐藏的命令的详细信息，请参阅 about_Command_Precedence。</span><span class="sxs-lookup"><span data-stu-id="9470d-181">For more information about command precedence and hidden commands, see about_Command_Precedence.</span></span>

### <span data-ttu-id="9470d-182">示例8：导入名称中包含特定字符串的命令</span><span class="sxs-lookup"><span data-stu-id="9470d-182">Example 8: Import commands that have a specific string in their names</span></span>

```
PS C:\> Import-PSSession -Session $S -CommandName *Item* -AllowClobber
```

<span data-ttu-id="9470d-183">此命令从 $S 中的 PSSession 中导入其名称包含项的命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-183">This command imports commands whose names include Item from the PSSession in $S.</span></span>
<span data-ttu-id="9470d-184">由于该命令包含 *CommandName* 参数而不是 *FormatTypeData* 参数，因此只会导入该命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-184">Because the command includes the *CommandName* parameter but not the *FormatTypeData* parameter, only the command is imported.</span></span>

<span data-ttu-id="9470d-185">当你要在远程计算机上使用 **Import-PSSession** 运行命令，而且已经具有当前会话中的命令的格式设置数据时，请使用此命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-185">Use this command when you are using **Import-PSSession** to run a command on a remote computer and you already have the formatting data for the command in the current session.</span></span>

### <span data-ttu-id="9470d-186">示例9：使用 Module 参数来发现已导入到会话中的命令</span><span class="sxs-lookup"><span data-stu-id="9470d-186">Example 9: Use the Module parameter to discover which commands were imported into the session</span></span>

```
PS C:\> $M = Import-PSSession -Session $S -CommandName *bits* -FormatTypeName *bits*
PS C:\> Get-Command -Module $M
CommandType     Name
-----------     ----
Function        Add-BitsFile
Function        Complete-BitsTransfer
Function        Get-BitsTransfer
Function        Remove-BitsTransfer
Function        Resume-BitsTransfer
Function        Set-BitsTransfer
Function        Start-BitsTransfer
Function        Suspend-BitsTransfer
```

<span data-ttu-id="9470d-187">此命令演示如何使用 **Get-command** 的 *Module* 参数来找出通过 **import-module** 命令导入到会话中的命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-187">This command shows how to use the *Module* parameter of **Get-Command** to find out which commands were imported into the session by an **Import-PSSession** command.</span></span>

<span data-ttu-id="9470d-188">第一个命令使用 **import-module** cmdlet 从 $S 变量的 PSSession 中导入其名称包含 "bits" 的命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-188">The first command uses the **Import-PSSession** cmdlet to import commands whose names include "bits" from the PSSession in the $S variable.</span></span>
<span data-ttu-id="9470d-189">**Import-PSSession** 命令将返回一个临时模块并将该模块保存在 $m 变量中。</span><span class="sxs-lookup"><span data-stu-id="9470d-189">The **Import-PSSession** command returns a temporary module, and the command saves the module in the $m variable.</span></span>

<span data-ttu-id="9470d-190">第二个命令使用 Get-Command cmdlet 获取 $M 变量中的模块导出的命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-190">The second command uses the Get-Command cmdlet to get the commands that are exported by the module in the $M variable.</span></span>

<span data-ttu-id="9470d-191">*Module* 参数采用字符串值，这是为模块名称而设计的。</span><span class="sxs-lookup"><span data-stu-id="9470d-191">The *Module* parameter takes a string value, which is designed for the module name.</span></span>
<span data-ttu-id="9470d-192">但是，当你提交 module 对象时，PowerShell 将对 module 对象使用 **ToString** 方法，该方法将返回模块名称。</span><span class="sxs-lookup"><span data-stu-id="9470d-192">However, when you submit a module object, PowerShell uses the **ToString** method on the module object, which returns the module name.</span></span>

<span data-ttu-id="9470d-193">**Get command** 命令等效于 `Get-Command $M.Name` "。</span><span class="sxs-lookup"><span data-stu-id="9470d-193">The **Get-Command** command is the equivalent of `Get-Command $M.Name`".</span></span>

## <span data-ttu-id="9470d-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9470d-194">PARAMETERS</span></span>

### <span data-ttu-id="9470d-195">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="9470d-195">-AllowClobber</span></span>

<span data-ttu-id="9470d-196">指示此 cmdlet 将导入指定的命令，即使它们与当前会话中的命令具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="9470d-196">Indicates that this cmdlet imports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="9470d-197">如果导入与当前会话中的命令同名的命令，则导入的命令会隐藏或替换原始命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-197">If you import a command with the same name as a command in the current session, the imported command hides or replaces the original commands.</span></span>
<span data-ttu-id="9470d-198">有关详细信息，请参阅 about_Command_Precedence。</span><span class="sxs-lookup"><span data-stu-id="9470d-198">For more information, see about_Command_Precedence.</span></span>

<span data-ttu-id="9470d-199">默认情况下， **Import-PSSession** 不导入与当前会话中的命令具有相同名称的命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-199">By default, **Import-PSSession** does not import commands that have the same name as commands in the current session.</span></span>

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

### <span data-ttu-id="9470d-200">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="9470d-200">-ArgumentList</span></span>

<span data-ttu-id="9470d-201">指定通过使用指定参数 (参数值) 导致的命令数组。</span><span class="sxs-lookup"><span data-stu-id="9470d-201">Specifies an array of commands that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="9470d-202">例如，若要在 $S 的 PSSession 中导入证书中的 Get-Item 命令的变体 (Cert： ) 驱动器，请键入 `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:` 。</span><span class="sxs-lookup"><span data-stu-id="9470d-202">For instance, to import the variant of the Get-Item command in the certificate (Cert:) drive in the PSSession in $S, type `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9470d-203">-Certificate</span><span class="sxs-lookup"><span data-stu-id="9470d-203">-Certificate</span></span>

<span data-ttu-id="9470d-204">指定用于对格式文件 (\*.Format.ps1xml) 或 **Import-PSSession** 创建的临时模块中的脚本模块文件 (.psm1) 进行签名的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="9470d-204">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the temporary module that **Import-PSSession** creates.</span></span>

<span data-ttu-id="9470d-205">输入一个包含证书的变量，或可获取该证书的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="9470d-205">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="9470d-206">若要查找证书，请使用 Get-PfxCertificate cmdlet，或在证书 (Cert： ) 驱动器中使用 Get-ChildItem cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-206">To find a certificate, use the Get-PfxCertificate cmdlet or use the Get-ChildItem cmdlet in the Certificate (Cert:) drive.</span></span>
<span data-ttu-id="9470d-207">如果证书无效或不具有足够的权限，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="9470d-207">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9470d-208">-CommandName</span><span class="sxs-lookup"><span data-stu-id="9470d-208">-CommandName</span></span>

<span data-ttu-id="9470d-209">指定带有指定名称或名称模式的命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-209">Specifies commands with the specified names or name patterns.</span></span>
<span data-ttu-id="9470d-210">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="9470d-210">Wildcards are permitted.</span></span>
<span data-ttu-id="9470d-211">使用 *CommandName* 或其 *别名。*</span><span class="sxs-lookup"><span data-stu-id="9470d-211">Use *CommandName* or its alias, *Name* .</span></span>

<span data-ttu-id="9470d-212">默认情况下， **Import-PSSession** 导入会话中的所有命令，与当前会话中的命令具有相同名称的命令除外。</span><span class="sxs-lookup"><span data-stu-id="9470d-212">By default, **Import-PSSession** imports all commands from the session, except for commands that have the same names as commands in the current session.</span></span>
<span data-ttu-id="9470d-213">这样可以防止导入的命令隐藏或替换会话中的命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-213">This prevents imported commands from hiding or replacing commands in the session.</span></span>
<span data-ttu-id="9470d-214">若要导入所有命令，甚至那些隐藏或替换其他命令的命令，请使用 *AllowClobber* 参数。</span><span class="sxs-lookup"><span data-stu-id="9470d-214">To import all commands, even those that hide or replace other commands, use the *AllowClobber* parameter.</span></span>

<span data-ttu-id="9470d-215">如果使用 *CommandName* 参数，则不导入这些命令的格式设置文件，除非使用 *FormatTypeName* 参数。</span><span class="sxs-lookup"><span data-stu-id="9470d-215">If you use the *CommandName* parameter, the formatting files for the commands are not imported unless you use the *FormatTypeName* parameter.</span></span>
<span data-ttu-id="9470d-216">同样，如果使用 *FormatTypeName* 参数，则不导入任何命令，除非使用 *CommandName* 参数。</span><span class="sxs-lookup"><span data-stu-id="9470d-216">Similarly, if you use the *FormatTypeName* parameter, no commands are imported unless you use the *CommandName* parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9470d-217">-CommandType</span><span class="sxs-lookup"><span data-stu-id="9470d-217">-CommandType</span></span>

<span data-ttu-id="9470d-218">指定命令对象的类型。</span><span class="sxs-lookup"><span data-stu-id="9470d-218">Specifies the type of command objects.</span></span>
<span data-ttu-id="9470d-219">默认值为 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-219">The default value is Cmdlet.</span></span>
<span data-ttu-id="9470d-220">使用 *CommandType* 或其别名 *Type* 。</span><span class="sxs-lookup"><span data-stu-id="9470d-220">Use *CommandType* or its alias, *Type* .</span></span>
<span data-ttu-id="9470d-221">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="9470d-221">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9470d-222">A.</span><span class="sxs-lookup"><span data-stu-id="9470d-222">Alias.</span></span>
<span data-ttu-id="9470d-223">远程会话中的 PowerShell 别名。</span><span class="sxs-lookup"><span data-stu-id="9470d-223">The PowerShell aliases in the remote session.</span></span>
- <span data-ttu-id="9470d-224">全部。</span><span class="sxs-lookup"><span data-stu-id="9470d-224">All.</span></span>
<span data-ttu-id="9470d-225">远程会话中的 cmdlet 和函数。</span><span class="sxs-lookup"><span data-stu-id="9470d-225">The cmdlets and functions in the remote session.</span></span>
- <span data-ttu-id="9470d-226">应用程序。</span><span class="sxs-lookup"><span data-stu-id="9470d-226">Application.</span></span>
<span data-ttu-id="9470d-227">Path 环境变量中列出的路径中的 PowerShell 文件以外的所有文件 (在远程会话中 $env:p a) ，包括 .txt、.exe 和 .dll 文件。</span><span class="sxs-lookup"><span data-stu-id="9470d-227">All the files other than PowerShell files in the paths that are listed in the Path environment variable ($env:path) in the remote session, including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="9470d-228">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9470d-228">Cmdlet.</span></span>
<span data-ttu-id="9470d-229">远程会话中的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-229">The cmdlets in the remote session.</span></span>
<span data-ttu-id="9470d-230">默认值为“Cmdlet”。</span><span class="sxs-lookup"><span data-stu-id="9470d-230">"Cmdlet" is the default.</span></span>
- <span data-ttu-id="9470d-231">ExternalScript.</span><span class="sxs-lookup"><span data-stu-id="9470d-231">ExternalScript.</span></span>
<span data-ttu-id="9470d-232">在远程会话中的 Path 环境变量 ($env:path) 中列出的路径中的 .ps1 文件。</span><span class="sxs-lookup"><span data-stu-id="9470d-232">The .ps1 files in the paths listed in the Path environment variable ($env:path) in the remote session.</span></span>
- <span data-ttu-id="9470d-233">Filter 和 Function。</span><span class="sxs-lookup"><span data-stu-id="9470d-233">Filter and Function.</span></span>
<span data-ttu-id="9470d-234">远程会话中的 PowerShell 函数。</span><span class="sxs-lookup"><span data-stu-id="9470d-234">The PowerShell functions in the remote session.</span></span>
- <span data-ttu-id="9470d-235">脚本。</span><span class="sxs-lookup"><span data-stu-id="9470d-235">Script.</span></span>
<span data-ttu-id="9470d-236">远程会话中的脚本块。</span><span class="sxs-lookup"><span data-stu-id="9470d-236">The script blocks in the remote session.</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9470d-237">-DisableNameChecking</span><span class="sxs-lookup"><span data-stu-id="9470d-237">-DisableNameChecking</span></span>

<span data-ttu-id="9470d-238">指示当你导入的 cmdlet 或函数名称包括未经批准的动词或禁止的字符时，此 cmdlet 将禁止显示警告你的消息。</span><span class="sxs-lookup"><span data-stu-id="9470d-238">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="9470d-239">默认情况下，当导入的模块导出名称中包含未经批准的谓词的 cmdlet 或函数时，PowerShell 将显示以下警告消息：</span><span class="sxs-lookup"><span data-stu-id="9470d-239">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, the PowerShell displays the following warning message:</span></span>

<span data-ttu-id="9470d-240">"警告：某些导入的命令名称包括未经批准的动词，这可能会使它们的发现性更小。</span><span class="sxs-lookup"><span data-stu-id="9470d-240">"WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span>
<span data-ttu-id="9470d-241">请使用 Verbose 参数获取详细信息或者键入 Get-Verb 以查看批准的动词列表。”</span><span class="sxs-lookup"><span data-stu-id="9470d-241">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs."</span></span>

<span data-ttu-id="9470d-242">此消息只是一个警告。</span><span class="sxs-lookup"><span data-stu-id="9470d-242">This message is only a warning.</span></span>
<span data-ttu-id="9470d-243">仍将导入完整的模块，其中包括非一致性的命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-243">The complete module is still imported, including the non-conforming commands.</span></span>
<span data-ttu-id="9470d-244">尽管会向模块用户显示消息，但是模块作者应修复命名问题。</span><span class="sxs-lookup"><span data-stu-id="9470d-244">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

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

### <span data-ttu-id="9470d-245">-FormatTypeName</span><span class="sxs-lookup"><span data-stu-id="9470d-245">-FormatTypeName</span></span>

<span data-ttu-id="9470d-246">指定指定 Microsoft .NET 框架类型的格式设置说明。</span><span class="sxs-lookup"><span data-stu-id="9470d-246">Specifies formatting instructions for the specified Microsoft .NET Framework types.</span></span>
<span data-ttu-id="9470d-247">输入类型名称。</span><span class="sxs-lookup"><span data-stu-id="9470d-247">Enter the type names.</span></span>
<span data-ttu-id="9470d-248">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="9470d-248">Wildcards are permitted.</span></span>

<span data-ttu-id="9470d-249">此参数的值必须是一个类型的名称，该类型由导出这些命令的会话中的 Get-FormatData 命令返回。</span><span class="sxs-lookup"><span data-stu-id="9470d-249">The value of this parameter must be the name of a type that is returned by a Get-FormatData command in the session from which the commands are being imported.</span></span>
<span data-ttu-id="9470d-250">若要获取远程会话中的所有格式数据，请键入 \*。</span><span class="sxs-lookup"><span data-stu-id="9470d-250">To get all of the formatting data in the remote session, type \*.</span></span>

<span data-ttu-id="9470d-251">如果此命令不包括 *CommandName* 或 *FormatTypeName* 参数，则将 **导入远程** 会话中 **update-formatdata** 命令返回的所有 .NET Framework 类型的格式说明。</span><span class="sxs-lookup"><span data-stu-id="9470d-251">If the command does not include either the *CommandName* or *FormatTypeName* parameter, **Import-PSSession** imports formatting instructions for all .NET Framework types returned by a **Get-FormatData** command in the remote session.</span></span>

<span data-ttu-id="9470d-252">如果使用 *FormatTypeName* 参数，则不导入任何命令，除非使用 *CommandName* 参数。</span><span class="sxs-lookup"><span data-stu-id="9470d-252">If you use the *FormatTypeName* parameter, no commands are imported unless you use the *CommandName* parameter.</span></span>

<span data-ttu-id="9470d-253">同样，如果使用 *CommandName* 参数，则不导入这些命令的格式设置文件，除非使用 *FormatTypeName* 参数。</span><span class="sxs-lookup"><span data-stu-id="9470d-253">Similarly, if you use the *CommandName* parameter, the formatting files for the commands are not imported unless you use the *FormatTypeName* parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9470d-254">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="9470d-254">-FullyQualifiedModule</span></span>

<span data-ttu-id="9470d-255">指定名称以 **ModuleSpecification** 对象的形式指定的模块 (在 MSDN) library 中的 [ModuleSpecification 构造函数 (哈希表)](https://msdn.microsoft.com/library/jj136290) 的 "备注" 部分中进行说明。</span><span class="sxs-lookup"><span data-stu-id="9470d-255">Specifies modules with names that are specified in the form of **ModuleSpecification** objects (described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](https://msdn.microsoft.com/library/jj136290) in the MSDN library).</span></span>
<span data-ttu-id="9470d-256">例如， *FullyQualifiedModule* 参数接受以 @ {ModuleName = "ModuleName" 格式指定的模块名称;ModuleVersion = "version_number"} 或 @ {ModuleName = "ModuleName";ModuleVersion = "version_number";Guid = "GUID"}。</span><span class="sxs-lookup"><span data-stu-id="9470d-256">For example, the *FullyQualifiedModule* parameter accepts a module name that is specified in the format @{ModuleName = "modulename"; ModuleVersion = "version_number"} or @{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.</span></span>
<span data-ttu-id="9470d-257">**ModuleName** 和 **ModuleVersion** 是必需的，但 **Guid** 是可选的。</span><span class="sxs-lookup"><span data-stu-id="9470d-257">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="9470d-258">不能在与 *Module* 参数相同的命令中指定 *FullyQualifiedModule* 参数;这两个参数是互斥的。</span><span class="sxs-lookup"><span data-stu-id="9470d-258">You cannot specify the *FullyQualifiedModule* parameter in the same command as a *Module* parameter; the two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9470d-259">-Module</span><span class="sxs-lookup"><span data-stu-id="9470d-259">-Module</span></span>

<span data-ttu-id="9470d-260">指定 PowerShell 管理单元和模块中的命令的数组。</span><span class="sxs-lookup"><span data-stu-id="9470d-260">Specifies and array of commands in the PowerShell snap-ins and modules.</span></span>
<span data-ttu-id="9470d-261">输入管理单元和模块的名称。</span><span class="sxs-lookup"><span data-stu-id="9470d-261">Enter the snap-in and module names.</span></span>
<span data-ttu-id="9470d-262">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="9470d-262">Wildcards are not permitted.</span></span>

<span data-ttu-id="9470d-263">**Import-PSSession** 无法从管理单元导入提供程序。</span><span class="sxs-lookup"><span data-stu-id="9470d-263">**Import-PSSession** cannot import providers from a snap-in.</span></span>

<span data-ttu-id="9470d-264">有关详细信息，请参阅 about_PSSnapins 和 [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md)。</span><span class="sxs-lookup"><span data-stu-id="9470d-264">For more information, see about_PSSnapins and [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9470d-265">-Prefix</span><span class="sxs-lookup"><span data-stu-id="9470d-265">-Prefix</span></span>

<span data-ttu-id="9470d-266">为导入的命令的名称中的名词指定前缀。</span><span class="sxs-lookup"><span data-stu-id="9470d-266">Specifies a prefix to the nouns in the names of imported commands.</span></span>

<span data-ttu-id="9470d-267">使用此参数可避免会话中的不同命令具有相同名称时可能出现的名称冲突。</span><span class="sxs-lookup"><span data-stu-id="9470d-267">Use this parameter to avoid name conflicts that might occur when different commands in the session have the same name.</span></span>

<span data-ttu-id="9470d-268">例如，如果你指定前缀 "远程"，然后导入 Get-Date cmdlet，则该 cmdlet 在会话中是 RemoteDate 的，并且不会与原始的 **获取日期** cmdlet 混淆。</span><span class="sxs-lookup"><span data-stu-id="9470d-268">For instance, if you specify the prefix Remote and then import a Get-Date cmdlet, the cmdlet is known in the session as Get-RemoteDate, and it is not confused with the original **Get-Date** cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9470d-269">-Session</span><span class="sxs-lookup"><span data-stu-id="9470d-269">-Session</span></span>

<span data-ttu-id="9470d-270">指定从中导入 cmdlet 的 **PSSession** 。</span><span class="sxs-lookup"><span data-stu-id="9470d-270">Specifies the **PSSession** from which the cmdlets are imported.</span></span>
<span data-ttu-id="9470d-271">输入包含会话对象的变量或获取会话对象的命令，如 New-PSSession 或 Get-PSSession 命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-271">Enter a variable that contains a session object or a command that gets a session object, such as a New-PSSession or Get-PSSession command.</span></span>
<span data-ttu-id="9470d-272">仅可以指定一个会话。</span><span class="sxs-lookup"><span data-stu-id="9470d-272">You can specify only one session.</span></span>
<span data-ttu-id="9470d-273">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="9470d-273">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9470d-274">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9470d-274">CommonParameters</span></span>

<span data-ttu-id="9470d-275">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9470d-275">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9470d-276">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="9470d-276">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9470d-277">输入</span><span class="sxs-lookup"><span data-stu-id="9470d-277">INPUTS</span></span>

### <span data-ttu-id="9470d-278">无</span><span class="sxs-lookup"><span data-stu-id="9470d-278">None</span></span>

<span data-ttu-id="9470d-279">不能通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-279">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="9470d-280">输出</span><span class="sxs-lookup"><span data-stu-id="9470d-280">OUTPUTS</span></span>

### <span data-ttu-id="9470d-281">System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="9470d-281">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="9470d-282">**Import-module** 返回 New-Module 和 Get-Module cmdlet 返回的相同模块对象。</span><span class="sxs-lookup"><span data-stu-id="9470d-282">**Import-PSSession** returns the same module object that New-Module and Get-Module cmdlets return.</span></span>
<span data-ttu-id="9470d-283">但是，导入的模块是临时的并且仅在当前会话中存在。</span><span class="sxs-lookup"><span data-stu-id="9470d-283">However, the imported module is temporary and exists only in the current session.</span></span>
<span data-ttu-id="9470d-284">若要在磁盘上创建永久模块，请使用 Export-PSSession cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-284">To create a permanent module on disk, use the Export-PSSession cmdlet.</span></span>

## <span data-ttu-id="9470d-285">注释</span><span class="sxs-lookup"><span data-stu-id="9470d-285">NOTES</span></span>

* <span data-ttu-id="9470d-286">**Import-module** 依赖于 PowerShell 远程处理基础结构。</span><span class="sxs-lookup"><span data-stu-id="9470d-286">**Import-PSSession** relies on the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="9470d-287">若要使用此 cmdlet，必须为 WS-Management 远程处理配置计算机。</span><span class="sxs-lookup"><span data-stu-id="9470d-287">To use this cmdlet, the computer must be configured for WS-Management remoting.</span></span> <span data-ttu-id="9470d-288">有关详细信息，请参阅 about_Remote 和 about_Remote_Requirements。</span><span class="sxs-lookup"><span data-stu-id="9470d-288">For more information, see about_Remote and about_Remote_Requirements.</span></span>
* <span data-ttu-id="9470d-289">**Import-module** 不会导入变量或 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="9470d-289">**Import-PSSession** does not import variables or PowerShell providers.</span></span>
* <span data-ttu-id="9470d-290">当你导入与当前会话中的命令具有相同名称的命令时，导入的命令可以隐藏会话中的别名、函数和 cmdlet，并且可以替换会话中的函数和变量。</span><span class="sxs-lookup"><span data-stu-id="9470d-290">When you import commands that have the same names as commands in the current session, the imported commands can hide aliases, functions, and cmdlets in the session and they can replace functions and variables in the session.</span></span> <span data-ttu-id="9470d-291">若要防止名称冲突，请使用 *Prefix* 参数。</span><span class="sxs-lookup"><span data-stu-id="9470d-291">To prevent name conflicts, use the *Prefix* parameter.</span></span> <span data-ttu-id="9470d-292">有关详细信息，请参阅 about_Command_Precedence。</span><span class="sxs-lookup"><span data-stu-id="9470d-292">For more information, see about_Command_Precedence.</span></span>
* <span data-ttu-id="9470d-293">**Import-module** 在导入前将所有命令转换为函数。</span><span class="sxs-lookup"><span data-stu-id="9470d-293">**Import-PSSession** converts all commands into functions before it imports them.</span></span> <span data-ttu-id="9470d-294">这样，导入的命令的行为与保留其原始命令类型时的行为稍有不同。</span><span class="sxs-lookup"><span data-stu-id="9470d-294">As a result, imported commands behave a bit differently than they would if they retained their original command type.</span></span> <span data-ttu-id="9470d-295">例如，如果从 PSSession 中导入一个 cmdlet，然后从模块或管理单元中导入具有相同名称的 cmdlet，则从 PSSession 中导入的 cmdlet 默认始终运行，因为函数优先于 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-295">For example, if you import a cmdlet from a PSSession and then import a cmdlet with the same name from a module or snap-in, the cmdlet that is imported from the PSSession always runs by default because functions take precedence over cmdlets.</span></span> <span data-ttu-id="9470d-296">相反，如果将别名导入到具有相同名称的别名的会话，则始终使用原来的别名，因为别名优先于函数。</span><span class="sxs-lookup"><span data-stu-id="9470d-296">Conversely, if you import an alias into a session that has an alias with the same name, the original alias is always used, because aliases take precedence over functions.</span></span> <span data-ttu-id="9470d-297">有关详细信息，请参阅 about_Command_Precedence。</span><span class="sxs-lookup"><span data-stu-id="9470d-297">For more information, see about_Command_Precedence.</span></span>
* <span data-ttu-id="9470d-298">**Import-module** 使用 Write-Progress cmdlet 来显示该命令的进度。</span><span class="sxs-lookup"><span data-stu-id="9470d-298">**Import-PSSession** uses the Write-Progress cmdlet to display the progress of the command.</span></span> <span data-ttu-id="9470d-299">该命令正在运行时，你可能会看到进度条。</span><span class="sxs-lookup"><span data-stu-id="9470d-299">You might see the progress bar while the command is running.</span></span>
* <span data-ttu-id="9470d-300">为了查找要导入的命令， **import-module** 使用 Invoke-Command Cmdlet 在 PSSession 中运行 Get-Command 命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-300">To find the commands to import, **Import-PSSession** uses the Invoke-Command cmdlet to run a Get-Command command in the PSSession.</span></span> <span data-ttu-id="9470d-301">若要获取命令的格式设置数据，请使用 Get-FormatData cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9470d-301">To get formatting data for the commands, it uses the Get-FormatData cmdlet.</span></span> <span data-ttu-id="9470d-302">运行 **import-module** 命令时，可能会看到来自这些 cmdlet 的错误消息。</span><span class="sxs-lookup"><span data-stu-id="9470d-302">You might see error messages from these cmdlets when you run an **Import-PSSession** command.</span></span> <span data-ttu-id="9470d-303">此外， **import-module** 不能从不包含 get 命令、Update-formatdata、Select-Object 和 Get-Help Cmdlet 的 PSSession 中导入命令。</span><span class="sxs-lookup"><span data-stu-id="9470d-303">Also, **Import-PSSession** cannot import commands from a PSSession that does not include the Get-Command, Get-FormatData, Select-Object, and Get-Help cmdlets.</span></span>
* <span data-ttu-id="9470d-304">导入的命令与其他远程命令具有相同的限制，包括无法通过用户界面（如“记事本”）启动程序。</span><span class="sxs-lookup"><span data-stu-id="9470d-304">Imported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>
* <span data-ttu-id="9470d-305">因为 PowerShell 配置文件不在 Pssession 中运行，所以配置文件添加到会话中的命令不能用于 **import-module** 。</span><span class="sxs-lookup"><span data-stu-id="9470d-305">Because PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to **Import-PSSession** .</span></span> <span data-ttu-id="9470d-306">若要从配置文件中导入命令，请使用 Invoke-Command 命令，以在导入命令之前，在 PSSession 中手动运行该配置文件。</span><span class="sxs-lookup"><span data-stu-id="9470d-306">To import commands from a profile, use an Invoke-Command command to run the profile in the PSSession manually before importing commands.</span></span>
* <span data-ttu-id="9470d-307">**Import-PSSession** 创建的临时模块可能包括格式设置文件，即使该命令不导入格式设置数据也是如此。</span><span class="sxs-lookup"><span data-stu-id="9470d-307">The temporary module that **Import-PSSession** creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="9470d-308">如果该命令不导入格式数据，则创建的任何格式设置文件都不包含格式数据。</span><span class="sxs-lookup"><span data-stu-id="9470d-308">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>
* <span data-ttu-id="9470d-309">若要使用 **Import-PSSession** ，当前会话中的执行策略不能为 Restricted 或 AllSigned，因为 **Import-PSSession** 创建的临时模块包含这些策略禁止的未签名脚本文件。</span><span class="sxs-lookup"><span data-stu-id="9470d-309">To use **Import-PSSession** , the execution policy in the current session cannot be Restricted or AllSigned, because the temporary module that **Import-PSSession** creates contains unsigned script files that are prohibited by these policies.</span></span> <span data-ttu-id="9470d-310">若要在不更改本地计算机的执行策略的情况下使用 **import-module** ，请使用 Set-ExecutionPolicy 的 *作用域* 参数为单个进程设置限制性较低的执行策略。</span><span class="sxs-lookup"><span data-stu-id="9470d-310">To use **Import-PSSession** without changing the execution policy for the local computer, use the *Scope* parameter of Set-ExecutionPolicy to set a less restrictive execution policy for a single process.</span></span>
* <span data-ttu-id="9470d-311">在 Windows PowerShell 2.0 中，从另一个会话中导入的命令的帮助主题不包括通过使用 *Prefix* 参数分配的前缀。</span><span class="sxs-lookup"><span data-stu-id="9470d-311">In Windows PowerShell 2.0, help topics for commands that are imported from another session do not include the prefix that you assign by using the *Prefix* parameter.</span></span> <span data-ttu-id="9470d-312">若要获得 Windows PowerShell 2.0 中导入命令的帮助，请使用原始（无前缀）的命令名称。</span><span class="sxs-lookup"><span data-stu-id="9470d-312">To get help for an imported command in Windows PowerShell 2.0, use the original (non-prefixed) command name.</span></span>

## <span data-ttu-id="9470d-313">相关链接</span><span class="sxs-lookup"><span data-stu-id="9470d-313">RELATED LINKS</span></span>

[<span data-ttu-id="9470d-314">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="9470d-314">Export-PSSession</span></span>](Export-PSSession.md)
