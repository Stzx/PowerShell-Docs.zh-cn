---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: b69688891df70c396d19911624c58ae7733183d0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197596"
---
# <span data-ttu-id="e55f5-103">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="e55f5-103">Wait-Job</span></span>

## <span data-ttu-id="e55f5-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e55f5-104">SYNOPSIS</span></span>
<span data-ttu-id="e55f5-105">禁止显示命令提示符，直到在会话中运行的一个或所有 PowerShell 后台作业完成。</span><span class="sxs-lookup"><span data-stu-id="e55f5-105">Suppresses the command prompt until one or all of the PowerShell background jobs running in the session are completed.</span></span>

## <span data-ttu-id="e55f5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e55f5-106">SYNTAX</span></span>

### <span data-ttu-id="e55f5-107">SessionIdParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="e55f5-107">SessionIdParameterSet (Default)</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="e55f5-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="e55f5-108">JobParameterSet</span></span>

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="e55f5-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="e55f5-109">NameParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="e55f5-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="e55f5-110">InstanceIdParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="e55f5-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="e55f5-111">StateParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="e55f5-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="e55f5-112">FilterParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="e55f5-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e55f5-113">DESCRIPTION</span></span>

<span data-ttu-id="e55f5-114">**Wait** cmdlet 会等待 PowerShell 后台作业完成，然后再显示命令提示符。</span><span class="sxs-lookup"><span data-stu-id="e55f5-114">The **Wait-Job** cmdlet waits for PowerShell background jobs to finish before it displays the command prompt.</span></span>
<span data-ttu-id="e55f5-115">可以等待某一个后台作业完成或所有后台作业完成，并可为作业设置最长等待时间。</span><span class="sxs-lookup"><span data-stu-id="e55f5-115">You can wait until any background job is complete, or until all background jobs are complete, and you can set a maximum wait time for the job.</span></span>

<span data-ttu-id="e55f5-116">当作业中的命令完成时， **Wait-Job** 将显示命令提示符并返回作业对象，以便你可以通过管道将该对象传递给另一个命令。</span><span class="sxs-lookup"><span data-stu-id="e55f5-116">When the commands in the job are complete, **Wait-Job** displays the command prompt and returns a job object so that you can pipe it to another command.</span></span>

<span data-ttu-id="e55f5-117">可以使用 **Wait-Job** cmdlet 等待后台作业，例如使用 Start-Job cmdlet 或 Invoke-Command cmdlet 的 *AsJob* 参数启动的后台作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-117">You can use **Wait-Job** cmdlet to wait for background jobs, such as those that were started by using the Start-Job cmdlet or the *AsJob* parameter of the Invoke-Command cmdlet.</span></span>
<span data-ttu-id="e55f5-118">有关 PowerShell 后台作业的详细信息，请参阅 about_Jobs。</span><span class="sxs-lookup"><span data-stu-id="e55f5-118">For more information about PowerShell background jobs, see about_Jobs.</span></span>

<span data-ttu-id="e55f5-119">从 Windows PowerShell 3.0 开始， **等待** cmdlet 还会等待自定义作业类型，例如工作流作业和计划作业的实例。</span><span class="sxs-lookup"><span data-stu-id="e55f5-119">Starting in Windows PowerShell 3.0, the **Wait-Job** cmdlet also waits for custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="e55f5-120">若要使 **等待作业** 等待特定类型的作业，请在运行 Get-Job cmdlet 之前将支持自定义作业类型的模块导入到会话中，方法是使用 Import-Module cmdlet，或者使用或在模块中获取 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e55f5-120">To enable **Wait-Job** to wait for jobs of a particular type, import the module that supports the custom job type into the session before you run the Get-Job cmdlet, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="e55f5-121">有关特定的自定义作业类型的信息，请参阅自定义作业类型功能的文档。</span><span class="sxs-lookup"><span data-stu-id="e55f5-121">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="e55f5-122">示例</span><span class="sxs-lookup"><span data-stu-id="e55f5-122">EXAMPLES</span></span>

### <span data-ttu-id="e55f5-123">示例1：等待所有作业</span><span class="sxs-lookup"><span data-stu-id="e55f5-123">Example 1: Wait for all jobs</span></span>

```powershell
Get-Job | Wait-Job
```

<span data-ttu-id="e55f5-124">此命令等待在会话中运行的所有后台作业完成。</span><span class="sxs-lookup"><span data-stu-id="e55f5-124">This command waits for all of the background jobs running in the session to finish.</span></span>

