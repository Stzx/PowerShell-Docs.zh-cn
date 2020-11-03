---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/register-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ScheduledJob
ms.openlocfilehash: 89887474142490a71d372577576fb0059b4ff12e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197784"
---
# <span data-ttu-id="3104f-103">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3104f-103">Register-ScheduledJob</span></span>

## <span data-ttu-id="3104f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3104f-104">SYNOPSIS</span></span>
<span data-ttu-id="3104f-105">创建计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-105">Creates a scheduled job.</span></span>

## <span data-ttu-id="3104f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3104f-106">SYNTAX</span></span>

### <span data-ttu-id="3104f-107">ScriptBlock（默认值）</span><span class="sxs-lookup"><span data-stu-id="3104f-107">ScriptBlock (Default)</span></span>

```
Register-ScheduledJob [-ScriptBlock] <ScriptBlock> [-Name] <String>
 [-Trigger <ScheduledJobTrigger[]>] [-InitializationScript <ScriptBlock>] [-RunAs32]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-ScheduledJobOption <ScheduledJobOptions>] [-ArgumentList <Object[]>] [-MaxResultCount <Int32>]
 [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3104f-108">文件路径</span><span class="sxs-lookup"><span data-stu-id="3104f-108">FilePath</span></span>

```
Register-ScheduledJob [-FilePath] <String> [-Name] <String> [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-ArgumentList <Object[]>] [-MaxResultCount <Int32>] [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3104f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3104f-109">DESCRIPTION</span></span>

<span data-ttu-id="3104f-110">`Register-ScheduledJob`Cmdlet 在本地计算机上创建计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-110">The `Register-ScheduledJob` cmdlet creates scheduled jobs on the local computer.</span></span>

<span data-ttu-id="3104f-111">计划作业是 Windows PowerShell 后台作业，可以按一次性或重复计划自动启动。</span><span class="sxs-lookup"><span data-stu-id="3104f-111">A scheduled job is a Windows PowerShell background job that can be started automatically on a one-time or recurring schedule.</span></span> <span data-ttu-id="3104f-112">计划作业存储在磁盘上并在任务计划程序中注册。</span><span class="sxs-lookup"><span data-stu-id="3104f-112">Scheduled jobs are stored on disk and registered in Task Scheduler.</span></span>
<span data-ttu-id="3104f-113">可以在任务计划程序中或使用 Windows PowerShell 中的计划作业 cmdlet 来管理作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-113">The jobs can be managed in Task Scheduler or by using the Scheduled Job cmdlets in Windows PowerShell.</span></span>

<span data-ttu-id="3104f-114">当计划作业启动时，它会创建计划作业的实例。</span><span class="sxs-lookup"><span data-stu-id="3104f-114">When a scheduled job starts, it creates an instance of the scheduled job.</span></span> <span data-ttu-id="3104f-115">除了结果保存在磁盘上以外，计划作业实例与 Windows PowerShell 后台作业相同。</span><span class="sxs-lookup"><span data-stu-id="3104f-115">Scheduled job instances are identical to Windows PowerShell background jobs, except that the results are saved on disk.</span></span> <span data-ttu-id="3104f-116">使用作业 cmdlet （如 `Start-Job` 、和） `Get-Job` `Receive-Job` 来启动、查看和获取作业实例的结果。</span><span class="sxs-lookup"><span data-stu-id="3104f-116">Use the Job cmdlets, such as `Start-Job`, `Get-Job`, and `Receive-Job` to start, view, and get the results of the job instances.</span></span>

<span data-ttu-id="3104f-117">使用 `Register-ScheduledJob` 创建新的计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-117">Use `Register-ScheduledJob` to create a new scheduled job.</span></span> <span data-ttu-id="3104f-118">若要指定计划作业运行的命令，请使用 **ScriptBlock** 参数。</span><span class="sxs-lookup"><span data-stu-id="3104f-118">To specify the commands that the scheduled job runs, use the **ScriptBlock** parameter.</span></span> <span data-ttu-id="3104f-119">若要指定作业运行的脚本，请使用 **FilePath** 参数。</span><span class="sxs-lookup"><span data-stu-id="3104f-119">To specify a script that the job runs, use the **FilePath** parameter.</span></span>

<span data-ttu-id="3104f-120">Windows PowerShell 计划作业使用与任务计划程序用于计划任务相同的作业触发器和作业选项。</span><span class="sxs-lookup"><span data-stu-id="3104f-120">Windows PowerShell-scheduled jobs use the same job triggers and job options that Task Scheduler uses for scheduled tasks.</span></span>

<span data-ttu-id="3104f-121">的 **Trigger** 参数 `Register-ScheduledJob` 可添加一个或多个启动作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="3104f-121">The **Trigger** parameter of `Register-ScheduledJob` adds one or more job triggers that start the job.</span></span> <span data-ttu-id="3104f-122">**Trigger** 参数是可选的，因此你可以在创建计划作业时添加触发器，稍后添加作业触发器，添加 **RunNow** 参数以立即启动作业，使用 `Start-Job` cmdlet 立即启动作业，或将存计划作业保存为其他作业的模板。</span><span class="sxs-lookup"><span data-stu-id="3104f-122">The **Trigger** parameter is optional, so you can add triggers when you create the scheduled job, add job triggers later, add the **RunNow** parameter to start the job immediately, use the `Start-Job` cmdlet to start the job immediately at any time, or save the untriggered scheduled job as a template for other jobs.</span></span>

<span data-ttu-id="3104f-123">使用 **Options** 参数可自定义计划作业的选项设置。</span><span class="sxs-lookup"><span data-stu-id="3104f-123">The **Options** parameter lets you customize the options settings for the scheduled job.</span></span> <span data-ttu-id="3104f-124">**选项** 参数是可选的，因此你可以在创建计划作业时设置作业选项，或者随时对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="3104f-124">The **Options** parameter is optional, so you can set job options when you create the scheduled job or change them at any time.</span></span> <span data-ttu-id="3104f-125">由于作业选项设置可能会阻止计划作业运行，因此需检查作业选项并小心设置它们。</span><span class="sxs-lookup"><span data-stu-id="3104f-125">Because job option settings can prevent the scheduled job from running, review the job options and set them carefully.</span></span>

<span data-ttu-id="3104f-126">`Register-ScheduledJob` 是包含在 Windows PowerShell 中的 **PSScheduledJob** 模块中的作业计划 cmdlet 集合之一。</span><span class="sxs-lookup"><span data-stu-id="3104f-126">`Register-ScheduledJob` is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="3104f-127">有关计划作业的详细信息，请参阅 **PSScheduledJob** 模块中的相关文章。</span><span class="sxs-lookup"><span data-stu-id="3104f-127">For more information about Scheduled Jobs, see the About articles in the **PSScheduledJob** module.</span></span>
<span data-ttu-id="3104f-128">导入 **PSScheduledJob** 模块，然后键入： `Get-Help about_Scheduled*` 或查看 [about_Scheduled_Jobs](./about/about_scheduled_jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="3104f-128">Import the **PSScheduledJob** module and then type: `Get-Help about_Scheduled*` or see [about_Scheduled_Jobs](./about/about_scheduled_jobs.md).</span></span>

<span data-ttu-id="3104f-129">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="3104f-129">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="3104f-130">示例</span><span class="sxs-lookup"><span data-stu-id="3104f-130">EXAMPLES</span></span>

### <span data-ttu-id="3104f-131">示例1：创建计划作业</span><span class="sxs-lookup"><span data-stu-id="3104f-131">Example 1: Create a scheduled job</span></span>

<span data-ttu-id="3104f-132">此示例在本地计算机上创建计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-132">This example creates a scheduled job on the local computer.</span></span>

```powershell
Register-ScheduledJob -Name "Archive-Scripts" -ScriptBlock {
  Get-ChildItem $home\*.ps1 -Recurse |
    Copy-Item -Destination "\\Server\Share\PSScriptArchive"
}
```

<span data-ttu-id="3104f-133">`Register-ScheduledJob` 使用 **Name** 参数来创建 **存档脚本** 的计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-133">`Register-ScheduledJob` uses the **Name** parameter to create the **Archive-Scripts** scheduled job.</span></span>
<span data-ttu-id="3104f-134">**ScriptBlock** 参数运行 `Get-ChildItem` ，以 `$home` 递归方式搜索目录中的 `.ps1` 文件。</span><span class="sxs-lookup"><span data-stu-id="3104f-134">The **ScriptBlock** parameter runs `Get-ChildItem` that searches the `$home` directory recursively for `.ps1` files.</span></span> <span data-ttu-id="3104f-135">`Copy-Item`Cmdlet 将文件复制到由 **Destination** 参数指定的目录中。</span><span class="sxs-lookup"><span data-stu-id="3104f-135">The `Copy-Item` cmdlet copies the files to a directory specified by the **Destination** parameter.</span></span>

<span data-ttu-id="3104f-136">因为计划作业不包含触发器，所以它不会自动启动。</span><span class="sxs-lookup"><span data-stu-id="3104f-136">Because the scheduled job doesn't contain a trigger, it's not started automatically.</span></span> <span data-ttu-id="3104f-137">你可以使用添加作业触发器 `Add-JobTrigger` ，使用 `Start-Job` cmdlet 按需启动作业，或使用计划作业作为其他计划作业的模板。</span><span class="sxs-lookup"><span data-stu-id="3104f-137">You can add job triggers with `Add-JobTrigger`, use the `Start-Job` cmdlet to start the job on demand, or use the scheduled job as a template for other scheduled jobs.</span></span>

### <span data-ttu-id="3104f-138">示例2：使用触发器和自定义选项创建计划作业</span><span class="sxs-lookup"><span data-stu-id="3104f-138">Example 2: Create a scheduled job with triggers and custom options</span></span>

<span data-ttu-id="3104f-139">此示例显示了如何创建具有作业触发器和自定义作业选项的计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-139">This example shows how to create a scheduled job that has a job trigger and custom job options.</span></span>

```powershell
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
$path = "\\Srv01\Scripts\UpdateVersion.ps1"
Register-ScheduledJob -Name "UpdateVersion" -FilePath $path -ScheduledJobOption $O -Trigger $T
```

<span data-ttu-id="3104f-140">`$O`变量存储 cmdlet 创建的作业选项对象 `New-ScheduledJobOption` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-140">The `$O` variable stores the job option object that the `New-ScheduledJobOption` cmdlet created.</span></span> <span data-ttu-id="3104f-141">选项将启动计划作业，即使计算机未处于空闲状态，也会唤醒计算机以运行作业（如有必要），并允许作业的多个实例在一个序列中运行。</span><span class="sxs-lookup"><span data-stu-id="3104f-141">The options start the scheduled job even if the computer isn't idle, wakes the computer to run the job, if necessary, and allows multiple instances of the job to run in a series.</span></span>

<span data-ttu-id="3104f-142">`$T`变量存储 cmdlet 的结果， `New-JobTrigger` 用于创建作业触发器，该触发器在每个星期一的下午9:00 开始作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-142">The `$T` variable stores the result from the `New-JobTrigger` cmdlet to create job trigger that starts a job every other Monday at 9:00 PM.</span></span>

<span data-ttu-id="3104f-143">`$path`变量存储 `UpdateVersion.ps1` 脚本文件的路径。</span><span class="sxs-lookup"><span data-stu-id="3104f-143">The `$path` variable stores the path to the `UpdateVersion.ps1` script file.</span></span>

<span data-ttu-id="3104f-144">`Register-ScheduledJob` 使用 **Name** 参数创建 **UpdateVersion** 计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-144">`Register-ScheduledJob` uses the **Name** paramter to create the **UpdateVersion** scheduled job.</span></span>
<span data-ttu-id="3104f-145">**FilePath** 参数用于 `$path` 指定作业运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="3104f-145">The **FilePath** parameter uses `$path` to specify the script that the job runs.</span></span> <span data-ttu-id="3104f-146">**Get-scheduledjoboption** 参数使用中存储的作业选项 `$O` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-146">The **ScheduledJobOption** parameter uses the job options stored in `$O`.</span></span> <span data-ttu-id="3104f-147">**Trigger** 参数使用存储在中的作业触发器 `$T` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-147">The **Trigger** parameter uses the job triggers stored in `$T`.</span></span>

### <span data-ttu-id="3104f-148">示例3：使用哈希表指定触发器和计划作业选项</span><span class="sxs-lookup"><span data-stu-id="3104f-148">Example 3: Use hash tables to specify a trigger and scheduled job options</span></span>

<span data-ttu-id="3104f-149">此示例与示例2中的命令具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="3104f-149">This example has the same effect as the command in Example 2.</span></span> <span data-ttu-id="3104f-150">它将创建一个计划作业，使用哈希表指定 **Trigger** 和 **get-scheduledjoboption** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="3104f-150">It creates a scheduled job, using hash tables to specify the values of the **Trigger** and **ScheduledJobOption** parameters.</span></span> <span data-ttu-id="3104f-151">`$O` `$T` 在示例2中定义的和变量将替换为哈希表。</span><span class="sxs-lookup"><span data-stu-id="3104f-151">The `$O` and `$T`variables defined in Example 2 are replaced with hash tables.</span></span>

```powershell
$T = @{
  Frequency="Weekly"
  At="9:00PM"
  DaysOfWeek="Monday"
  Interval=2
}
$O = @{
  WakeToRun=$true
  StartIfNotIdle=$false
  MultipleInstancePolicy="Queue"
}
Register-ScheduledJob -Trigger $T -ScheduledJobOption $O -Name UpdateVersion -FilePath "\\Srv01\Scripts\Update-Version.ps1"
```

### <span data-ttu-id="3104f-152">示例4：在远程计算机上创建计划作业</span><span class="sxs-lookup"><span data-stu-id="3104f-152">Example 4: Create scheduled jobs on remote computers</span></span>

<span data-ttu-id="3104f-153">在此示例中，将在多台远程计算机上创建 **energydata.ps1** 计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-153">In this example, the **EnergyData** scheduled job is created on multiple remote computers.</span></span> <span data-ttu-id="3104f-154">计划的作业运行一个脚本，该脚本收集原始数据并将其保存在远程计算机上运行的日志中。</span><span class="sxs-lookup"><span data-stu-id="3104f-154">The scheduled job runs a script that gathers raw data and saves it in a running log on the remote computer.</span></span>

```powershell
$Cred = Get-Credential
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Invoke-Command -ComputerName (Get-Content Servers.txt) -Credential $Cred -ScriptBlock {
  $params = @{
      Name = "Get-EnergyData"
      FilePath = "\\Srv01\Scripts\Get-EnergyData.ps1"
      ScheduledJobOption = $using:O
      Trigger = $using:T
  }
  Register-ScheduledJob @params
}
```

<span data-ttu-id="3104f-155">`$Cred`变量为有权创建计划作业的用户在 **PSCredential** 对象中存储凭据。</span><span class="sxs-lookup"><span data-stu-id="3104f-155">The `$Cred` variable stores credentials in a **PSCredential** object for a user with permissions to create scheduled jobs.</span></span> <span data-ttu-id="3104f-156">`$O`变量存储用创建的作业选项 `New-ScheduledJobOption` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-156">The `$O` variable stores the job options created with `New-ScheduledJobOption`.</span></span> <span data-ttu-id="3104f-157">`$T`变量存储用创建的作业触发器 `New-JobTrigger` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-157">The `$T` variable stores the job triggers created with `New-JobTrigger`.</span></span>

<span data-ttu-id="3104f-158">该 `Invoke-Command` cmdlet 使用 **ComputerName** 参数从文件获取服务器名称的列表 `Servers.txt` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-158">The `Invoke-Command` cmdlet uses the **ComputerName** parameter to get a list of server names from the `Servers.txt` file.</span></span> <span data-ttu-id="3104f-159">**Credential** 参数获取存储在中的凭据对象 `$Cred` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-159">The **Credential** parameter gets the credential object stored in `$Cred`.</span></span>
<span data-ttu-id="3104f-160">**ScriptBlock** 参数在 `Register-ScheduledJob` 文件中的计算机上运行命令 `Servers.txt` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-160">The **ScriptBlock** parameter runs a `Register-ScheduledJob` command on the computers in the `Servers.txt` file.</span></span>

<span data-ttu-id="3104f-161">的参数 `Register-ScheduledJob` 由定义 `$params` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-161">The parameters for `Register-ScheduledJob` are defined by `$params`.</span></span> <span data-ttu-id="3104f-162">**Name** 参数指定作业在每台远程计算机上都命名为 **energydata.ps1** 。</span><span class="sxs-lookup"><span data-stu-id="3104f-162">The **Name** parameters specifies the job is named **Get-EnergyData** on each remote computer.</span></span> <span data-ttu-id="3104f-163">**FilePath** 提供脚本的位置 `EnergyData.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-163">**FilePath** provides the location of the `EnergyData.ps1` script.</span></span> <span data-ttu-id="3104f-164">该脚本位于可用于所有参与的计算机的文件服务器上。作业按照中的作业触发器指定的计划运行 `$T` ，并在中运行作业选项 `$O` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-164">The script is located on a file server that is available to all participating computers.The job runs on the schedule specified by the job triggers in `$T` and the job options in `$O`.</span></span>

<span data-ttu-id="3104f-165">`Register-ScheduledJob @params`命令用脚本块中的参数创建计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-165">The `Register-ScheduledJob @params` command creates the scheduled job with the parameters from the script block.</span></span>

### <span data-ttu-id="3104f-166">示例5：创建在远程计算机上运行脚本的计划作业</span><span class="sxs-lookup"><span data-stu-id="3104f-166">Example 5: Create a scheduled job that runs a script on remote computers</span></span>

<span data-ttu-id="3104f-167">此示例在本地计算机上创建 **CollectEnergyData** 计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-167">This example creates the **CollectEnergyData** scheduled job on the local computer.</span></span> <span data-ttu-id="3104f-168">作业在多台远程计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="3104f-168">The job runs on multiple remote computers.</span></span>

```powershell
$Admin = Get-Credential
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Register-ScheduledJob -Name "CollectEnergyData" -Trigger $T -MaxResultCount 99 -ScriptBlock {
  $params = @{
    AsJob = $true
    ComputerName = (Get-Content Servers.txt)
    FilePath = '\\Srv01\Scripts\Get-EnergyData.ps1'
    Credential = $using:Admin
    Authentication = 'CredSSP'
  }
  Invoke-Command @params
}
```

<span data-ttu-id="3104f-169">`$Admin`变量为有权在 **PSCredential** 对象中运行命令的用户存储凭据。</span><span class="sxs-lookup"><span data-stu-id="3104f-169">The `$Admin` variable stores credentials for a user with permissions to run the commands in a **PSCredential** object.</span></span> <span data-ttu-id="3104f-170">`$T`变量存储用创建的作业触发器 `New-JobTrigger` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-170">The `$T` variable stores the job triggers created with `New-JobTrigger`.</span></span>

<span data-ttu-id="3104f-171">`Register-ScheduledJob`Cmdlet 使用 **Name** 参数在本地计算机上创建 **CollectEnergyData** 计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-171">The `Register-ScheduledJob` cmdlet uses the **Name** parameter to create the **CollectEnergyData** scheduled job on the local computer.</span></span> <span data-ttu-id="3104f-172">**Trigger** 参数指定中的作业触发器 `$T` ， **MaxResultCount** 参数会将保存的结果数增加到99。</span><span class="sxs-lookup"><span data-stu-id="3104f-172">The **Trigger** parameter specifies the job triggers in `$T` and the **MaxResultCount** parameter increases the number of saved results to 99.</span></span>

<span data-ttu-id="3104f-173">**ScriptBlock** 参数定义 `Invoke-Command` 参数 `$params` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-173">The **ScriptBlock** parameter defines the `Invoke-Command` parameters with `$params`.</span></span> <span data-ttu-id="3104f-174">**AsJob** 参数在本地计算机上创建后台作业对象，即使该 `Energydata.ps1` 脚本在远程计算机上运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="3104f-174">The **AsJob** parameter creates the background job object on the local computer, even though the `Energydata.ps1` script runs on the remote computers.</span></span> <span data-ttu-id="3104f-175">**ComputerName** 参数从文件中获取服务器名称的列表 `Servers.txt` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-175">The **ComputerName** parameter gets a list of server names from the `Servers.txt` file.</span></span> <span data-ttu-id="3104f-176">**Credential** 参数指定有权在远程计算机上运行脚本的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3104f-176">The **Credential** parameter specifies a user account that has permission to run scripts on the remote computers.</span></span> <span data-ttu-id="3104f-177">**身份验证** 参数将值 **CredSSP** 指定为允许委托凭据。</span><span class="sxs-lookup"><span data-stu-id="3104f-177">And, the **Authentication** parameter specifies a value of **CredSSP** to allow delegated credentials.</span></span>

<span data-ttu-id="3104f-178">`Invoke-Command @params`用脚本块中的参数运行命令。</span><span class="sxs-lookup"><span data-stu-id="3104f-178">The `Invoke-Command @params` runs the command with the parameters from the script block.</span></span>

## <span data-ttu-id="3104f-179">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3104f-179">PARAMETERS</span></span>

### <span data-ttu-id="3104f-180">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="3104f-180">-ArgumentList</span></span>

<span data-ttu-id="3104f-181">指定由 **FilePath** 参数指定的脚本的参数值，或者指定由 **ScriptBlock** 参数指定的命令的值。</span><span class="sxs-lookup"><span data-stu-id="3104f-181">Specifies values for the parameters of the script that is specified by the **FilePath** parameter or for the command that is specified by the **ScriptBlock** parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3104f-182">-Authentication</span><span class="sxs-lookup"><span data-stu-id="3104f-182">-Authentication</span></span>

<span data-ttu-id="3104f-183">指定用于对用户的凭据进行身份验证的机制。</span><span class="sxs-lookup"><span data-stu-id="3104f-183">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="3104f-184">默认值为 Default。</span><span class="sxs-lookup"><span data-stu-id="3104f-184">The default value is Default.</span></span>

<span data-ttu-id="3104f-185">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="3104f-185">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3104f-186">默认</span><span class="sxs-lookup"><span data-stu-id="3104f-186">Default</span></span>
- <span data-ttu-id="3104f-187">基本</span><span class="sxs-lookup"><span data-stu-id="3104f-187">Basic</span></span>
- <span data-ttu-id="3104f-188">Credssp</span><span class="sxs-lookup"><span data-stu-id="3104f-188">Credssp</span></span>
- <span data-ttu-id="3104f-189">摘要</span><span class="sxs-lookup"><span data-stu-id="3104f-189">Digest</span></span>
- <span data-ttu-id="3104f-190">Kerberos</span><span class="sxs-lookup"><span data-stu-id="3104f-190">Kerberos</span></span>
- <span data-ttu-id="3104f-191">Negotiate</span><span class="sxs-lookup"><span data-stu-id="3104f-191">Negotiate</span></span>
- <span data-ttu-id="3104f-192">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="3104f-192">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="3104f-193">有关此参数的值的详细信息，请参阅 [system.management.automation.runspaces.authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)。</span><span class="sxs-lookup"><span data-stu-id="3104f-193">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="3104f-194">在凭据安全服务提供程序 (CredSSP) 身份验证中，用户凭据传递到远程计算机中以进行验证，这种验证用于要求对多个资源（例如访问远程网络共享）进行验证的命令。</span><span class="sxs-lookup"><span data-stu-id="3104f-194">Credential Security Service Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="3104f-195">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="3104f-195">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="3104f-196">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="3104f-196">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3104f-197">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3104f-197">-Confirm</span></span>

<span data-ttu-id="3104f-198">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="3104f-198">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3104f-199">-Credential</span><span class="sxs-lookup"><span data-stu-id="3104f-199">-Credential</span></span>

<span data-ttu-id="3104f-200">指定有权运行计划作业的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3104f-200">Specifies a user account that has permission to run the scheduled job.</span></span> <span data-ttu-id="3104f-201">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="3104f-201">The default is the current user.</span></span>

<span data-ttu-id="3104f-202">键入用户名（如 **User01** 或 **Domain01\User01** ）或输入 PSCredential 对象，例如来自 cmdlet 的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-202">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="3104f-203">如果只输入用户名，系统会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="3104f-203">If you enter only a user name, you're prompted for a password.</span></span>

<span data-ttu-id="3104f-204">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="3104f-204">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="3104f-205">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="3104f-205">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3104f-206">-FilePath</span><span class="sxs-lookup"><span data-stu-id="3104f-206">-FilePath</span></span>

<span data-ttu-id="3104f-207">指定计划作业运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="3104f-207">Specifies a script that the scheduled job runs.</span></span> <span data-ttu-id="3104f-208">输入 `.ps1` 本地计算机上的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="3104f-208">Enter the path to a `.ps1` file on the local computer.</span></span> <span data-ttu-id="3104f-209">若要指定脚本参数的默认值，请使用 **ArgumentList** 参数。</span><span class="sxs-lookup"><span data-stu-id="3104f-209">To specify default values for the script parameters, use the **ArgumentList** parameter.</span></span>
<span data-ttu-id="3104f-210">每个 `Register-ScheduledJob` 命令都必须使用 **ScriptBlock** 或 **FilePath** 参数。</span><span class="sxs-lookup"><span data-stu-id="3104f-210">Every `Register-ScheduledJob` command must use either the **ScriptBlock** or **FilePath** parameters.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3104f-211">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="3104f-211">-InitializationScript</span></span>

<span data-ttu-id="3104f-212">指定 () 的 Windows PowerShell 脚本的完全限定路径 `.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-212">Specifies the fully qualified path to a Windows PowerShell script (`.ps1`).</span></span> <span data-ttu-id="3104f-213">在会话中运行针对后台作业而创建的初始化脚本，然后再运行由 **ScriptBlock** 参数指定的命令或由 **FilePath** 参数指定的脚本。</span><span class="sxs-lookup"><span data-stu-id="3104f-213">The initialization script runs in the session that is created for the background job before the commands that are specified by the **ScriptBlock** parameter or the script that is specified by the **FilePath** parameter.</span></span> <span data-ttu-id="3104f-214">可使用初始化脚本配置会话，例如添加文件、函数或别名、创建目录或者检查必备项。</span><span class="sxs-lookup"><span data-stu-id="3104f-214">You can use the initialization script to configure the session, such as adding files, functions, or aliases, creating directories, or checking for prerequisites.</span></span>

<span data-ttu-id="3104f-215">若要指定用于运行主作业命令的脚本，请使用 **FilePath** 参数。</span><span class="sxs-lookup"><span data-stu-id="3104f-215">To specify a script that runs the primary job commands, use the **FilePath** parameter.</span></span>

<span data-ttu-id="3104f-216">如果初始化脚本生成错误，甚至是一个非终止错误，则计划作业的当前实例将不运行，并且其状态为 " **失败** "。</span><span class="sxs-lookup"><span data-stu-id="3104f-216">If the initialization script generates an error, even a non-terminating error, the current instance of the scheduled job doesn't run and its status is **Failed** .</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3104f-217">-MaxResultCount</span><span class="sxs-lookup"><span data-stu-id="3104f-217">-MaxResultCount</span></span>

<span data-ttu-id="3104f-218">指定为计划作业保留的作业结果项数。</span><span class="sxs-lookup"><span data-stu-id="3104f-218">Specifies how many job result entries are maintained for the scheduled job.</span></span> <span data-ttu-id="3104f-219">默认值为 32。</span><span class="sxs-lookup"><span data-stu-id="3104f-219">The default value is 32.</span></span>

<span data-ttu-id="3104f-220">Windows PowerShell 将计划作业的每个触发实例的执行历史记录和结果都保存在磁盘上。</span><span class="sxs-lookup"><span data-stu-id="3104f-220">Windows PowerShell saves the execution history and results of each triggered instance of the scheduled job on disk.</span></span> <span data-ttu-id="3104f-221">此参数的值可确定为此计划作业保存的作业实例结果数。</span><span class="sxs-lookup"><span data-stu-id="3104f-221">The value of this parameter determines the number of job instance results that are saved for this scheduled job.</span></span> <span data-ttu-id="3104f-222">当作业实例结果数超过此值时，Windows PowerShell 将删除最旧的作业实例结果，以便为最新的作业实例结果腾出空间。</span><span class="sxs-lookup"><span data-stu-id="3104f-222">When the number of job instance results exceeds this value, Windows PowerShell deletes the results of the oldest job instance to make room for the results of the newest job instance.</span></span>

<span data-ttu-id="3104f-223">作业执行历史记录和作业结果保存在 `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`</span><span class="sxs-lookup"><span data-stu-id="3104f-223">The job execution history and job results are saved in the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`</span></span>
<span data-ttu-id="3104f-224">在其上创建作业的计算机上的目录。</span><span class="sxs-lookup"><span data-stu-id="3104f-224">directories on the computer on which the job is created.</span></span> <span data-ttu-id="3104f-225">若要查看执行历史记录，请使用 `Get-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3104f-225">To see the execution history, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="3104f-226">若要获取作业结果，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3104f-226">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="3104f-227">**MaxResultCount** 参数设置计划作业的 ExecutionHistoryLength 属性值。</span><span class="sxs-lookup"><span data-stu-id="3104f-227">The **MaxResultCount** parameter sets the value of the ExecutionHistoryLength property of the scheduled job.</span></span>

<span data-ttu-id="3104f-228">若要删除当前执行历史记录和作业结果，请使用 cmdlet 的 **ClearExecutionHistory** 参数 `Set-ScheduledJob` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-228">To delete the current execution history and job results, use the **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3104f-229">-Name</span><span class="sxs-lookup"><span data-stu-id="3104f-229">-Name</span></span>

<span data-ttu-id="3104f-230">指定计划作业的名称。</span><span class="sxs-lookup"><span data-stu-id="3104f-230">Specifies a name for the scheduled job.</span></span> <span data-ttu-id="3104f-231">该名称也用于计划作业的所有启动实例。</span><span class="sxs-lookup"><span data-stu-id="3104f-231">The name is also used for all started instances of the scheduled job.</span></span> <span data-ttu-id="3104f-232">该名称在计算机上必须唯一。</span><span class="sxs-lookup"><span data-stu-id="3104f-232">The name must be unique on the computer.</span></span> <span data-ttu-id="3104f-233">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="3104f-233">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3104f-234">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="3104f-234">-RunAs32</span></span>

<span data-ttu-id="3104f-235">在 32 位进程中运行计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-235">Runs the scheduled job in a 32-bit process.</span></span>

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

### <span data-ttu-id="3104f-236">-RunEvery</span><span class="sxs-lookup"><span data-stu-id="3104f-236">-RunEvery</span></span>

<span data-ttu-id="3104f-237">用于指定运行作业的频率。</span><span class="sxs-lookup"><span data-stu-id="3104f-237">Used to specify how often to run the job.</span></span> <span data-ttu-id="3104f-238">例如，使用此选项可以每隔15分钟运行一次作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-238">For example, use this option to run a job every 15 minutes.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3104f-239">-RunNow</span><span class="sxs-lookup"><span data-stu-id="3104f-239">-RunNow</span></span>

<span data-ttu-id="3104f-240">运行 cmdlet 后立即启动作业 `Register-ScheduledJob` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-240">Starts a job immediately, as soon as the `Register-ScheduledJob` cmdlet is run.</span></span> <span data-ttu-id="3104f-241">此参数无需触发任务计划程序在注册后立即运行 Windows PowerShell 脚本，并且不需要用户创建指定开始日期和时间的触发器。</span><span class="sxs-lookup"><span data-stu-id="3104f-241">This parameter eliminates the need to trigger Task Scheduler to run a Windows PowerShell script immediately after registration, and doesn't require users to create a trigger that specifies a starting date and time.</span></span>

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

### <span data-ttu-id="3104f-242">-Get-scheduledjoboption</span><span class="sxs-lookup"><span data-stu-id="3104f-242">-ScheduledJobOption</span></span>

<span data-ttu-id="3104f-243">设置计划作业的选项。</span><span class="sxs-lookup"><span data-stu-id="3104f-243">Sets options for the scheduled job.</span></span> <span data-ttu-id="3104f-244">输入 **ScheduledJobOptions** 对象（例如使用 cmdlet 创建的对象） `New-ScheduledJobOption` 或哈希表值。</span><span class="sxs-lookup"><span data-stu-id="3104f-244">Enter a **ScheduledJobOptions** object, such as one that you create by using the `New-ScheduledJobOption` cmdlet, or a hash table value.</span></span>

<span data-ttu-id="3104f-245">你可以在注册计划作业时设置计划作业的选项，或者使用 `Set-ScheduledJobOption` 或 `Set-ScheduledJob` cmdlet 来更改选项。</span><span class="sxs-lookup"><span data-stu-id="3104f-245">You can set options for a scheduled job when you register the schedule job or use the `Set-ScheduledJobOption` or `Set-ScheduledJob` cmdlets to change the options.</span></span>

<span data-ttu-id="3104f-246">许多选项及其默认值都可确定是否运行计划作业以及运行时间。</span><span class="sxs-lookup"><span data-stu-id="3104f-246">Many of the options and their default values determine whether and when a scheduled job runs.</span></span> <span data-ttu-id="3104f-247">在计划某个作业之前，务必检查这些选项。</span><span class="sxs-lookup"><span data-stu-id="3104f-247">Be sure to review these options before scheduling a job.</span></span> <span data-ttu-id="3104f-248">有关计划作业选项（包括默认值）的说明，请参阅 `New-ScheduledJobOption` 。</span><span class="sxs-lookup"><span data-stu-id="3104f-248">For a description of the scheduled job options, including the default values, see `New-ScheduledJobOption`.</span></span>

<span data-ttu-id="3104f-249">若要提交哈希表，请使用以下键。</span><span class="sxs-lookup"><span data-stu-id="3104f-249">To submit a hash table, use the following keys.</span></span> <span data-ttu-id="3104f-250">在下列哈希表中，这些键与其默认值一起显示。</span><span class="sxs-lookup"><span data-stu-id="3104f-250">In the following hash table, the keys are shown with their default values.</span></span>

`@{StartIfOnBattery=$False; StopIfGoingOnBattery=$True; WakeToRun=$False; StartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False; ShowInTaskScheduler=$True; RunElevated=$False; RunWithoutNetwork=$False; DoNotAllowDemandStart=$False; MultipleInstancePolicy="IgnoreNew"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3104f-251">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="3104f-251">-ScriptBlock</span></span>

<span data-ttu-id="3104f-252">指定计划作业运行的命令。</span><span class="sxs-lookup"><span data-stu-id="3104f-252">Specifies the commands that the scheduled job runs.</span></span> <span data-ttu-id="3104f-253">将命令括在大括号中， (`{}`) 创建脚本块。</span><span class="sxs-lookup"><span data-stu-id="3104f-253">Enclose the commands in curly braces (`{}`) to create a script block.</span></span> <span data-ttu-id="3104f-254">若要指定命令参数的默认值，请使用 **ArgumentList** 参数。</span><span class="sxs-lookup"><span data-stu-id="3104f-254">To specify default values for command parameters, use the **ArgumentList** parameter.</span></span>

<span data-ttu-id="3104f-255">每个 `Register-ScheduledJob` 命令都必须使用 **ScriptBlock** 或 **FilePath** 参数。</span><span class="sxs-lookup"><span data-stu-id="3104f-255">Every `Register-ScheduledJob` command must use either the **ScriptBlock** or **FilePath** parameters.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3104f-256">-Trigger</span><span class="sxs-lookup"><span data-stu-id="3104f-256">-Trigger</span></span>

<span data-ttu-id="3104f-257">指定计划作业的触发器。</span><span class="sxs-lookup"><span data-stu-id="3104f-257">Specifies the triggers for the scheduled job.</span></span> <span data-ttu-id="3104f-258">输入一个或多个 **ScheduledJobTrigger** 对象（例如 cmdlet 返回的对象 `New-JobTrigger` ），或者输入一个作业触发器键和值的哈希表。</span><span class="sxs-lookup"><span data-stu-id="3104f-258">Enter one or more **ScheduledJobTrigger** objects, such as the objects that the `New-JobTrigger` cmdlet returns, or a hash table of job trigger keys and values.</span></span>

<span data-ttu-id="3104f-259">作业触发器启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-259">A job trigger starts the schedule job.</span></span> <span data-ttu-id="3104f-260">该触发器可指定一次性或循环计划作业或者事件，例如在用户进行登录或 Windows 启动时。</span><span class="sxs-lookup"><span data-stu-id="3104f-260">The trigger can specify a one-time or recurring scheduled or an event, such as when a user logs on or Windows starts.</span></span>

<span data-ttu-id="3104f-261">**Trigger** 参数为可选参数。</span><span class="sxs-lookup"><span data-stu-id="3104f-261">The **Trigger** parameter is optional.</span></span> <span data-ttu-id="3104f-262">你可以在创建计划作业时添加触发器，使用 `Add-JobTrigger` 、 `Set-JobTrigger` 或 `Set-ScheduledJob` cmdlet 稍后添加或更改作业触发器，或者使用 `Start-Job` cmdlet 立即启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-262">You can add a trigger when you create the scheduled job, use the `Add-JobTrigger`, `Set-JobTrigger`, or `Set-ScheduledJob` cmdlets to add or change job triggers later, or use the `Start-Job` cmdlet to start the scheduled job immediately.</span></span> <span data-ttu-id="3104f-263">你还可以在没有用作模板的触发器的情况下创建和保留计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-263">You can also create and maintain a scheduled job without a trigger that is used as a template.</span></span>

<span data-ttu-id="3104f-264">若要提交哈希表，请使用以下键：</span><span class="sxs-lookup"><span data-stu-id="3104f-264">To submit a hash table, use the following keys:</span></span>

- <span data-ttu-id="3104f-265">**频率** ：每日、每周、AtStartup、AtLogon</span><span class="sxs-lookup"><span data-stu-id="3104f-265">**Frequency** : Daily, Weekly, AtStartup, AtLogon</span></span>
- <span data-ttu-id="3104f-266">**位置** ：任何有效的时间字符串</span><span class="sxs-lookup"><span data-stu-id="3104f-266">**At** : Any valid time string</span></span>
- <span data-ttu-id="3104f-267">**DaysOfWeek** -日期名称的任意组合</span><span class="sxs-lookup"><span data-stu-id="3104f-267">**DaysOfWeek** - Any combination of day names</span></span>
- <span data-ttu-id="3104f-268">**间隔** -任何有效的频率间隔</span><span class="sxs-lookup"><span data-stu-id="3104f-268">**Interval** - Any valid frequency interval</span></span>
- <span data-ttu-id="3104f-269">**RandomDelay** ：任何有效的 timespan 字符串</span><span class="sxs-lookup"><span data-stu-id="3104f-269">**RandomDelay** : Any valid timespan string</span></span>
- <span data-ttu-id="3104f-270">**用户** ：任何有效的用户。</span><span class="sxs-lookup"><span data-stu-id="3104f-270">**User** : Any valid user.</span></span> <span data-ttu-id="3104f-271">仅与 AtLogon frequency 值一起使用</span><span class="sxs-lookup"><span data-stu-id="3104f-271">Used only with the AtLogon frequency value</span></span>

<span data-ttu-id="3104f-272">例如：</span><span class="sxs-lookup"><span data-stu-id="3104f-272">For example:</span></span>

`@{Frequency="Once"; At="3am"; DaysOfWeek="Monday", "Wednesday"; Interval=2; RandomDelay="30minutes"; User="Domain1\User01"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3104f-273">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3104f-273">-WhatIf</span></span>

<span data-ttu-id="3104f-274">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="3104f-274">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="3104f-275">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="3104f-275">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="3104f-276">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3104f-276">CommonParameters</span></span>

<span data-ttu-id="3104f-277">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="3104f-277">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3104f-278">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="3104f-278">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3104f-279">输入</span><span class="sxs-lookup"><span data-stu-id="3104f-279">INPUTS</span></span>

### <span data-ttu-id="3104f-280">无</span><span class="sxs-lookup"><span data-stu-id="3104f-280">None</span></span>

<span data-ttu-id="3104f-281">不能将输入向下发送到该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3104f-281">You can't send input down the pipeline to this cmdlet.</span></span>

## <span data-ttu-id="3104f-282">输出</span><span class="sxs-lookup"><span data-stu-id="3104f-282">OUTPUTS</span></span>

### <span data-ttu-id="3104f-283">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="3104f-283">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>

## <span data-ttu-id="3104f-284">注释</span><span class="sxs-lookup"><span data-stu-id="3104f-284">NOTES</span></span>

<span data-ttu-id="3104f-285">每个计划作业都保存在 `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` 本地计算机上目录的子目录中。</span><span class="sxs-lookup"><span data-stu-id="3104f-285">Each scheduled job is saved in a subdirectory of the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` directory on the local computer.</span></span>
<span data-ttu-id="3104f-286">为计划作业命名子目录，并包含计划作业的 XML 文件以及其执行历史记录的记录。</span><span class="sxs-lookup"><span data-stu-id="3104f-286">The subdirectory is named for the scheduled job and contains an XML file for the scheduled job and records of its execution history.</span></span> <span data-ttu-id="3104f-287">有关磁盘上计划作业的详细信息，请参阅 [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md)。</span><span class="sxs-lookup"><span data-stu-id="3104f-287">For more information about scheduled jobs on disk, see [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md).</span></span>

<span data-ttu-id="3104f-288">在 Windows PowerShell 中创建的计划作业将显示在 "任务计划程序" `Library\Microsoft\Windows\PowerShell\ScheduledJobs` 文件夹任务计划程序中。</span><span class="sxs-lookup"><span data-stu-id="3104f-288">Scheduled jobs that you create in Windows PowerShell appear in Task Scheduler in the Task Scheduler `Library\Microsoft\Windows\PowerShell\ScheduledJobs` folder.</span></span> <span data-ttu-id="3104f-289">你可以使用任务计划程序查看和编辑计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-289">You can use Task Scheduler to view and edit the scheduled job.</span></span>

<span data-ttu-id="3104f-290">你可以使用任务计划程序、 **schtasks.exe** 命令行工具和任务计划程序 cmdlet 来管理你使用计划作业 cmdlet 创建的计划作业。</span><span class="sxs-lookup"><span data-stu-id="3104f-290">You can use Task Scheduler, the **schtasks.exe** command-line tool, and the Task Scheduler cmdlets to manage scheduled jobs that you create with the Scheduled Job cmdlets.</span></span> <span data-ttu-id="3104f-291">但是，不能使用计划的作业 cmdlet 来管理在任务计划程序中创建的任务。</span><span class="sxs-lookup"><span data-stu-id="3104f-291">However, you can't use the Scheduled Job cmdlets to manage tasks that you create in Task Scheduler.</span></span>

<span data-ttu-id="3104f-292">如果计划作业命令失败，则 Windows PowerShell 将返回一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="3104f-292">If a scheduled job command fails, Windows PowerShell returns an error message.</span></span> <span data-ttu-id="3104f-293">但是，如果作业在任务计划程序尝试运行它时失败，则 Windows PowerShell 将无法使用此错误。</span><span class="sxs-lookup"><span data-stu-id="3104f-293">However, if the job fails when Task Scheduler tries to run it, the error isn't available to Windows PowerShell.</span></span>

<span data-ttu-id="3104f-294">如果计划作业没有运行，请使用以下方法来查找原因：</span><span class="sxs-lookup"><span data-stu-id="3104f-294">If a scheduled job doesn't run, use the following methods to find the reason:</span></span>

- <span data-ttu-id="3104f-295">验证作业触发器是否设置正确。</span><span class="sxs-lookup"><span data-stu-id="3104f-295">Verify that the job trigger is set properly.</span></span>
  - <span data-ttu-id="3104f-296">验证是否满足作业选项中设置的条件。</span><span class="sxs-lookup"><span data-stu-id="3104f-296">Verify that the conditions set in the job options are satisfied.</span></span>
- <span data-ttu-id="3104f-297">验证运行作业的用户帐户是否有权运行该作业中的命令或脚本。</span><span class="sxs-lookup"><span data-stu-id="3104f-297">Verify that the user account under which the job runs has permission to run the commands or scripts in the job.</span></span>
- <span data-ttu-id="3104f-298">检查任务计划程序历史记录中是否存在错误。</span><span class="sxs-lookup"><span data-stu-id="3104f-298">Check the Task Scheduler history for errors.</span></span>
- <span data-ttu-id="3104f-299">检查任务计划程序事件日志中是否存在错误。</span><span class="sxs-lookup"><span data-stu-id="3104f-299">Check the Task Scheduler event log for errors.</span></span>

<span data-ttu-id="3104f-300">有关详细信息，请参阅 [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="3104f-300">For more information, see [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md).</span></span>

## <span data-ttu-id="3104f-301">相关链接</span><span class="sxs-lookup"><span data-stu-id="3104f-301">RELATED LINKS</span></span>

[<span data-ttu-id="3104f-302">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3104f-302">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="3104f-303">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3104f-303">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="3104f-304">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3104f-304">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="3104f-305">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3104f-305">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="3104f-306">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3104f-306">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="3104f-307">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3104f-307">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="3104f-308">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3104f-308">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="3104f-309">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="3104f-309">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="3104f-310">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3104f-310">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="3104f-311">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="3104f-311">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="3104f-312">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3104f-312">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="3104f-313">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3104f-313">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="3104f-314">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3104f-314">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="3104f-315">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3104f-315">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="3104f-316">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="3104f-316">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="3104f-317">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3104f-317">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
