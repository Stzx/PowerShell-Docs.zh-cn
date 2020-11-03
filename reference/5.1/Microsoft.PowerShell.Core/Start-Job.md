---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 116e007cc28a91e3c97fd980cc27461932390b7c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197614"
---
# <span data-ttu-id="cb0d7-103">Start-Job</span><span class="sxs-lookup"><span data-stu-id="cb0d7-103">Start-Job</span></span>

## <span data-ttu-id="cb0d7-104">摘要</span><span class="sxs-lookup"><span data-stu-id="cb0d7-104">SYNOPSIS</span></span>
<span data-ttu-id="cb0d7-105">启动 PowerShell 后台作业。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-105">Starts a PowerShell background job.</span></span>

## <span data-ttu-id="cb0d7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cb0d7-106">SYNTAX</span></span>

### <span data-ttu-id="cb0d7-107">ComputerName（默认值）</span><span class="sxs-lookup"><span data-stu-id="cb0d7-107">ComputerName (Default)</span></span>

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="cb0d7-108">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="cb0d7-108">DefinitionName</span></span>

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="cb0d7-109">FilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="cb0d7-109">FilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="cb0d7-110">LiteralFilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="cb0d7-110">LiteralFilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="cb0d7-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb0d7-111">DESCRIPTION</span></span>

<span data-ttu-id="cb0d7-112">`Start-Job`Cmdlet 在本地计算机上启动 PowerShell 后台作业。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-112">The `Start-Job` cmdlet starts a PowerShell background job on the local computer.</span></span>