### <span data-ttu-id="e55f5-125">示例2：使用 Start-Job 等待远程计算机上启动的作业</span><span class="sxs-lookup"><span data-stu-id="e55f5-125">Example 2: Wait for jobs started on remote computers by using Start-Job</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
$done.Count
```

```Output
3
```

<span data-ttu-id="e55f5-126">此示例演示如何通过使用 **启动作业** cmdlet，将 **Wait** cmdlet 用于远程计算机上启动的作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-126">This example shows how to use the **Wait-Job** cmdlet with jobs started on remote computers by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="e55f5-127">**启动作业** 和 **等待作业** 命令都使用 **命令调用** cmdlet 提交到远程计算机。</span><span class="sxs-lookup"><span data-stu-id="e55f5-127">Both **Start-Job** and **Wait-Job** commands are submitted to the remote computer by using the **Invoke-Command** cmdlet.</span></span>

<span data-ttu-id="e55f5-128">此示例使用 **Wait** 来确定在三台不同计算机上作为后台作业运行的 Get-Date 命令是否完成。</span><span class="sxs-lookup"><span data-stu-id="e55f5-128">This example uses **Wait-Job** to determine whether a Get-Date command running as a background job on three different computers is finished.</span></span>

<span data-ttu-id="e55f5-129">第一个命令在三台远程计算机上 ( **PSSession** ) 创建 PowerShell 会话，并将它们存储在 $s 变量中。</span><span class="sxs-lookup"><span data-stu-id="e55f5-129">The first command creates a PowerShell session ( **PSSession** ) on each of the three remote computers and stores them in the $s variable.</span></span>

<span data-ttu-id="e55f5-130">第二个命令使用 **Invoke 命令** 在 $s 的三个会话中的每个会话中运行 **Start-Job** 。</span><span class="sxs-lookup"><span data-stu-id="e55f5-130">The second command uses **Invoke-Command** to run **Start-Job** in each of the three sessions in $s.</span></span>
<span data-ttu-id="e55f5-131">所有作业都命名为 Date1。</span><span class="sxs-lookup"><span data-stu-id="e55f5-131">All of the jobs are named Date1.</span></span>

<span data-ttu-id="e55f5-132">第三个命令使用 **Invoke 命令** 来运行 **等待作业** 。</span><span class="sxs-lookup"><span data-stu-id="e55f5-132">The third command uses **Invoke-Command** to run **Wait-Job** .</span></span>
<span data-ttu-id="e55f5-133">此命令等待每台计算机上的 Date1 作业完成。</span><span class="sxs-lookup"><span data-stu-id="e55f5-133">This command waits for the Date1 jobs on each computer to finish.</span></span>
<span data-ttu-id="e55f5-134">它将生成的作业对象集合（数组）存储在 $done 变量中。</span><span class="sxs-lookup"><span data-stu-id="e55f5-134">It stores the resulting collection (array) of job objects in the $done variable.</span></span>

<span data-ttu-id="e55f5-135">第四个命令使用 $done 变量中的作业对象数组的 **Count** 属性来确定完成的作业数。</span><span class="sxs-lookup"><span data-stu-id="e55f5-135">The fourth command uses the **Count** property of the array of job objects in the $done variable to determine how many of the jobs are finished.</span></span>

### <span data-ttu-id="e55f5-136">示例3：确定第一次后台作业何时完成</span><span class="sxs-lookup"><span data-stu-id="e55f5-136">Example 3: Determine when the first background job finishes</span></span>

```powershell
$s = New-PSSession (Get-Content Machines.txt)
$c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

<span data-ttu-id="e55f5-137">此示例使用 **Wait** 的 *Any* 参数来确定在当前会话中运行的多个后台作业中的第一个作业完成的时间。</span><span class="sxs-lookup"><span data-stu-id="e55f5-137">This example uses the *Any* parameter of **Wait-Job** to determine when the first of many background jobs running in the current session are completed.</span></span>
<span data-ttu-id="e55f5-138">它还演示了如何使用 **wait** cmdlet 等待远程作业完成。</span><span class="sxs-lookup"><span data-stu-id="e55f5-138">It also shows how to use the **Wait-Job** cmdlet to wait for remote jobs to finish.</span></span>

