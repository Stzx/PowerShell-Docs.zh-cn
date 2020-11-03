---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJob
ms.openlocfilehash: 99dbdc84430c0a8b5cf505a22b139cd07236e160
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197772"
---
# <span data-ttu-id="edda5-103">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="edda5-103">Set-ScheduledJob</span></span>

## <span data-ttu-id="edda5-104">摘要</span><span class="sxs-lookup"><span data-stu-id="edda5-104">SYNOPSIS</span></span>
<span data-ttu-id="edda5-105">更改计划作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-105">Changes scheduled jobs.</span></span>

## <span data-ttu-id="edda5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="edda5-106">SYNTAX</span></span>

### <span data-ttu-id="edda5-107">ScriptBlock（默认值）</span><span class="sxs-lookup"><span data-stu-id="edda5-107">ScriptBlock (Default)</span></span>

```
Set-ScheduledJob [-Name <String>] [-ScriptBlock <ScriptBlock>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### <span data-ttu-id="edda5-108">文件路径</span><span class="sxs-lookup"><span data-stu-id="edda5-108">FilePath</span></span>

```
Set-ScheduledJob [-Name <String>] [-FilePath <String>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### <span data-ttu-id="edda5-109">执行</span><span class="sxs-lookup"><span data-stu-id="edda5-109">Execution</span></span>

```
Set-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-ClearExecutionHistory] [-PassThru]
 [<CommonParameters>]
```

## <span data-ttu-id="edda5-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="edda5-110">DESCRIPTION</span></span>
<span data-ttu-id="edda5-111">**Set-ScheduledJob** cmdlet 更改计划作业的属性，例如作业运行的命令或运行该作业时所需的凭据。</span><span class="sxs-lookup"><span data-stu-id="edda5-111">The **Set-ScheduledJob** cmdlet changes the properties of scheduled jobs, such as the commands that the jobs run or the credentials required to run the job.</span></span>
<span data-ttu-id="edda5-112">它还可用于清除计划作业的执行历史记录。</span><span class="sxs-lookup"><span data-stu-id="edda5-112">You can also use it to clear the execution history of the scheduled job.</span></span>

<span data-ttu-id="edda5-113">若要使用此 cmdlet，请首先使用 Get-ScheduledJob cmdlet 来获取计划作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-113">To use this cmdlet, begin by using the Get-ScheduledJob cmdlet to get the scheduled job.</span></span>
<span data-ttu-id="edda5-114">然后，通过管道将计划作业传递给 **get-scheduledjob** ，或将作业保存在变量中，并使用 *InputObject* 参数来标识作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-114">Then, pipe the scheduled job to **Set-ScheduledJob** or save the job in a variable and use the *InputObject* parameter to identify the job.</span></span>
<span data-ttu-id="edda5-115">使用 **Set-ScheduledJob** 的剩余参数，以更改作业属性或清除执行历史记录。</span><span class="sxs-lookup"><span data-stu-id="edda5-115">Use the remaining parameters of **Set-ScheduledJob** to change the job properties or clear the execution history.</span></span>

<span data-ttu-id="edda5-116">尽管可以使用 **get-scheduledjob** 更改计划作业的触发器和选项，但 Get-jobtrigger、get-jobtrigger 和 Set-ScheduledJobOption cmdlet 提供了更简单的方法来完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="edda5-116">Although you can use **Set-ScheduledJob** to change the triggers and options of a scheduled job, the Add-JobTrigger, Set-JobTrigger, and Set-ScheduledJobOption cmdlets provide much easier ways to accomplish those tasks.</span></span>
<span data-ttu-id="edda5-117">若要创建新的计划作业，请使用 Register-ScheduledJob cmdlet。</span><span class="sxs-lookup"><span data-stu-id="edda5-117">To create a new scheduled job, use the Register-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="edda5-118">**Get-scheduledjob** 的 *Trigger* 参数可添加一个或多个启动作业的作业触发器。</span><span class="sxs-lookup"><span data-stu-id="edda5-118">The *Trigger* parameter of **Set-ScheduledJob** adds one or more job triggers that start the job.</span></span>
<span data-ttu-id="edda5-119">*Trigger* 参数是可选的，因此你可以在创建计划作业时添加触发器，稍后添加作业触发器，添加 *RunNow* 参数以立即启动作业，使用 Start-Job cmdlet 随时启动作业，或将存计划作业保存为其他作业的模板。</span><span class="sxs-lookup"><span data-stu-id="edda5-119">The *Trigger* parameter is optional, so you can add triggers when you create the scheduled job, add job triggers later, add the *RunNow* parameter to start the job immediately, use the Start-Job cmdlet to start the job immediately at any time, or save the untriggered scheduled job as a template for other jobs.</span></span>

<span data-ttu-id="edda5-120">**Get-scheduledjob** 是 Windows PowerShell 中包含的 PSScheduledJob 模块中的作业计划 cmdlet 集合之一。</span><span class="sxs-lookup"><span data-stu-id="edda5-120">**Set-ScheduledJob** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="edda5-121">有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。</span><span class="sxs-lookup"><span data-stu-id="edda5-121">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="edda5-122">导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="edda5-122">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="edda5-123">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="edda5-123">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="edda5-124">示例</span><span class="sxs-lookup"><span data-stu-id="edda5-124">EXAMPLES</span></span>

### <span data-ttu-id="edda5-125">示例1：更改作业运行的脚本</span><span class="sxs-lookup"><span data-stu-id="edda5-125">Example 1: Change the script that a job runs</span></span>

```
PS C:\> Get-ScheduledJob -Name "Inventory"
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-Inventory.ps1             True

The second command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job. A pipeline operator (|) sends the scheduled job to the **Set-ScheduledJob** cmdlet. The **Set-ScheduledJob** cmdlet uses the *Script* parameter to specify a new script, Get-FullInventory.ps1. The command uses the *Passthru* parameter to return the scheduled job after the change.
PS C:\> Get-ScheduledJob -Name "Inventory" | Set-ScheduledJob -FilePath "C:\Scripts\Get-FullInventory.ps1" -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-FullInventory.ps1         True
```

<span data-ttu-id="edda5-126">此示例显示了如何更改在计划作业中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="edda5-126">This example shows how to change the script that is run in a scheduled job.</span></span>

<span data-ttu-id="edda5-127">第一个命令使用 Get-ScheduledJob cmdlet 获取清单计划作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-127">The first command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job.</span></span>
<span data-ttu-id="edda5-128">此输出显示该作业运行 Get-Inventory.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="edda5-128">The output shows that the job runs the Get-Inventory.ps1 script.</span></span>

<span data-ttu-id="edda5-129">此命令不是必需的；包含它只是为了显示脚本更改的效果。</span><span class="sxs-lookup"><span data-stu-id="edda5-129">This command is not required; it is included only to show the effect of the script change.</span></span>

### <span data-ttu-id="edda5-130">示例2：删除计划作业的执行历史记录</span><span class="sxs-lookup"><span data-stu-id="edda5-130">Example 2: Delete the execution history of a scheduled job</span></span>

```
PS C:\> Get-ScheduledJob BackupArchive | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="edda5-131">此命令删除 BackupArchive 计划作业的当前执行历史记录以及保存的作业结果。</span><span class="sxs-lookup"><span data-stu-id="edda5-131">This command deletes the current execution history and saved job results for the BackupArchive scheduled job.</span></span>

<span data-ttu-id="edda5-132">该命令使用 Get-ScheduledJob cmdlet 来获取 BackupArchive 计划作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-132">The command uses the Get-ScheduledJob cmdlet to get the BackupArchive scheduled job.</span></span>
<span data-ttu-id="edda5-133">管道运算符 (|) 将该作业发送到 **Set-ScheduledJob** cmdlet 以更改它。</span><span class="sxs-lookup"><span data-stu-id="edda5-133">A pipeline operator (|) sends the job to the **Set-ScheduledJob** cmdlet to change it.</span></span>
<span data-ttu-id="edda5-134">**Get-scheduledjob** Cmdlet 使用 *ClearExecutionHistory* 参数来删除执行历史记录和保存的结果。</span><span class="sxs-lookup"><span data-stu-id="edda5-134">The **Set-ScheduledJob** cmdlet uses the *ClearExecutionHistory* parameter to delete the execution history and saved results.</span></span>

<span data-ttu-id="edda5-135">有关计划作业的执行历史记录和保存的作业结果的详细信息，请参阅 about_Scheduled_Jobs。</span><span class="sxs-lookup"><span data-stu-id="edda5-135">For more information about the execution history and saved job results of scheduled jobs, see about_Scheduled_Jobs.</span></span>

### <span data-ttu-id="edda5-136">示例3：更改远程计算机上的计划作业</span><span class="sxs-lookup"><span data-stu-id="edda5-136">Example 3: Change scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -Computer "Server01, Server02" -ScriptBlock {Get-ScheduledJob | Set-ScheduledJob -InitializationScript \\SrvA\Scripts\SetForRun.ps1}
```

<span data-ttu-id="edda5-137">此命令更改 Server01 和 Server02 计算机上所有计划作业中的初始化脚本。</span><span class="sxs-lookup"><span data-stu-id="edda5-137">This command changes the initialization script in all scheduled jobs on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="edda5-138">该命令使用 Invoke-Command cmdlet 在 Server01 和 Server02 计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="edda5-138">The command uses the Invoke-Command cmdlet to run a command on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="edda5-139">远程命令以获取计算机上所有计划作业的 Get-ScheduledJob 命令开头。</span><span class="sxs-lookup"><span data-stu-id="edda5-139">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="edda5-140">计划的作业将通过管道传递给 **get-scheduledjob** cmdlet，该 cmdlet 会将初始化脚本更改为 SetForRun.ps1。</span><span class="sxs-lookup"><span data-stu-id="edda5-140">The scheduled jobs are piped to the **Set-ScheduledJob** cmdlet, which changes the initialization script to SetForRun.ps1.</span></span>

## <span data-ttu-id="edda5-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="edda5-141">PARAMETERS</span></span>

### <span data-ttu-id="edda5-142">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="edda5-142">-ArgumentList</span></span>
<span data-ttu-id="edda5-143">指定由 *FilePath* 参数指定的脚本的参数值，或者指定由 *ScriptBlock* 参数指定的命令的值。</span><span class="sxs-lookup"><span data-stu-id="edda5-143">Specifies values for the parameters of the script that is specified by the *FilePath* parameter or for the command that is specified by the *ScriptBlock* parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-144">-Authentication</span><span class="sxs-lookup"><span data-stu-id="edda5-144">-Authentication</span></span>
<span data-ttu-id="edda5-145">指定用于对用户的凭据进行身份验证的机制。</span><span class="sxs-lookup"><span data-stu-id="edda5-145">Specifies the mechanism that is used to authenticate the user's credentials.</span></span>
<span data-ttu-id="edda5-146">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="edda5-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="edda5-147">默认</span><span class="sxs-lookup"><span data-stu-id="edda5-147">Default</span></span>
- <span data-ttu-id="edda5-148">基本</span><span class="sxs-lookup"><span data-stu-id="edda5-148">Basic</span></span>
- <span data-ttu-id="edda5-149">Credssp</span><span class="sxs-lookup"><span data-stu-id="edda5-149">Credssp</span></span>
- <span data-ttu-id="edda5-150">摘要</span><span class="sxs-lookup"><span data-stu-id="edda5-150">Digest</span></span>
- <span data-ttu-id="edda5-151">Kerberos</span><span class="sxs-lookup"><span data-stu-id="edda5-151">Kerberos</span></span>
- <span data-ttu-id="edda5-152">Negotiate</span><span class="sxs-lookup"><span data-stu-id="edda5-152">Negotiate</span></span>
- <span data-ttu-id="edda5-153">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="edda5-153">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="edda5-154">默认值为 Default。</span><span class="sxs-lookup"><span data-stu-id="edda5-154">The default value is Default.</span></span>
<span data-ttu-id="edda5-155">有关此参数的值的详细信息，请参阅 MSDN 库中的 [System.management.automation.runspaces.authenticationmechanism 枚举](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) 。</span><span class="sxs-lookup"><span data-stu-id="edda5-155">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

<span data-ttu-id="edda5-156">警告：凭据安全支持提供程序 (CredSSP) 身份验证，其中用户的凭据将传递给要进行身份验证的远程计算机，其适用于需要在多个资源（例如访问远程网络共享）上进行身份验证的命令。</span><span class="sxs-lookup"><span data-stu-id="edda5-156">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="edda5-157">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="edda5-157">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="edda5-158">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="edda5-158">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ScriptBlock, FilePath
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-159">-ClearExecutionHistory</span><span class="sxs-lookup"><span data-stu-id="edda5-159">-ClearExecutionHistory</span></span>
<span data-ttu-id="edda5-160">删除计划作业的当前执行历史记录以及保存的结果。</span><span class="sxs-lookup"><span data-stu-id="edda5-160">Deletes the current execution history and the saved results of the scheduled job.</span></span>

<span data-ttu-id="edda5-161">作业执行历史记录和作业结果都将随计划作业一同保存在创建该作业的计算机上的 $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs 目录中。</span><span class="sxs-lookup"><span data-stu-id="edda5-161">The job execution history and job results are saved with the scheduled job in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory on the computer on which the job is created.</span></span>
<span data-ttu-id="edda5-162">若要查看执行历史记录，请使用 Get-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="edda5-162">To see the execution history, use the Get-Job cmdlet.</span></span>
<span data-ttu-id="edda5-163">若要获取作业结果，请使用 Receive-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="edda5-163">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="edda5-164">此参数不会影响任务计划程序写入 Windows 事件日志的事件，也不会阻止 Windows PowerShell 保存作业结果。</span><span class="sxs-lookup"><span data-stu-id="edda5-164">This parameter does not affect the events that Task Scheduler writes to the Windows event logs and it does not stop Windows PowerShell from saving job results.</span></span>
<span data-ttu-id="edda5-165">若要管理保存的作业结果数，请使用 *MaxResultCount* 参数。</span><span class="sxs-lookup"><span data-stu-id="edda5-165">To manage the number of job results that are saved, use the *MaxResultCount* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Execution
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-166">-Credential</span><span class="sxs-lookup"><span data-stu-id="edda5-166">-Credential</span></span>
<span data-ttu-id="edda5-167">指定有权运行计划作业的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="edda5-167">Specifies a user account that has permission to run the scheduled job.</span></span>
<span data-ttu-id="edda5-168">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="edda5-168">The default is the current user.</span></span>

<span data-ttu-id="edda5-169">键入用户名（如 User01 或 Domain01\User01）或输入 **PSCredential** 对象，例如 Get-Credential cmdlet 中的一个。</span><span class="sxs-lookup"><span data-stu-id="edda5-169">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one from the Get-Credential cmdlet.</span></span>
<span data-ttu-id="edda5-170">如果仅输入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="edda5-170">If you enter only a user name, you will be prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-171">-FilePath</span><span class="sxs-lookup"><span data-stu-id="edda5-171">-FilePath</span></span>
<span data-ttu-id="edda5-172">指定计划作业运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="edda5-172">Specifies a script that the scheduled job runs.</span></span>
<span data-ttu-id="edda5-173">在本地计算机上输入指向 .ps1 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="edda5-173">Enter the path to a .ps1 file on the local computer.</span></span>
<span data-ttu-id="edda5-174">若要指定脚本参数的默认值，请使用 *ArgumentList* 参数。</span><span class="sxs-lookup"><span data-stu-id="edda5-174">To specify default values for the script parameters, use the *ArgumentList* parameter.</span></span>
<span data-ttu-id="edda5-175">每个计划作业都必须具有 *ScriptBlock* 或 *FilePath* 值。</span><span class="sxs-lookup"><span data-stu-id="edda5-175">Every scheduled job must have either a *ScriptBlock* or *FilePath* value.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-176">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="edda5-176">-InitializationScript</span></span>
<span data-ttu-id="edda5-177">指定指向 Windows PowerShell 脚本 (.ps1) 的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="edda5-177">Specifies the fully qualified path to a Windows PowerShell script (.ps1).</span></span>
<span data-ttu-id="edda5-178">在会话中运行针对后台作业而创建的初始化脚本，然后再运行由 *ScriptBlock* 参数指定的命令或由 *FilePath* 参数指定的脚本。</span><span class="sxs-lookup"><span data-stu-id="edda5-178">The initialization script runs in the session that is created for the background job before the commands that are specified by the *ScriptBlock* parameter or the script that is specified by the *FilePath* parameter.</span></span>
<span data-ttu-id="edda5-179">可使用初始化脚本配置会话，例如添加文件、函数或别名、创建目录或者检查必备项。</span><span class="sxs-lookup"><span data-stu-id="edda5-179">You can use the initialization script to configure the session, such as adding files, functions, or aliases, creating directories, or checking for prerequisites.</span></span>

<span data-ttu-id="edda5-180">若要指定用于运行主作业命令的脚本，请使用 *FilePath* 参数。</span><span class="sxs-lookup"><span data-stu-id="edda5-180">To specify a script that runs the primary job commands, use the *FilePath* parameter.</span></span>

<span data-ttu-id="edda5-181">如果初始化脚本生成错误，包括非终止错误，则计划作业的当前实例将不运行，并且其状态为 "失败"。</span><span class="sxs-lookup"><span data-stu-id="edda5-181">If the initialization script generates an error, including a non-terminating error, the current instance of the scheduled job does not run and its status is Failed.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-182">-InputObject</span><span class="sxs-lookup"><span data-stu-id="edda5-182">-InputObject</span></span>
<span data-ttu-id="edda5-183">指定要更改的计划作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-183">Specifies the scheduled job to be changed.</span></span>
<span data-ttu-id="edda5-184">输入包含 **ScheduledJobDefinition** 对象的变量，或者键入获取 **ScheduledJobDefinition** 对象的命令或表达式，如 Get-ScheduledJob 命令。</span><span class="sxs-lookup"><span data-stu-id="edda5-184">Enter a variable that contains **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="edda5-185">还可以通过管道将 **ScheduledJobDefinition** 对象传递给 **get-scheduledjob** 。</span><span class="sxs-lookup"><span data-stu-id="edda5-185">You can also pipe a **ScheduledJobDefinition** object to **Set-ScheduledJob** .</span></span>

<span data-ttu-id="edda5-186">如果指定多个计划作业，则 **Set-ScheduledJob** 将对所有作业做出相同的更改。</span><span class="sxs-lookup"><span data-stu-id="edda5-186">If you specify multiple scheduled jobs, **Set-ScheduledJob** makes the same changes to all jobs.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-187">-MaxResultCount</span><span class="sxs-lookup"><span data-stu-id="edda5-187">-MaxResultCount</span></span>
<span data-ttu-id="edda5-188">指定为计划作业保留的作业结果项数。</span><span class="sxs-lookup"><span data-stu-id="edda5-188">Specifies how many job result entries are maintained for the scheduled job.</span></span>
<span data-ttu-id="edda5-189">默认值为 32。</span><span class="sxs-lookup"><span data-stu-id="edda5-189">The default value is 32.</span></span>

<span data-ttu-id="edda5-190">Windows PowerShell 将计划作业的每个触发实例的执行历史记录和结果都保存在磁盘上。</span><span class="sxs-lookup"><span data-stu-id="edda5-190">Windows PowerShell saves the execution history and results of each triggered instance of the scheduled job on disk.</span></span>
<span data-ttu-id="edda5-191">此参数的值可确定为此计划作业保存的作业实例结果数。</span><span class="sxs-lookup"><span data-stu-id="edda5-191">The value of this parameter determines the number of job instance results that are saved for this scheduled job.</span></span>
<span data-ttu-id="edda5-192">当作业实例结果数超过此值时，Windows PowerShell 将删除最旧的作业实例结果，以便为最新的作业实例结果腾出空间。</span><span class="sxs-lookup"><span data-stu-id="edda5-192">When the number of job instance results exceeds this value, Windows PowerShell deletes the results of the oldest job instance to make room for the results of the newest job instance.</span></span>

<span data-ttu-id="edda5-193">作业执行历史记录和作业结果保存在 \\ \<JobName\> \\ \<Timestamp\> 创建该作业的计算机上的 $home \appdata\local\microsoft\windows\powershell\scheduledjobs \Output 目录中。</span><span class="sxs-lookup"><span data-stu-id="edda5-193">The job execution history and job results are saved in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\\\<JobName\>\Output\\\<Timestamp\> directories on the computer on which the job is created.</span></span>
<span data-ttu-id="edda5-194">若要查看执行历史记录，请使用 Get-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="edda5-194">To see the execution history, use the Get-Job cmdlet.</span></span>
<span data-ttu-id="edda5-195">若要获取作业结果，请使用 Receive-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="edda5-195">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="edda5-196">*MaxResultCount* 参数设置计划作业的 ExecutionHistoryLength 属性值。</span><span class="sxs-lookup"><span data-stu-id="edda5-196">The *MaxResultCount* parameter sets the value of the ExecutionHistoryLength property of the scheduled job.</span></span>

<span data-ttu-id="edda5-197">若要删除当前执行历史记录和作业结果，请使用 *ClearExecutionHistory* 参数。</span><span class="sxs-lookup"><span data-stu-id="edda5-197">To delete the current execution history and job results, use the *ClearExecutionHistory* parameter.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-198">-Name</span><span class="sxs-lookup"><span data-stu-id="edda5-198">-Name</span></span>
<span data-ttu-id="edda5-199">为计划作业及其实例指定新名称。</span><span class="sxs-lookup"><span data-stu-id="edda5-199">Specifies a new name for the scheduled job and instances of the scheduled job.</span></span>
<span data-ttu-id="edda5-200">该名称在本地计算机上必须唯一。</span><span class="sxs-lookup"><span data-stu-id="edda5-200">The name must be unique on the local computer.</span></span>

<span data-ttu-id="edda5-201">若要确定要更改的计划作业，请使用 *InputObject* 参数或通过管道将计划作业从 Get-ScheduledJob 传递给 **get-scheduledjob** 。</span><span class="sxs-lookup"><span data-stu-id="edda5-201">To identify the scheduled job to be changed, use the *InputObject* parameter or pipe a scheduled job from Get-ScheduledJob to **Set-ScheduledJob** .</span></span>

<span data-ttu-id="edda5-202">此参数不更改磁盘上作业实例的名称。</span><span class="sxs-lookup"><span data-stu-id="edda5-202">This parameter does not change the names of job instances on disk.</span></span>
<span data-ttu-id="edda5-203">它仅影响在此命令完成后启动的作业实例。</span><span class="sxs-lookup"><span data-stu-id="edda5-203">It affects only job instances that are started after this command completes.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-204">-PassThru</span><span class="sxs-lookup"><span data-stu-id="edda5-204">-PassThru</span></span>
<span data-ttu-id="edda5-205">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="edda5-205">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="edda5-206">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="edda5-206">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="edda5-207">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="edda5-207">-RunAs32</span></span>
<span data-ttu-id="edda5-208">在 32 位进程中运行计划作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-208">Runs the scheduled job in a 32-bit process.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-209">-RunEvery</span><span class="sxs-lookup"><span data-stu-id="edda5-209">-RunEvery</span></span>

<span data-ttu-id="edda5-210">用于指定运行作业的频率。</span><span class="sxs-lookup"><span data-stu-id="edda5-210">Used to specify how often to run the job.</span></span> <span data-ttu-id="edda5-211">例如，使用此选项可以每隔15分钟运行一次作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-211">For example, use this option to run a job every 15 minutes.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-212">-RunNow</span><span class="sxs-lookup"><span data-stu-id="edda5-212">-RunNow</span></span>
<span data-ttu-id="edda5-213">在运行 **get-scheduledjob** cmdlet 后立即启动作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-213">Starts a job immediately, as soon as the **Set-ScheduledJob** cmdlet is run.</span></span>
<span data-ttu-id="edda5-214">通过使用此参数，使得触发器任务计划程序无需在注册后立即运行 Windows PowerShell 脚本，而且用户无需创建可指定启动日期和时间的触发器。</span><span class="sxs-lookup"><span data-stu-id="edda5-214">This parameter eliminates the need to trigger Task Scheduler to run a Windows PowerShell script immediately after registration, and does not require users to create a trigger that specifies a starting date and time.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-215">-Get-scheduledjoboption</span><span class="sxs-lookup"><span data-stu-id="edda5-215">-ScheduledJobOption</span></span>
<span data-ttu-id="edda5-216">设置计划作业的选项。</span><span class="sxs-lookup"><span data-stu-id="edda5-216">Sets options for the scheduled job.</span></span>
<span data-ttu-id="edda5-217">输入 **ScheduledJobOptions** 对象（例如使用 New-ScheduledJobOption cmdlet 创建的对象）或哈希表值。</span><span class="sxs-lookup"><span data-stu-id="edda5-217">Enter a **ScheduledJobOptions** object, such as one that you create by using the New-ScheduledJobOption cmdlet, or a hash table value.</span></span>

<span data-ttu-id="edda5-218">你可以在注册计划作业时设置计划作业的选项，或者使用 Set-ScheduledJobOption 或 **get-scheduledjob** cmdlet 来设置或更改选项。</span><span class="sxs-lookup"><span data-stu-id="edda5-218">You can set options for a scheduled job when you register the scheduled job or use the Set-ScheduledJobOption or **Set-ScheduledJob** cmdlets to set or change options.</span></span>

<span data-ttu-id="edda5-219">许多选项及其默认值都可确定是否运行计划作业以及运行时间。</span><span class="sxs-lookup"><span data-stu-id="edda5-219">Many of the options and their default values determine whether and when a scheduled job runs.</span></span>
<span data-ttu-id="edda5-220">在计划某个作业之前，务必检查这些选项。</span><span class="sxs-lookup"><span data-stu-id="edda5-220">Be sure to review these options before scheduling a job.</span></span>
<span data-ttu-id="edda5-221">有关计划作业选项（包括默认值）的说明，请参阅 Get-scheduledjoboption。</span><span class="sxs-lookup"><span data-stu-id="edda5-221">For a description of the scheduled job options, including the default values, see New-ScheduledJobOption.</span></span>

<span data-ttu-id="edda5-222">若要提交哈希表，请使用以下键。</span><span class="sxs-lookup"><span data-stu-id="edda5-222">To submit a hash table, use the following keys.</span></span>
<span data-ttu-id="edda5-223">在下列哈希表中，这些键与其默认值一起显示。</span><span class="sxs-lookup"><span data-stu-id="edda5-223">In the following hash table, the keys are shown with their default values.</span></span>

`@{# Power SettingsStartIfOnBattery=$False;StopIfGoingOnBattery=$True; WakeToRun=$False; # Idle SettingsStartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False;# Security settingsShowInTaskScheduler=$TrueRunElevated=$False;# MiscRunWithoutNetwork=$False;DoNotAllowDemandStart=$False;MultipleInstancePolicy=IgnoreNew# Can be IgnoreNew, Parallel, Queue, StopExisting}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-224">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="edda5-224">-ScriptBlock</span></span>
<span data-ttu-id="edda5-225">指定计划作业运行的命令。</span><span class="sxs-lookup"><span data-stu-id="edda5-225">Specifies the commands that the scheduled job runs.</span></span>
<span data-ttu-id="edda5-226">用大括号 ({ }) 括起命令以形成脚本块。</span><span class="sxs-lookup"><span data-stu-id="edda5-226">Enclose the commands in braces ( { } ) to create a script block.</span></span>
<span data-ttu-id="edda5-227">若要指定命令参数的默认值，请使用 *ArgumentList* 参数。</span><span class="sxs-lookup"><span data-stu-id="edda5-227">To specify default values for command parameters, use the *ArgumentList* parameter.</span></span>

<span data-ttu-id="edda5-228">每个 Register-ScheduledJob 命令都必须使用 *ScriptBlock* 或 *FilePath* 参数。</span><span class="sxs-lookup"><span data-stu-id="edda5-228">Every Register-ScheduledJob command must use either the *ScriptBlock* or *FilePath* parameters.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-229">-Trigger</span><span class="sxs-lookup"><span data-stu-id="edda5-229">-Trigger</span></span>
<span data-ttu-id="edda5-230">指定计划作业的触发器。</span><span class="sxs-lookup"><span data-stu-id="edda5-230">Specifies the triggers for the scheduled job.</span></span>
<span data-ttu-id="edda5-231">输入一个或多个 **ScheduledJobTrigger** 对象（例如 New-JobTrigger cmdlet 返回的对象），或者输入一个作业触发器键和值的哈希表。</span><span class="sxs-lookup"><span data-stu-id="edda5-231">Enter one or more **ScheduledJobTrigger** objects, such as the objects that the New-JobTrigger cmdlet returns, or a hash table of job trigger keys and values.</span></span>

<span data-ttu-id="edda5-232">作业触发器在一次性或定期计划或发生事件时自动启动计划作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-232">A job trigger starts a scheduled job automatically on a one-time or recurring scheduled or when an event occurs.</span></span>

<span data-ttu-id="edda5-233">作业触发器是可选的。</span><span class="sxs-lookup"><span data-stu-id="edda5-233">Job triggers are optional.</span></span>
<span data-ttu-id="edda5-234">你可以在创建计划作业时添加触发器，使用 Add-JobTrigger 或 **get-scheduledjob** cmdlet 稍后添加触发器，或使用 Start-Job cmdlet 立即启动计划的作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-234">You can add a trigger when you create the scheduled job, use the Add-JobTrigger or **Set-ScheduledJob** cmdlets to add triggers later, or use the Start-Job cmdlet to start the scheduled job immediately.</span></span>
<span data-ttu-id="edda5-235">你还可以创建和保留没有作业触发器的计划作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-235">You can also create and maintain a scheduled job that has no job triggers.</span></span>

<span data-ttu-id="edda5-236">若要提交哈希表，请使用以下键。</span><span class="sxs-lookup"><span data-stu-id="edda5-236">To submit a hash table, use the following keys.</span></span>

<span data-ttu-id="edda5-237">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (或任意有效的时间字符串) ; `DaysOfWeek="Monday", "Wednesday"` (或星期名称的任意组合) ; `Interval=2` (或任何有效频率间隔) ; `RandomDelay="30minutes"` (或任意有效的 timespan 字符串) ; `User="Domain1\User01"` (或任意有效的用户;仅与 AtLogon frequency 值一起使用) </span><span class="sxs-lookup"><span data-stu-id="edda5-237">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (or any valid time string); `DaysOfWeek="Monday", "Wednesday"` (or any combination of day names); `Interval=2` (or any valid frequency interval); `RandomDelay="30minutes"` (or any valid timespan string); `User="Domain1\User01"` (or any valid user; used only with the AtLogon frequency value)</span></span>

<span data-ttu-id="edda5-238">}</span><span class="sxs-lookup"><span data-stu-id="edda5-238">}</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edda5-239">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="edda5-239">CommonParameters</span></span>
<span data-ttu-id="edda5-240">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="edda5-240">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="edda5-241">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="edda5-241">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="edda5-242">输入</span><span class="sxs-lookup"><span data-stu-id="edda5-242">INPUTS</span></span>

### <span data-ttu-id="edda5-243">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="edda5-243">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="edda5-244">你可以通过管道将计划作业传递给 **Set-ScheduledJob** 。</span><span class="sxs-lookup"><span data-stu-id="edda5-244">You can pipe scheduled jobs to **Set-ScheduledJob** .</span></span>

## <span data-ttu-id="edda5-245">输出</span><span class="sxs-lookup"><span data-stu-id="edda5-245">OUTPUTS</span></span>

### <span data-ttu-id="edda5-246">无或 Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="edda5-246">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="edda5-247">如果你使用 *Passthru* 参数，则 **Set-ScheduledJob** 将返回已更改的计划作业。</span><span class="sxs-lookup"><span data-stu-id="edda5-247">If you use the *Passthru* parameter, **Set-ScheduledJob** returns the scheduled job that was changed.</span></span>
<span data-ttu-id="edda5-248">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="edda5-248">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="edda5-249">注释</span><span class="sxs-lookup"><span data-stu-id="edda5-249">NOTES</span></span>

## <span data-ttu-id="edda5-250">相关链接</span><span class="sxs-lookup"><span data-stu-id="edda5-250">RELATED LINKS</span></span>

[<span data-ttu-id="edda5-251">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="edda5-251">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="edda5-252">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="edda5-252">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="edda5-253">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="edda5-253">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="edda5-254">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="edda5-254">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="edda5-255">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="edda5-255">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="edda5-256">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="edda5-256">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="edda5-257">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="edda5-257">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="edda5-258">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="edda5-258">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="edda5-259">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="edda5-259">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="edda5-260">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="edda5-260">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="edda5-261">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="edda5-261">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="edda5-262">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="edda5-262">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="edda5-263">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="edda5-263">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="edda5-264">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="edda5-264">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="edda5-265">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="edda5-265">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="edda5-266">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="edda5-266">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