<span data-ttu-id="cb0d7-113">PowerShell 后台作业运行命令，而不与当前会话交互。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-113">A PowerShell background job runs a command without interacting with the current session.</span></span> <span data-ttu-id="cb0d7-114">启动后台作业时，作业对象会立即返回，即使该作业需要很长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-114">When you start a background job, a job object returns immediately, even if the job takes an extended time to finish.</span></span> <span data-ttu-id="cb0d7-115">当该作业运行时，你可以继续在此会话中工作而不会发生中断。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-115">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="cb0d7-116">作业对象包含有关该作业的有用信息，但不包含作业结果。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-116">The job object contains useful information about the job, but it doesn't contain the job results.</span></span>
<span data-ttu-id="cb0d7-117">作业完成后，使用 `Receive-Job` cmdlet 获取作业的结果。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-117">When the job finishes, use the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="cb0d7-118">有关后台作业的详细信息，请参阅 [about_Jobs](./About/about_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-118">For more information about background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="cb0d7-119">若要在远程计算机上运行后台作业，请使用多个 cmdlet 上可用的 **AsJob** 参数，或使用 `Invoke-Command` cmdlet `Start-Job` 在远程计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-119">To run a background job on a remote computer, use the **AsJob** parameter that is available on many cmdlets, or use the `Invoke-Command` cmdlet to run a `Start-Job` command on the remote computer.</span></span> <span data-ttu-id="cb0d7-120">有关详细信息，请参阅 [about_Remote_Jobs](./About/about_Remote_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-120">For more information, see [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="cb0d7-121">从 PowerShell 3.0 开始， `Start-Job` 可以启动自定义作业类型的实例，例如计划作业。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-121">Starting in PowerShell 3.0, `Start-Job` can start instances of custom job types, such as scheduled jobs.</span></span> <span data-ttu-id="cb0d7-122">有关如何使用 `Start-Job` 来启动具有自定义类型的作业的信息，请参阅作业类型功能的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-122">For information about how to use `Start-Job` to start jobs with custom types, see the help documents for the job type feature.</span></span>

<span data-ttu-id="cb0d7-123">作业的默认工作目录是硬编码的。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-123">The default working directory for jobs is hardcoded.</span></span> <span data-ttu-id="cb0d7-124">Windows 默认值为 `$HOME\Documents` ，Linux 或 macOS 上的默认值为 `$HOME` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-124">The Windows default is `$HOME\Documents` and on Linux or macOS the default is `$HOME`.</span></span> <span data-ttu-id="cb0d7-125">在后台作业中运行的脚本代码需要根据需要管理工作目录。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-125">The script code running in the background job needs to manage the working directory as needed.</span></span>

## <span data-ttu-id="cb0d7-126">示例</span><span class="sxs-lookup"><span data-stu-id="cb0d7-126">EXAMPLES</span></span>

### <span data-ttu-id="cb0d7-127">示例1：启动后台作业</span><span class="sxs-lookup"><span data-stu-id="cb0d7-127">Example 1: Start a background job</span></span>

<span data-ttu-id="cb0d7-128">此示例启动在本地计算机上运行的后台作业。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-128">This example starts a background job that runs on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name powershell }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name powershell
```

<span data-ttu-id="cb0d7-129">`Start-Job` 使用 **ScriptBlock** 参数 `Get-Process` 作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-129">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Process` as a background job.</span></span> <span data-ttu-id="cb0d7-130">**Name** 参数指定查找 PowerShell 进程 `powershell` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-130">The **Name** parameter specifies to find PowerShell processes, `powershell`.</span></span> <span data-ttu-id="cb0d7-131">当作业在后台运行时，将显示作业信息并返回到提示符。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-131">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="cb0d7-132">若要查看作业的输出，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-132">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="cb0d7-133">例如，`Receive-Job -Id 1`。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-133">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="cb0d7-134">示例2：使用 Invoke-Command 启动作业</span><span class="sxs-lookup"><span data-stu-id="cb0d7-134">Example 2: Start a job using Invoke-Command</span></span>

<span data-ttu-id="cb0d7-135">此示例在多台计算机上运行作业。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-135">This example runs a job on multiple computers.</span></span> <span data-ttu-id="cb0d7-136">作业存储在一个变量中，并通过使用 PowerShell 命令行上的变量名称来执行。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-136">The job is stored in a variable and is executed by using the variable name on the PowerShell command line.</span></span>

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

<span data-ttu-id="cb0d7-137">将创建一个使用的作业并将其 `Invoke-Command` 存储在 `$jobWRM` 变量中。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-137">A job that uses `Invoke-Command` is created and stored in the `$jobWRM` variable.</span></span> <span data-ttu-id="cb0d7-138">`Invoke-Command` 使用 **ComputerName** 参数来指定运行作业的计算机。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-138">`Invoke-Command` uses the **ComputerName** parameter to specify the computers where the job runs.</span></span> <span data-ttu-id="cb0d7-139">`Get-Content` 从文件中获取服务器名称 `C:\Servers.txt` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-139">`Get-Content` gets the server names from the `C:\Servers.txt` file.</span></span>

<span data-ttu-id="cb0d7-140">**ScriptBlock** 参数指定用于 `Get-Service` 获取 **WinRM** 服务的命令。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-140">The **ScriptBlock** parameter specifies a command that `Get-Service` gets the **WinRM** service.</span></span> <span data-ttu-id="cb0d7-141">**JobName** 参数指定作业 **WinRM** 的友好名称。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-141">The **JobName** parameter specifies a friendly name for the job, **WinRM** .</span></span> <span data-ttu-id="cb0d7-142">**ThrottleLimit** 参数将并发命令数限制为16。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-142">The **ThrottleLimit** parameter limits the number of concurrent commands to 16.</span></span> <span data-ttu-id="cb0d7-143">**AsJob** 参数启动在服务器上运行命令的后台作业。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-143">The **AsJob** parameter starts a background job that runs the command on the servers.</span></span>

### <span data-ttu-id="cb0d7-144">示例3：获取作业信息</span><span class="sxs-lookup"><span data-stu-id="cb0d7-144">Example 3: Get job information</span></span>

<span data-ttu-id="cb0d7-145">此示例将获取有关作业的信息，并显示在本地计算机上运行的已完成作业的结果。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-145">This example gets information about a job and displays the results of a completed job that was run on the local computer.</span></span>

```powershell
$j = Start-Job -ScriptBlock { Get-WinEvent -Log System } -Credential Domain01\User01
$j | Select-Object -Property *
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-WinEvent -Log System
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : 27ce3fd9-40ed-488a-99e5-679cd91b9dd3
Id            : 18
Name          : Job18
ChildJobs     : {Job19}
PSBeginTime   : 8/8/2019 14:41:57
PSEndTime     : 8/8/2019 14:42:07
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

<span data-ttu-id="cb0d7-146">`Start-Job` 使用 **ScriptBlock** 参数来运行命令，该命令指定 `Get-WinEvent` 获取 **系统** 日志。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-146">`Start-Job` uses the **ScriptBlock** parameter to run a command that specifies `Get-WinEvent` to get the **System** log.</span></span> <span data-ttu-id="cb0d7-147">**Credential** 参数指定有权在计算机上运行作业的域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-147">The **Credential** parameter specifies a domain user account with permission to run the job on the computer.</span></span> <span data-ttu-id="cb0d7-148">作业对象存储在 `$j` 变量中。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-148">The job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="cb0d7-149">变量中的对象将 `$j` 向下发送到 `Select-Object` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-149">The object in the `$j` variable is sent down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="cb0d7-150">**Property** 参数指定星号 (`*`) 以显示作业对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-150">The **Property** parameter specifies an asterisk (`*`) to display all the job object's properties.</span></span>

### <span data-ttu-id="cb0d7-151">示例4：将脚本作为后台作业运行</span><span class="sxs-lookup"><span data-stu-id="cb0d7-151">Example 4: Run a script as a background job</span></span>

<span data-ttu-id="cb0d7-152">在此示例中，本地计算机上的脚本作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-152">In this example, a script on the local computer is run as a background job.</span></span>

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

<span data-ttu-id="cb0d7-153">`Start-Job` 使用 **FilePath** 参数来指定存储在本地计算机上的脚本文件。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-153">`Start-Job` uses the **FilePath** parameter to specify a script file that's stored on the local computer.</span></span>

### <span data-ttu-id="cb0d7-154">示例5：使用后台作业获取进程</span><span class="sxs-lookup"><span data-stu-id="cb0d7-154">Example 5: Get a process using a background job</span></span>

<span data-ttu-id="cb0d7-155">此示例使用后台作业按名称获取指定的进程。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-155">This example uses a background job to get a specified process by name.</span></span>

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

<span data-ttu-id="cb0d7-156">`Start-Job` 使用 **Name** 参数指定友好的作业名称 **PShellJob** 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-156">`Start-Job` uses the **Name** parameter to specify a friendly job name, **PShellJob** .</span></span> <span data-ttu-id="cb0d7-157">**ScriptBlock** 参数指定 `Get-Process` 获取名称为 **PowerShell** 的进程。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-157">The **ScriptBlock** parameter specifies `Get-Process` to get processes with the name **PowerShell** .</span></span>

### <span data-ttu-id="cb0d7-158">示例6：使用后台作业收集和保存数据</span><span class="sxs-lookup"><span data-stu-id="cb0d7-158">Example 6: Collect and save data by using a background job</span></span>

<span data-ttu-id="cb0d7-159">此示例将启动一个作业，该作业收集大量的地图数据，然后将其保存到 `.tif` 文件中。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-159">This example starts a job that collects a large amount of map data and then saves it in a `.tif` file.</span></span>

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif } -RunAs32
```

<span data-ttu-id="cb0d7-160">`Start-Job` 使用 **Name** 参数指定友好的作业名称 **GetMappingFiles** 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-160">`Start-Job` uses the **Name** parameter to specify a friendly job name, **GetMappingFiles** .</span></span> <span data-ttu-id="cb0d7-161">**InitializationScript** 参数运行导入 **MapFunctions** 模块的脚本块。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-161">The **InitializationScript** parameter runs a script block that imports the **MapFunctions** module.</span></span> <span data-ttu-id="cb0d7-162">**ScriptBlock** 参数运行 `Get-Map` 并将 `Set-Content` 数据保存在 **Path** 参数指定的位置。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-162">The **ScriptBlock** parameter runs `Get-Map` and `Set-Content` saves the data in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="cb0d7-163">**RunAs32** 参数将进程作为32位运行，即使在64位操作系统上也是如此。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-163">The **RunAs32** parameter runs the process as 32-bit, even on a 64-bit operating system.</span></span>

### <span data-ttu-id="cb0d7-164">示例7：将输入传递到后台作业</span><span class="sxs-lookup"><span data-stu-id="cb0d7-164">Example 7: Pass input to a background job</span></span>

<span data-ttu-id="cb0d7-165">此示例使用 `$input` 自动变量来处理输入对象。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-165">This example uses the `$input` automatic variable to process an input object.</span></span> <span data-ttu-id="cb0d7-166">使用 `Receive-Job` 查看作业的输出。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-166">Use `Receive-Job` to view the job's output.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Content $input } -InputObject "C:\Servers.txt"
Receive-Job -Name Job45 -Keep
```

```Output
Server01
Server02
Server03
Server04
```

<span data-ttu-id="cb0d7-167">`Start-Job`使用 **ScriptBlock** `Get-Content` 带有自动变量的 ScriptBlock 参数运行 `$input` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-167">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Content` with the `$input` automatic variable.</span></span> <span data-ttu-id="cb0d7-168">`$input`变量从 **InputObject** 参数获取对象。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-168">The `$input` variable gets objects from the **InputObject** parameter.</span></span> <span data-ttu-id="cb0d7-169">`Receive-Job` 使用 **Name** 参数指定作业并输出结果。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-169">`Receive-Job` uses the **Name** parameter to specify the job and outputs the results.</span></span> <span data-ttu-id="cb0d7-170">**Keep** 参数保存作业输出，以便可以在 PowerShell 会话期间再次查看。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-170">The **Keep** parameter saves the job output so it can be viewed again during the PowerShell session.</span></span>

### <span data-ttu-id="cb0d7-171">示例8：使用 ArgumentList 参数指定数组</span><span class="sxs-lookup"><span data-stu-id="cb0d7-171">Example 8: Use the ArgumentList parameter to specify an array</span></span>

<span data-ttu-id="cb0d7-172">此示例使用 **ArgumentList** 参数来指定参数数组。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-172">This example uses the **ArgumentList** parameter to specify an array of arguments.</span></span> <span data-ttu-id="cb0d7-173">数组是以逗号分隔的进程名称列表。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-173">The array is a comma-separated list of process names.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

<span data-ttu-id="cb0d7-174">`Start-Job`Cmdlet 使用 **ScriptBlock** 参数运行命令。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-174">The `Start-Job` cmdlet uses the **ScriptBlock** parameter to run a command.</span></span> <span data-ttu-id="cb0d7-175">`Get-Process` 使用 **Name** 参数来指定自动变量 `$args` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-175">`Get-Process` uses the **Name** parameter to specify the automatic variable `$args`.</span></span> <span data-ttu-id="cb0d7-176">**ArgumentList** 参数将进程名称数组传递给 `$args` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-176">The **ArgumentList** parameter passes the array of process names to `$args`.</span></span> <span data-ttu-id="cb0d7-177">进程名称 "powershell"、"pwsh" 和 "记事本" 是在本地计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-177">The process names powershell, pwsh, and notepad are processes running on the local computer.</span></span>

<span data-ttu-id="cb0d7-178">若要查看作业的输出，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-178">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="cb0d7-179">例如，`Receive-Job -Id 1`。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-179">For example, `Receive-Job -Id 1`.</span></span>

## <span data-ttu-id="cb0d7-180">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cb0d7-180">PARAMETERS</span></span>

### <span data-ttu-id="cb0d7-181">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="cb0d7-181">-ArgumentList</span></span>

<span data-ttu-id="cb0d7-182">指定由 **FilePath** 参数或使用 **ScriptBlock** 参数指定的命令指定的脚本的参数数组或参数值。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-182">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** parameter or a command specified with the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="cb0d7-183">参数必须以单维度数组参数的形式传递给 **ArgumentList** 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-183">Arguments must be passed to **ArgumentList** as single-dimension array argument.</span></span> <span data-ttu-id="cb0d7-184">例如，以逗号分隔的列表。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-184">For example, a comma-separated list.</span></span> <span data-ttu-id="cb0d7-185">有关 **ArgumentList** 行为的详细信息，请参阅 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-185">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-186">-Authentication</span><span class="sxs-lookup"><span data-stu-id="cb0d7-186">-Authentication</span></span>

<span data-ttu-id="cb0d7-187">指定用于对用户凭据进行身份验证的机制。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-187">Specifies the mechanism that is used to authenticate user credentials.</span></span>

<span data-ttu-id="cb0d7-188">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="cb0d7-188">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="cb0d7-189">默认</span><span class="sxs-lookup"><span data-stu-id="cb0d7-189">Default</span></span>
- <span data-ttu-id="cb0d7-190">基本</span><span class="sxs-lookup"><span data-stu-id="cb0d7-190">Basic</span></span>
- <span data-ttu-id="cb0d7-191">Credssp</span><span class="sxs-lookup"><span data-stu-id="cb0d7-191">Credssp</span></span>
- <span data-ttu-id="cb0d7-192">摘要</span><span class="sxs-lookup"><span data-stu-id="cb0d7-192">Digest</span></span>
- <span data-ttu-id="cb0d7-193">Kerberos</span><span class="sxs-lookup"><span data-stu-id="cb0d7-193">Kerberos</span></span>
- <span data-ttu-id="cb0d7-194">Negotiate</span><span class="sxs-lookup"><span data-stu-id="cb0d7-194">Negotiate</span></span>
- <span data-ttu-id="cb0d7-195">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="cb0d7-195">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="cb0d7-196">默认值为 Default。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-196">The default value is Default.</span></span>

<span data-ttu-id="cb0d7-197">CredSSP 身份验证仅在 Windows Vista、Windows Server 2008 和更高版本的 Windows 操作系统中可用。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-197">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="cb0d7-198">有关此参数的值的详细信息，请参阅 [system.management.automation.runspaces.authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-198">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="cb0d7-199">在凭据安全支持提供程序 (CredSSP) 身份验证中，用户凭据传递到远程计算机中以进行验证，这种验证用于要求对多个资源（例如访问远程网络共享）进行验证的命令。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-199">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="cb0d7-200">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-200">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="cb0d7-201">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-201">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-202">-Credential</span><span class="sxs-lookup"><span data-stu-id="cb0d7-202">-Credential</span></span>

<span data-ttu-id="cb0d7-203">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-203">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="cb0d7-204">如果未指定 **Credential** 参数，则该命令使用当前用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-204">If the **Credential** parameter isn't specified, the command uses the current user's credentials.</span></span>

<span data-ttu-id="cb0d7-205">键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-205">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="cb0d7-206">如果键入用户名，系统会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-206">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="cb0d7-207">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-207">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="cb0d7-208">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-208">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-209">-DefinitionName</span><span class="sxs-lookup"><span data-stu-id="cb0d7-209">-DefinitionName</span></span>

<span data-ttu-id="cb0d7-210">指定此 cmdlet 启动的作业的定义名称。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-210">Specifies the definition name of the job that this cmdlet starts.</span></span> <span data-ttu-id="cb0d7-211">使用此参数来启动具有定义名称的自定义作业，例如计划作业。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-211">Use this parameter to start custom job types that have a definition name, such as scheduled jobs.</span></span>

<span data-ttu-id="cb0d7-212">当使用 `Start-Job` 启动计划作业的实例时，将立即启动该作业，而不考虑作业触发器或作业选项。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-212">When you use `Start-Job` to start an instance of a scheduled job, the job starts immediately, regardless of job triggers or job options.</span></span> <span data-ttu-id="cb0d7-213">生成的作业实例是计划作业，但不会将其保存到磁盘上，如触发的计划作业。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-213">The resulting job instance is a scheduled job, but it isn't saved to disk like triggered scheduled jobs.</span></span> <span data-ttu-id="cb0d7-214">不能使用的 **ArgumentList** 参数为 `Start-Job` 在计划作业中运行的脚本的参数提供值。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-214">You can't use the **ArgumentList** parameter of `Start-Job` to provide values for parameters of scripts that run in a scheduled job.</span></span> <span data-ttu-id="cb0d7-215">有关详细信息，请参阅 [about_Scheduled_Jobs](../PSScheduledJob/About/about_Scheduled_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-215">For more information, see [about_Scheduled_Jobs](../PSScheduledJob/About/about_Scheduled_Jobs.md).</span></span>

<span data-ttu-id="cb0d7-216">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-216">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-217">-DefinitionPath</span><span class="sxs-lookup"><span data-stu-id="cb0d7-217">-DefinitionPath</span></span>

<span data-ttu-id="cb0d7-218">指定此 cmdlet 启动的作业的定义路径。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-218">Specifies path of the definition for the job that this cmdlet starts.</span></span> <span data-ttu-id="cb0d7-219">输入定义路径。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-219">Enter the definition path.</span></span> <span data-ttu-id="cb0d7-220">**DefinitionPath** 和 **DefinitionName** 参数的值的串联是作业定义的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-220">The concatenation of the values of the **DefinitionPath** and **DefinitionName** parameters is the fully qualified path of the job definition.</span></span> <span data-ttu-id="cb0d7-221">使用此参数来启动具有定义路径的自定义作业，例如计划作业。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-221">Use this parameter to start custom job types that have a definition path, such as scheduled jobs.</span></span>

<span data-ttu-id="cb0d7-222">对于计划作业， **DefinitionPath** 参数的值为 `$home\AppData\Local\Windows\PowerShell\ScheduledJob` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-222">For scheduled jobs, the value of the **DefinitionPath** parameter is `$home\AppData\Local\Windows\PowerShell\ScheduledJob`.</span></span>

<span data-ttu-id="cb0d7-223">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-223">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-224">-FilePath</span><span class="sxs-lookup"><span data-stu-id="cb0d7-224">-FilePath</span></span>

<span data-ttu-id="cb0d7-225">指定 `Start-Job` 作为后台作业运行的本地脚本。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-225">Specifies a local script that `Start-Job` runs as a background job.</span></span> <span data-ttu-id="cb0d7-226">输入脚本的路径和文件名，或使用管道将脚本路径发送到 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-226">Enter the path and file name of the script or use the pipeline to send a script path to `Start-Job`.</span></span> <span data-ttu-id="cb0d7-227">脚本必须位于本地计算机上或本地计算机可以访问的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-227">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="cb0d7-228">使用此参数时，PowerShell 会将指定脚本文件的内容转换为脚本块，并将该脚本块作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-228">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-229">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="cb0d7-229">-InitializationScript</span></span>

<span data-ttu-id="cb0d7-230">指定在作业开始前运行的命令。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-230">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="cb0d7-231">若要创建脚本块，请将命令括在大括号中， (`{}`) 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-231">To create a script block, enclose the commands in curly braces (`{}`).</span></span>

<span data-ttu-id="cb0d7-232">使用此参数可以准备运行作业的会话。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-232">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="cb0d7-233">例如，可以使用它将函数、管理单元和模块添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-233">For example, you can use it to add functions, snap-ins, and modules to the session.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-234">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cb0d7-234">-InputObject</span></span>

<span data-ttu-id="cb0d7-235">指定命令的输入。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-235">Specifies input to the command.</span></span> <span data-ttu-id="cb0d7-236">请输入包含对象的变量，或者键入可生成对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-236">Enter a variable that contains the objects, or type a command or expression that generates the objects.</span></span>

<span data-ttu-id="cb0d7-237">在 **ScriptBlock** 参数的值中，使用 `$input` 自动变量来表示输入对象。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-237">In the value of the **ScriptBlock** parameter, use the `$input` automatic variable to represent the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-238">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="cb0d7-238">-LiteralPath</span></span>

<span data-ttu-id="cb0d7-239">指定此 cmdlet 作为后台作业运行的本地脚本。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-239">Specifies a local script that this cmdlet runs as a background job.</span></span> <span data-ttu-id="cb0d7-240">在本地计算机上输入脚本的路径。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-240">Enter the path of a script on the local computer.</span></span>

<span data-ttu-id="cb0d7-241">`Start-Job` 使用 **LiteralPath** 参数的值，与键入的值完全相同。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-241">`Start-Job` uses the value of the **LiteralPath** parameter exactly as it's typed.</span></span> <span data-ttu-id="cb0d7-242">不会将任何字符解释为通配字符。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-242">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="cb0d7-243">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-243">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="cb0d7-244">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-244">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralFilePathComputerName
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-245">-Name</span><span class="sxs-lookup"><span data-stu-id="cb0d7-245">-Name</span></span>

<span data-ttu-id="cb0d7-246">为新作业指定一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-246">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="cb0d7-247">你可以使用该名称来确定其他作业 cmdlet （如 cmdlet）的作业 `Stop-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-247">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="cb0d7-248">默认友好名称为 `Job#` ，其中 `#` 是每个作业递增的序号。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-248">The default friendly name is `Job#`, where `#` is an ordinal number that is incremented for each job.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-249">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="cb0d7-249">-PSVersion</span></span>

<span data-ttu-id="cb0d7-250">指定版本。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-250">Specifies a version.</span></span> <span data-ttu-id="cb0d7-251">`Start-Job` 用 PowerShell 的版本运行作业。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-251">`Start-Job` runs the job with the version of PowerShell.</span></span> <span data-ttu-id="cb0d7-252">此参数可接受的值包括： `2.0` 和 `3.0` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-252">The acceptable values for this parameter are: `2.0` and `3.0`.</span></span>

<span data-ttu-id="cb0d7-253">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-253">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-254">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="cb0d7-254">-RunAs32</span></span>

<span data-ttu-id="cb0d7-255">指示 `Start-Job` 在32位进程中运行作业。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-255">Indicates that `Start-Job` runs the job in a 32-bit process.</span></span> <span data-ttu-id="cb0d7-256">**RunAs32** 强制作业在32位进程中运行，即使在64位操作系统上也是如此。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-256">**RunAs32** forces the job to run in a 32-bit process, even on a 64-bit operating system.</span></span>

<span data-ttu-id="cb0d7-257">在64位版本的 Windows 7 和 Windows Server 2008 R2 上，当 `Start-Job` 命令包括 **RunAs32** 参数时，不能使用 **Credential** 参数来指定另一个用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-257">On 64-bit versions of Windows 7 and Windows Server 2008 R2, when the `Start-Job` command includes the **RunAs32** parameter, you can't use the **Credential** parameter to specify the credentials of another user.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-258">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="cb0d7-258">-ScriptBlock</span></span>

<span data-ttu-id="cb0d7-259">指定要在后台作业中运行的命令。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-259">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="cb0d7-260">若要创建脚本块，请将命令括在大括号中， (`{}`) 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-260">To create a script block, enclose the commands in curly braces (`{}`).</span></span> <span data-ttu-id="cb0d7-261">使用 `$input` 自动变量访问 **InputObject** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-261">Use the `$input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="cb0d7-262">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-262">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-263">-Type</span><span class="sxs-lookup"><span data-stu-id="cb0d7-263">-Type</span></span>

<span data-ttu-id="cb0d7-264">指定由启动的作业的自定义类型 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-264">Specifies the custom type for jobs started by `Start-Job`.</span></span> <span data-ttu-id="cb0d7-265">输入自定义作业类型名称，例如 PSScheduledJob（对于计划作业）或 PSWorkflowJob（对于工作流作业）。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-265">Enter a custom job type name, such as PSScheduledJob for scheduled jobs or PSWorkflowJob for workflows jobs.</span></span> <span data-ttu-id="cb0d7-266">此参数对标准后台作业无效。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-266">This parameter isn't valid for standard background jobs.</span></span>

<span data-ttu-id="cb0d7-267">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-267">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cb0d7-268">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cb0d7-268">CommonParameters</span></span>

<span data-ttu-id="cb0d7-269">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-269">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cb0d7-270">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-270">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cb0d7-271">输入</span><span class="sxs-lookup"><span data-stu-id="cb0d7-271">INPUTS</span></span>

### <span data-ttu-id="cb0d7-272">System.String</span><span class="sxs-lookup"><span data-stu-id="cb0d7-272">System.String</span></span>

<span data-ttu-id="cb0d7-273">可以使用管道将具有 **name** 属性的对象发送到 **name** 参数。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-273">You can use the pipeline to send an object with the **Name** property to the **Name** parameter.</span></span> <span data-ttu-id="cb0d7-274">例如，可以通过管道将 **FileInfo** 对象从管道 `Get-ChildItem` 管道 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-274">For example, you can pipeline a **FileInfo** object from `Get-ChildItem` to `Start-Job`.</span></span>

## <span data-ttu-id="cb0d7-275">输出</span><span class="sxs-lookup"><span data-stu-id="cb0d7-275">OUTPUTS</span></span>

### <span data-ttu-id="cb0d7-276">System.Management.Automation.PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="cb0d7-276">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="cb0d7-277">`Start-Job` 返回一个 **PSRemotingJob** 对象，该对象表示其启动的作业。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-277">`Start-Job` returns a **PSRemotingJob** object that represents the job that it started.</span></span>

## <span data-ttu-id="cb0d7-278">注释</span><span class="sxs-lookup"><span data-stu-id="cb0d7-278">NOTES</span></span>

<span data-ttu-id="cb0d7-279">若要在后台运行，请 `Start-Job` 在当前会话中自己的会话中运行。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-279">To run in the background, `Start-Job` runs in its own session in the current session.</span></span> <span data-ttu-id="cb0d7-280">使用 `Invoke-Command` cmdlet 在 `Start-Job` 远程计算机上的会话中运行命令时，将 `Start-Job` 在远程会话的会话中运行。</span><span class="sxs-lookup"><span data-stu-id="cb0d7-280">When you use the `Invoke-Command` cmdlet to run a `Start-Job` command in a session on a remote computer, `Start-Job` runs in a session in the remote session.</span></span>

## <span data-ttu-id="cb0d7-281">相关链接</span><span class="sxs-lookup"><span data-stu-id="cb0d7-281">RELATED LINKS</span></span>

[<span data-ttu-id="cb0d7-282">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="cb0d7-282">about_Arrays</span></span>](./about/about_arrays.md)

[<span data-ttu-id="cb0d7-283">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="cb0d7-283">about_Automatic_Variables</span></span>](./about/about_automatic_variables.md)

[<span data-ttu-id="cb0d7-284">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="cb0d7-284">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="cb0d7-285">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="cb0d7-285">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="cb0d7-286">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="cb0d7-286">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="cb0d7-287">Get-Job</span><span class="sxs-lookup"><span data-stu-id="cb0d7-287">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="cb0d7-288">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="cb0d7-288">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="cb0d7-289">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="cb0d7-289">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="cb0d7-290">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="cb0d7-290">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="cb0d7-291">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="cb0d7-291">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="cb0d7-292">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="cb0d7-292">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="cb0d7-293">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="cb0d7-293">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="cb0d7-294">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="cb0d7-294">Wait-Job</span></span>](Wait-Job.md)