<span data-ttu-id="e55f5-139">第一个命令在 Machines.txt 文件中列出的每台计算机上创建 **pssession** ，并将 **pssession** 对象存储在 $s 变量中。</span><span class="sxs-lookup"><span data-stu-id="e55f5-139">The first command creates a **PSSession** on each of the computers listed in the Machines.txt file and stores the **PSSession** objects in the $s variable.</span></span>
<span data-ttu-id="e55f5-140">该命令使用 Get-Content cmdlet 获取文件的内容。</span><span class="sxs-lookup"><span data-stu-id="e55f5-140">The command uses the Get-Content cmdlet to get the contents of the file.</span></span>
<span data-ttu-id="e55f5-141">**Get Content** 命令括在括号中，以确保它在 New-PSSession 命令之前运行。</span><span class="sxs-lookup"><span data-stu-id="e55f5-141">The **Get-Content** command is enclosed in parentheses to make sure that it runs before the New-PSSession command.</span></span>

<span data-ttu-id="e55f5-142">第二个命令在 $c 变量中存储 **Get-EventLog** 命令字符串，用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="e55f5-142">The second command stores a **Get-EventLog** command string, in quotation marks, in the $c variable.</span></span>

<span data-ttu-id="e55f5-143">第三个命令使用 Invoke-Command cmdlet 在 $s 中的每个会话中运行 **启动作业** 。</span><span class="sxs-lookup"><span data-stu-id="e55f5-143">The third command uses Invoke-Command cmdlet to run **Start-Job** in each of the sessions in $s.</span></span>
<span data-ttu-id="e55f5-144">**Start-Job** 命令启动一个运行 $c 变量中的 **Get-EventLog** 命令的后台作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-144">The **Start-Job** command starts a background job that runs the **Get-EventLog** command in the $c variable.</span></span>

<span data-ttu-id="e55f5-145">该命令使用 **Using** 作用域修饰符以指示已在本地计算机上定义 $c 变量。</span><span class="sxs-lookup"><span data-stu-id="e55f5-145">The command uses the **Using** scope modifier to indicate that the $c variable was defined on the local computer.</span></span>
<span data-ttu-id="e55f5-146">在 Windows PowerShell 3.0 中引入了 **Using** 作用域修饰符。</span><span class="sxs-lookup"><span data-stu-id="e55f5-146">The **Using** scope modifier is introduced in Windows PowerShell 3.0.</span></span>
<span data-ttu-id="e55f5-147">有关 **Using** 作用域修饰符的详细信息，请参阅 [about_Remote_Variables](about/about_Remote_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="e55f5-147">For more information about the **Using** scope modifier, see [about_Remote_Variables](about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="e55f5-148">第四个命令使用 **Invoke** 命令在会话中运行 **等待作业** 命令。</span><span class="sxs-lookup"><span data-stu-id="e55f5-148">The fourth command uses **Invoke-Command** to run a **Wait-Job** command in the sessions.</span></span>
<span data-ttu-id="e55f5-149">它使用 *Any* 参数等待，直到远程计算机上的第一个作业完成。</span><span class="sxs-lookup"><span data-stu-id="e55f5-149">It uses the *Any* parameter to wait until the first job on the remote computers is completed.</span></span>

### <span data-ttu-id="e55f5-150">示例4：设置远程计算机上的作业的等待时间</span><span class="sxs-lookup"><span data-stu-id="e55f5-150">Example 4: Set a wait time for jobs on remote computers</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
$jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
```

<span data-ttu-id="e55f5-151">此示例演示如何使用 **Wait** 的 *Timeout* 参数设置在远程计算机上运行的作业的最长等待时间。</span><span class="sxs-lookup"><span data-stu-id="e55f5-151">This example shows how to use the *Timeout* parameter of **Wait-Job** to set a maximum wait time for the jobs running on remote computers.</span></span>

<span data-ttu-id="e55f5-152">第一个命令在 (Server01、Server02 和 Server03) 的三台远程计算机上创建 **pssession** ，然后在 $s 变量中存储 **pssession** 对象。</span><span class="sxs-lookup"><span data-stu-id="e55f5-152">The first command creates a **PSSession** on each of three remote computers (Server01, Server02, and Server03), and then stores the **PSSession** objects in the $s variable.</span></span>

<span data-ttu-id="e55f5-153">第二个命令使用 **Invoke 命令** 在 $s 中的每个 **PSSession** 对象中运行 **Start-Job** 。</span><span class="sxs-lookup"><span data-stu-id="e55f5-153">The second command uses **Invoke-Command** to run **Start-Job** in each of the **PSSession** objects in $s.</span></span>
<span data-ttu-id="e55f5-154">它将生成的作业对象存储在 $jobs 的变量中。</span><span class="sxs-lookup"><span data-stu-id="e55f5-154">It stores the resulting job objects in the $jobs variable.</span></span>

<span data-ttu-id="e55f5-155">第三个命令使用 **Invoke 命令** 在 $s 中的每个会话中运行 **等待作业** 。</span><span class="sxs-lookup"><span data-stu-id="e55f5-155">The third command uses **Invoke-Command** to run **Wait-Job** in each of the sessions in $s.</span></span>
<span data-ttu-id="e55f5-156">**Wait** 命令确定所有命令是否在30秒内完成。</span><span class="sxs-lookup"><span data-stu-id="e55f5-156">The **Wait-Job** command determines whether all of the commands have completed within 30 seconds.</span></span>
<span data-ttu-id="e55f5-157">它使用值为30的 *Timeout* 参数来建立最长等待时间，然后将命令的结果存储在 $done 的变量中。</span><span class="sxs-lookup"><span data-stu-id="e55f5-157">It uses the *Timeout* parameter with a value of 30 to establish the maximum wait time, and then stores the results of the command in the $done variable.</span></span>

<span data-ttu-id="e55f5-158">在此示例中，30 秒后，只有 Server02 计算机上的命令完成。</span><span class="sxs-lookup"><span data-stu-id="e55f5-158">In this case, after 30 seconds, only the command on the Server02 computer has completed.</span></span>
<span data-ttu-id="e55f5-159">**Wait** 结束等待，显示命令提示符，并返回表示已完成作业的对象。</span><span class="sxs-lookup"><span data-stu-id="e55f5-159">**Wait-Job** ends the wait, displays the command prompt, and returns the object that represents the job that was completed.</span></span>

<span data-ttu-id="e55f5-160">$done 变量包含一个表示在 Server02 上运行的作业的作业对象。</span><span class="sxs-lookup"><span data-stu-id="e55f5-160">The $done variable contains a job object that represents the job that ran on Server02.</span></span>

### <span data-ttu-id="e55f5-161">示例5：等待多个作业中的一个完成</span><span class="sxs-lookup"><span data-stu-id="e55f5-161">Example 5: Wait until one of several jobs finishes</span></span>

```powershell
Wait-Job -id 1,2,5 -Any
```

<span data-ttu-id="e55f5-162">此命令通过 Id 标识三个作业，并等待其中任何一个作业完成。</span><span class="sxs-lookup"><span data-stu-id="e55f5-162">This command identifies three jobs by their IDs and waits until any one of them are completed.</span></span>
<span data-ttu-id="e55f5-163">当第一个作业完成时，将返回命令提示符。</span><span class="sxs-lookup"><span data-stu-id="e55f5-163">The command prompt returns when the first job finishes.</span></span>

### <span data-ttu-id="e55f5-164">示例6：等待一段时间，然后允许作业在后台继续</span><span class="sxs-lookup"><span data-stu-id="e55f5-164">Example 6: Wait for a period, then allow job to continue in background</span></span>

```powershell
Wait-Job -Name "DailyLog" -Timeout 120
```

<span data-ttu-id="e55f5-165">此命令120等待 DailyLog 作业 (两分钟) ，直到完成。</span><span class="sxs-lookup"><span data-stu-id="e55f5-165">This command waits 120 seconds (two minutes) for the DailyLog job to finish.</span></span>
<span data-ttu-id="e55f5-166">如果作业未在接下来的两分钟内完成，则命令提示符仍返回，并且作业继续在后台运行。</span><span class="sxs-lookup"><span data-stu-id="e55f5-166">If the job does not finish in the next two minutes, the command prompt returns anyway, and the job continues to run in the background.</span></span>

### <span data-ttu-id="e55f5-167">示例7：按名称等待作业</span><span class="sxs-lookup"><span data-stu-id="e55f5-167">Example 7: Wait for a job by name</span></span>

```powershell
Wait-Job -Name "Job3"
```

<span data-ttu-id="e55f5-168">此命令使用作业名称来标识要等待的作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-168">This command uses the job name to identify the job for which to wait.</span></span>

### <span data-ttu-id="e55f5-169">示例8：等待本地计算机上的作业开始 Start-Job</span><span class="sxs-lookup"><span data-stu-id="e55f5-169">Example 8: Wait for jobs on local computer started with Start-Job</span></span>

```powershell
$j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
$j | Wait-Job
```

<span data-ttu-id="e55f5-170">此示例演示如何通过使用 " **启动-作业** " 将 **Wait** cmdlet 用于本地计算机上启动的作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-170">This example shows how to use the **Wait-Job** cmdlet with jobs started on the local computer by using **Start-Job** .</span></span>

<span data-ttu-id="e55f5-171">这些命令启动一个可获取在上一周添加或更新的 PowerShell 脚本文件的作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-171">These commands start a job that gets the PowerShell script files that were added or updated in the last week.</span></span>

<span data-ttu-id="e55f5-172">第一个命令使用 **start-job** 在本地计算机上启动后台作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-172">The first command uses **Start-Job** to start a background job on the local computer.</span></span>
<span data-ttu-id="e55f5-173">作业运行 Get-ChildItem 命令，该命令获取在上周添加或更新的文件扩展名为 ps1 的所有文件。</span><span class="sxs-lookup"><span data-stu-id="e55f5-173">The job runs a Get-ChildItem command that gets all of the files that have a .ps1 file name extension that were added or updated in the last week.</span></span>

<span data-ttu-id="e55f5-174">第三个命令使用 **wait** 等待等待作业完成。</span><span class="sxs-lookup"><span data-stu-id="e55f5-174">The third command uses **Wait-Job** to wait until the job is completed.</span></span>
<span data-ttu-id="e55f5-175">作业完成后，该命令将显示作业对象，该对象包含有关作业的信息。</span><span class="sxs-lookup"><span data-stu-id="e55f5-175">When the job finishes, the command displays the job object, which contains information about the job.</span></span>

### <span data-ttu-id="e55f5-176">示例9：使用 Invoke-Command 等待远程计算机上启动的作业</span><span class="sxs-lookup"><span data-stu-id="e55f5-176">Example 9: Wait for jobs started on remote computers by using Invoke-Command</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
$j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
$j | Wait-Job
```

<span data-ttu-id="e55f5-177">此示例演示如何通过使用 **命令调用-Command** 的 *AsJob* 参数，将 **等待作业** 与远程计算机上启动的作业一起使用。</span><span class="sxs-lookup"><span data-stu-id="e55f5-177">This example shows how to use **Wait-Job** with jobs started on remote computers by using the *AsJob* parameter of **Invoke-Command** .</span></span>
<span data-ttu-id="e55f5-178">使用 *AsJob* 时，将在本地计算机上创建作业，并自动将结果返回到本地计算机，即使作业运行在远程计算机上也是如此。</span><span class="sxs-lookup"><span data-stu-id="e55f5-178">When using *AsJob* , the job is created on the local computer and the results are automatically returned to the local computer, even though the job runs on the remote computers.</span></span>

<span data-ttu-id="e55f5-179">此示例使用 **Wait** 来确定是否完成了三台远程计算机上的会话中运行的 **进程** 内命令。</span><span class="sxs-lookup"><span data-stu-id="e55f5-179">This example uses **Wait-Job** to determine whether a **Get-Process** command running in the sessions on three remote computers is completed.</span></span>

<span data-ttu-id="e55f5-180">第一个命令在三台计算机上创建 **PSSession** 对象，并将它们存储在 $s 变量中。</span><span class="sxs-lookup"><span data-stu-id="e55f5-180">The first command creates **PSSession** objects on three computers and stores them in the $s variable.</span></span>

<span data-ttu-id="e55f5-181">第二个命令使用 **Invoke 命令** 在 $s 中的三个会话中的每个会话中运行 **Get 进程** 。</span><span class="sxs-lookup"><span data-stu-id="e55f5-181">The second command uses **Invoke-Command** to run **Get-Process** in each of the three sessions in $s.</span></span>
<span data-ttu-id="e55f5-182">该命令使用 *AsJob* 参数将命令作为后台作业异步运行。</span><span class="sxs-lookup"><span data-stu-id="e55f5-182">The command uses the *AsJob* parameter to run the command asynchronously as a background job.</span></span>
<span data-ttu-id="e55f5-183">该命令返回一个作业对象，就像使用 **Start-job** 启动的作业一样，该作业对象存储在 $j 的变量中。</span><span class="sxs-lookup"><span data-stu-id="e55f5-183">The command returns a job object, just like the jobs started by using **Start-Job** , and the job object is stored in the $j variable.</span></span>

<span data-ttu-id="e55f5-184">第三个命令使用管道运算符 (|) 将 $j 中的作业对象发送到 **Wait** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e55f5-184">The third command uses a pipeline operator (|) to send the job object in $j to the **Wait-Job** cmdlet.</span></span>
<span data-ttu-id="e55f5-185">在这种情况下，不需要 **调用命令** 命令，因为作业驻留在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="e55f5-185">An **Invoke-Command** command is not required in this case, because the job resides on the local computer.</span></span>

### <span data-ttu-id="e55f5-186">示例10：等待 ID 为的作业</span><span class="sxs-lookup"><span data-stu-id="e55f5-186">Example 10: Wait for a job that has an ID</span></span>

```powershell
Get-Job
```

```Output
Id   Name     State      HasMoreData     Location             Command
--   ----     -----      -----------     --------             -------
1    Job1     Completed  True            localhost,Server01.. get-service
4    Job4     Completed  True            localhost            dir | where
```

```powershell
Wait-Job -Id 1
```

<span data-ttu-id="e55f5-187">此命令等待 ID 值为 1 的作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-187">This command waits for the job with an ID value of 1.</span></span>

## <span data-ttu-id="e55f5-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e55f5-188">PARAMETERS</span></span>

### <span data-ttu-id="e55f5-189">-Any</span><span class="sxs-lookup"><span data-stu-id="e55f5-189">-Any</span></span>

<span data-ttu-id="e55f5-190">指示此 cmdlet 显示命令提示符，并在任何作业完成时返回作业对象。</span><span class="sxs-lookup"><span data-stu-id="e55f5-190">Indicates that this cmdlet displays the command prompt, and returns the job object, when any job finishes.</span></span>
<span data-ttu-id="e55f5-191">默认情况下， **等待作业** 将等待，直到所有指定的作业都完成后才显示提示。</span><span class="sxs-lookup"><span data-stu-id="e55f5-191">By default, **Wait-Job** waits until all of the specified jobs are complete before it displays the prompt.</span></span>

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

### <span data-ttu-id="e55f5-192">-Filter</span><span class="sxs-lookup"><span data-stu-id="e55f5-192">-Filter</span></span>

<span data-ttu-id="e55f5-193">指定条件的哈希表。</span><span class="sxs-lookup"><span data-stu-id="e55f5-193">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="e55f5-194">此 cmdlet 将等待满足哈希表中所有条件的作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-194">This cmdlet waits for jobs that satisfy all of the conditions in the hash table.</span></span>
<span data-ttu-id="e55f5-195">输入一个哈希表，其中的键为作业属性，其中的值为作业属性值。</span><span class="sxs-lookup"><span data-stu-id="e55f5-195">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="e55f5-196">此参数仅适用于自定义作业类型，例如工作流作业和计划作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-196">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="e55f5-197">它不适用于标准后台作业，如使用 **Start-Job** cmdlet 创建的作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-197">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="e55f5-198">有关支持此参数的信息，请参阅作业类型的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e55f5-198">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="e55f5-199">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="e55f5-199">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e55f5-200">-Force</span><span class="sxs-lookup"><span data-stu-id="e55f5-200">-Force</span></span>

<span data-ttu-id="e55f5-201">指示此 cmdlet 继续等待处于 "挂起" 或 "已断开连接" 状态的作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-201">Indicates that this cmdlet continues to wait for jobs in the Suspended or Disconnected state.</span></span>
<span data-ttu-id="e55f5-202">默认情况下，当作业处于以下状态之一时， **等待作业** 返回或结束等待：</span><span class="sxs-lookup"><span data-stu-id="e55f5-202">By default, **Wait-Job** returns, or ends  the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="e55f5-203">已完成</span><span class="sxs-lookup"><span data-stu-id="e55f5-203">Completed</span></span>
- <span data-ttu-id="e55f5-204">已失败</span><span class="sxs-lookup"><span data-stu-id="e55f5-204">Failed</span></span>
- <span data-ttu-id="e55f5-205">已停止</span><span class="sxs-lookup"><span data-stu-id="e55f5-205">Stopped</span></span>
- <span data-ttu-id="e55f5-206">Suspended</span><span class="sxs-lookup"><span data-stu-id="e55f5-206">Suspended</span></span>
- <span data-ttu-id="e55f5-207">已断开连接</span><span class="sxs-lookup"><span data-stu-id="e55f5-207">Disconnected</span></span>

<span data-ttu-id="e55f5-208">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="e55f5-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="e55f5-209">-Id</span><span class="sxs-lookup"><span data-stu-id="e55f5-209">-Id</span></span>

<span data-ttu-id="e55f5-210">指定此 cmdlet 等待的作业的 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="e55f5-210">Specifies an array of IDs of jobs for which this cmdlet waits.</span></span>

<span data-ttu-id="e55f5-211">ID 是一个整数，用于唯一标识当前会话中的作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-211">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="e55f5-212">它比实例 ID 更容易记住和键入，但它仅在当前会话中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e55f5-212">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="e55f5-213">你可以键入一个或多个 Id （以逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="e55f5-213">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="e55f5-214">若要查找作业的 ID，请键入 `Get-Job` 。</span><span class="sxs-lookup"><span data-stu-id="e55f5-214">To find the ID of a job, type `Get-Job`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e55f5-215">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="e55f5-215">-InstanceId</span></span>

<span data-ttu-id="e55f5-216">指定此 cmdlet 等待的作业的实例 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="e55f5-216">Specifies an array of instance IDs of jobs for which this cmdlet waits.</span></span>
<span data-ttu-id="e55f5-217">默认值为所有作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-217">The default is all jobs.</span></span>

<span data-ttu-id="e55f5-218">实例 ID 是一个 GUID，用于在计算机上唯一标识作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-218">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="e55f5-219">若要查找作业的实例 ID，请使用 **Get-Job** 。</span><span class="sxs-lookup"><span data-stu-id="e55f5-219">To find the instance ID of a job, use **Get-Job** .</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e55f5-220">-Job</span><span class="sxs-lookup"><span data-stu-id="e55f5-220">-Job</span></span>

<span data-ttu-id="e55f5-221">指定此 cmdlet 要等待的作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-221">Specifies the jobs for which this cmdlet waits.</span></span>
<span data-ttu-id="e55f5-222">输入一个包含作业对象的变量或可获取作业对象的命令。</span><span class="sxs-lookup"><span data-stu-id="e55f5-222">Enter a variable that contains the job objects or a command that gets the job objects.</span></span>
<span data-ttu-id="e55f5-223">你还可以使用管道运算符将作业对象发送到 **Wait** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e55f5-223">You can also use a pipeline operator to send job objects to the **Wait-Job** cmdlet.</span></span>
<span data-ttu-id="e55f5-224">默认情况下， **等待** 时间等待在当前会话中创建的所有作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-224">By default, **Wait-Job** waits for all jobs created in the current session.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e55f5-225">-Name</span><span class="sxs-lookup"><span data-stu-id="e55f5-225">-Name</span></span>

<span data-ttu-id="e55f5-226">指定此 cmdlet 等待的作业的友好名称。</span><span class="sxs-lookup"><span data-stu-id="e55f5-226">Specifies friendly names of jobs for which this cmdlet waits.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e55f5-227">-State</span><span class="sxs-lookup"><span data-stu-id="e55f5-227">-State</span></span>

<span data-ttu-id="e55f5-228">指定作业状态。</span><span class="sxs-lookup"><span data-stu-id="e55f5-228">Specifies a job state.</span></span>
<span data-ttu-id="e55f5-229">此 cmdlet 仅等待处于指定状态的作业。</span><span class="sxs-lookup"><span data-stu-id="e55f5-229">This cmdlet waits only for jobs in the specified state.</span></span>
<span data-ttu-id="e55f5-230">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="e55f5-230">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e55f5-231">NotStarted</span><span class="sxs-lookup"><span data-stu-id="e55f5-231">NotStarted</span></span>
- <span data-ttu-id="e55f5-232">正在运行</span><span class="sxs-lookup"><span data-stu-id="e55f5-232">Running</span></span>
- <span data-ttu-id="e55f5-233">已完成</span><span class="sxs-lookup"><span data-stu-id="e55f5-233">Completed</span></span>
- <span data-ttu-id="e55f5-234">已失败</span><span class="sxs-lookup"><span data-stu-id="e55f5-234">Failed</span></span>
- <span data-ttu-id="e55f5-235">已停止</span><span class="sxs-lookup"><span data-stu-id="e55f5-235">Stopped</span></span>
- <span data-ttu-id="e55f5-236">已阻止</span><span class="sxs-lookup"><span data-stu-id="e55f5-236">Blocked</span></span>
- <span data-ttu-id="e55f5-237">Suspended</span><span class="sxs-lookup"><span data-stu-id="e55f5-237">Suspended</span></span>
- <span data-ttu-id="e55f5-238">已断开连接</span><span class="sxs-lookup"><span data-stu-id="e55f5-238">Disconnected</span></span>
- <span data-ttu-id="e55f5-239">正在暂停</span><span class="sxs-lookup"><span data-stu-id="e55f5-239">Suspending</span></span>
- <span data-ttu-id="e55f5-240">正在停止</span><span class="sxs-lookup"><span data-stu-id="e55f5-240">Stopping</span></span>

<span data-ttu-id="e55f5-241">有关作业状态的详细信息，请参阅 MSDN 库中的 [JobState 枚举](https://msdn.microsoft.com/library/system.management.automation.jobstate) 。</span><span class="sxs-lookup"><span data-stu-id="e55f5-241">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e55f5-242">-Timeout</span><span class="sxs-lookup"><span data-stu-id="e55f5-242">-Timeout</span></span>

<span data-ttu-id="e55f5-243">指定每个后台作业的最长等待时间（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e55f5-243">Specifies the maximum wait time for each background job, in seconds.</span></span>
<span data-ttu-id="e55f5-244">默认值为-1，指示该 cmdlet 将等待直到作业完成。</span><span class="sxs-lookup"><span data-stu-id="e55f5-244">The default value, -1, indicates that the cmdlet waits until the job finishes.</span></span>
<span data-ttu-id="e55f5-245">当你提交 **等待作业** 命令时，将开始计时，而不是 **启动作业** 命令。</span><span class="sxs-lookup"><span data-stu-id="e55f5-245">The timing starts when you submit the **Wait-Job** command, not the **Start-Job** command.</span></span>

<span data-ttu-id="e55f5-246">如果超过此时间，则等待结束，并返回命令提示符，即使作业仍在运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="e55f5-246">If this time is exceeded, the wait ends and the command prompt returns, even if the job is still running.</span></span>
<span data-ttu-id="e55f5-247">此命令不会显示任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="e55f5-247">The command does not display any error message.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e55f5-248">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e55f5-248">CommonParameters</span></span>

<span data-ttu-id="e55f5-249">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e55f5-249">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e55f5-250">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e55f5-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e55f5-251">输入</span><span class="sxs-lookup"><span data-stu-id="e55f5-251">INPUTS</span></span>

### <span data-ttu-id="e55f5-252">System.Management.Automation.RemotingJob</span><span class="sxs-lookup"><span data-stu-id="e55f5-252">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="e55f5-253">可以通过管道将作业对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e55f5-253">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="e55f5-254">输出</span><span class="sxs-lookup"><span data-stu-id="e55f5-254">OUTPUTS</span></span>

### <span data-ttu-id="e55f5-255">System.Management.Automation.PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="e55f5-255">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="e55f5-256">此 cmdlet 将返回表示已完成作业的作业对象。</span><span class="sxs-lookup"><span data-stu-id="e55f5-256">This cmdlet returns job objects that represent the completed jobs.</span></span>
<span data-ttu-id="e55f5-257">如果由于超过 *Timeout* 参数的值而导致等待结束，则 **等待作业** 不返回任何对象。</span><span class="sxs-lookup"><span data-stu-id="e55f5-257">If the wait ends because the value of the *Timeout* parameter is exceeded, **Wait-Job** does not return any objects.</span></span>

## <span data-ttu-id="e55f5-258">注释</span><span class="sxs-lookup"><span data-stu-id="e55f5-258">NOTES</span></span>

* <span data-ttu-id="e55f5-259">默认情况下，当作业处于以下状态之一时， **等待作业** 返回或结束等待：</span><span class="sxs-lookup"><span data-stu-id="e55f5-259">By default, **Wait-Job** returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="e55f5-260">已完成</span><span class="sxs-lookup"><span data-stu-id="e55f5-260">Completed</span></span>
- <span data-ttu-id="e55f5-261">已失败</span><span class="sxs-lookup"><span data-stu-id="e55f5-261">Failed</span></span>
- <span data-ttu-id="e55f5-262">已停止</span><span class="sxs-lookup"><span data-stu-id="e55f5-262">Stopped</span></span>
- <span data-ttu-id="e55f5-263">已挂起</span><span class="sxs-lookup"><span data-stu-id="e55f5-263">Suspended</span></span>
- <span data-ttu-id="e55f5-264">断开连接以继续等待挂起和断开 **连接的作业** ，请使用 *Force* 参数。</span><span class="sxs-lookup"><span data-stu-id="e55f5-264">Disconnected To direct **Wait-Job** to continue to wait for Suspended and Disconnected jobs, use the *Force* parameter.</span></span>

## <span data-ttu-id="e55f5-265">相关链接</span><span class="sxs-lookup"><span data-stu-id="e55f5-265">RELATED LINKS</span></span>

[<span data-ttu-id="e55f5-266">Get-Job</span><span class="sxs-lookup"><span data-stu-id="e55f5-266">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="e55f5-267">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="e55f5-267">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="e55f5-268">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="e55f5-268">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="e55f5-269">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="e55f5-269">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="e55f5-270">Start-Job</span><span class="sxs-lookup"><span data-stu-id="e55f5-270">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="e55f5-271">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="e55f5-271">Stop-Job</span></span>](Stop-Job.md)

