---
ms.date: 09/13/2016
ms.topic: reference
title: 后台作业
description: 后台作业
ms.openlocfilehash: 5478789a2ee1f2eabc71a46673e3a707643cdba8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648611"
---
# <a name="background-jobs"></a><span data-ttu-id="81a22-103">后台作业</span><span class="sxs-lookup"><span data-stu-id="81a22-103">Background Jobs</span></span>

<span data-ttu-id="81a22-104">Cmdlet 可以在内部执行其操作，也可以用作 Windows PowerShell *后台作业*。</span><span class="sxs-lookup"><span data-stu-id="81a22-104">Cmdlets can perform their action internally or as a Windows PowerShell *background job*.</span></span> <span data-ttu-id="81a22-105">当某个 cmdlet 作为后台作业运行时，将以异步方式在独立于该 cmdlet 使用的管道线程的单独线程中完成工作。</span><span class="sxs-lookup"><span data-stu-id="81a22-105">When a cmdlet runs as a background job, the work is done asynchronously in its own thread separate from the pipeline thread that the cmdlet is using.</span></span> <span data-ttu-id="81a22-106">从用户的角度来看，当某个 cmdlet 作为后台作业运行时，命令提示符会立即返回，即使该作业需要很长时间才能完成，并且在运行作业时，用户可以继续而不中断。</span><span class="sxs-lookup"><span data-stu-id="81a22-106">From the user perspective, when a cmdlet runs as a background job, the command prompt returns immediately even if the job takes an extended amount of time to complete, and the user can continue without interruption while the job runs.</span></span>

## <a name="background-jobs-child-jobs-and-the-job-repository"></a><span data-ttu-id="81a22-107">后台作业、子作业和作业存储库</span><span class="sxs-lookup"><span data-stu-id="81a22-107">Background Jobs, Child Jobs, and the Job Repository</span></span>

<span data-ttu-id="81a22-108">支持后台作业的 cmdlet 返回的作业对象定义作业。</span><span class="sxs-lookup"><span data-stu-id="81a22-108">The job object that is returned by the cmdlets that support background jobs defines the job.</span></span> <span data-ttu-id="81a22-109"> ([启动作业](/powershell/module/Microsoft.PowerShell.Core/Start-Job) cmdlet 还会返回一个作业对象。 ) 作业的名称、用于指定作业的标识符、状态信息以及子作业包含在此定义中。</span><span class="sxs-lookup"><span data-stu-id="81a22-109">(The [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) cmdlet also returns a job object.) The name of the job, an identifier that is used to specify the job, the state information, and the child jobs are included in this definition.</span></span> <span data-ttu-id="81a22-110">作业不执行任何工作。</span><span class="sxs-lookup"><span data-stu-id="81a22-110">The job does not perform any of the work.</span></span> <span data-ttu-id="81a22-111">每个后台作业至少有一个子作业，因为子作业执行实际工作。</span><span class="sxs-lookup"><span data-stu-id="81a22-111">Each background job has at least one child job because the child job performs the actual work.</span></span> <span data-ttu-id="81a22-112">当你运行 cmdlet 以便以后台作业的形式执行工作时，该 cmdlet 必须将作业和子作业添加到公共存储库（称为 *作业存储库*）。</span><span class="sxs-lookup"><span data-stu-id="81a22-112">When you run a cmdlet so that the work is performed as a background job, the cmdlet must add the job and the child jobs to a common repository, referred to as the *job repository*.</span></span>

<span data-ttu-id="81a22-113">有关如何在命令行中处理后台作业的详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="81a22-113">For more information about how background jobs are handled at the command line, see the following:</span></span>

- [<span data-ttu-id="81a22-114">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="81a22-114">about_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [<span data-ttu-id="81a22-115">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="81a22-115">about_Job_Details</span></span>](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [<span data-ttu-id="81a22-116">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="81a22-116">about_Remote_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a><span data-ttu-id="81a22-117">编写作为后台作业运行的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="81a22-117">Writing a Cmdlet That Runs as a Background Job</span></span>

<span data-ttu-id="81a22-118">若要编写可作为后台作业运行的 cmdlet，必须完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="81a22-118">To write a cmdlet that can be run as a background job, you must complete the following tasks:</span></span>

- <span data-ttu-id="81a22-119">定义 `asJob` 开关参数，使用户可以决定是否将该 cmdlet 作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="81a22-119">Define an `asJob` switch parameter so that the user can decide whether to run the cmdlet as a background job.</span></span>

- <span data-ttu-id="81a22-120">创建一个派生自 [system.object](/dotnet/api/System.Management.Automation.Job) 类的对象。</span><span class="sxs-lookup"><span data-stu-id="81a22-120">Create an object that derives from the [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) class.</span></span> <span data-ttu-id="81a22-121">此对象可以是自定义作业对象，也可以是 Windows PowerShell 提供的作业对象，例如 [Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) 对象。</span><span class="sxs-lookup"><span data-stu-id="81a22-121">This object can be a custom job object or a job object provided by Windows PowerShell, such as a [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) object.</span></span>

- <span data-ttu-id="81a22-122">在记录处理方法中，添加一个 `if` 语句来检测该 cmdlet 是否应作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="81a22-122">In a record processing method, add an `if` statement that detects whether the cmdlet should run as a background job.</span></span>

- <span data-ttu-id="81a22-123">对于自定义作业对象，请实现 job 类。</span><span class="sxs-lookup"><span data-stu-id="81a22-123">For custom job objects, implement the job class.</span></span>

- <span data-ttu-id="81a22-124">返回相应的对象，具体取决于 cmdlet 是否作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="81a22-124">Return the appropriate objects, depending on whether the cmdlet is run as a background job.</span></span>

<span data-ttu-id="81a22-125">有关代码示例，请参阅 [如何支持作业](./how-to-support-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="81a22-125">For a code example, see [How to Support Jobs](./how-to-support-jobs.md).</span></span>

## <a name="background-job-related-apis"></a><span data-ttu-id="81a22-126">后台 Job-Related Api</span><span class="sxs-lookup"><span data-stu-id="81a22-126">Background Job-Related APIs</span></span>

<span data-ttu-id="81a22-127">Windows PowerShell 提供以下 Api 来管理后台作业。</span><span class="sxs-lookup"><span data-stu-id="81a22-127">The following APIs are provided by Windows PowerShell to manage background jobs.</span></span>

<span data-ttu-id="81a22-128">[System.web](/dotnet/api/System.Management.Automation.Job) 派生自定义作业对象。</span><span class="sxs-lookup"><span data-stu-id="81a22-128">[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) Derives custom job objects.</span></span> <span data-ttu-id="81a22-129">这是一个抽象类。</span><span class="sxs-lookup"><span data-stu-id="81a22-129">This is an abstract class.</span></span>

<span data-ttu-id="81a22-130">[Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) 管理并提供有关当前活动的后台作业的信息。</span><span class="sxs-lookup"><span data-stu-id="81a22-130">[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) Manages and provides information about the current active background jobs.</span></span>

<span data-ttu-id="81a22-131">[Jobstate](/dotnet/api/System.Management.Automation.JobState) 用于定义后台作业的状态。</span><span class="sxs-lookup"><span data-stu-id="81a22-131">[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState) Defines the state of the background job.</span></span> <span data-ttu-id="81a22-132">状态包括 "已启动"、"正在运行" 和 "已停止"。</span><span class="sxs-lookup"><span data-stu-id="81a22-132">States include Started, Running, and Stopped.</span></span>

<span data-ttu-id="81a22-133">[Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) 提供有关后台作业状态的信息，并且，如果上次状态更改是由错误引起的，则该作业进入其当前状态的原因。</span><span class="sxs-lookup"><span data-stu-id="81a22-133">[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) Provides information about the state of a background job and, if the last state change was caused by an error, the reason the job entered its current state.</span></span>

<span data-ttu-id="81a22-134">[Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) 提供在后台作业更改状态时引发的事件的参数。</span><span class="sxs-lookup"><span data-stu-id="81a22-134">[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) Provides the arguments for an event that is raised when a background job changes state.</span></span>

## <a name="windows-powershell-job-cmdlets"></a><span data-ttu-id="81a22-135">Windows PowerShell 作业 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="81a22-135">Windows PowerShell Job Cmdlets</span></span>

<span data-ttu-id="81a22-136">Windows PowerShell 提供以下 cmdlet 来管理后台作业。</span><span class="sxs-lookup"><span data-stu-id="81a22-136">The following cmdlets are provided by Windows PowerShell to manage background jobs.</span></span>

[<span data-ttu-id="81a22-137">Get-Job</span><span class="sxs-lookup"><span data-stu-id="81a22-137">Get-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

<span data-ttu-id="81a22-138">获取在当前会话中运行的 Windows PowerShell 后台作业。</span><span class="sxs-lookup"><span data-stu-id="81a22-138">Gets Windows PowerShell background jobs that are running in the current session.</span></span>

[<span data-ttu-id="81a22-139">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="81a22-139">Receive-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

<span data-ttu-id="81a22-140">获取当前会话中的 Windows PowerShell 后台作业的结果。</span><span class="sxs-lookup"><span data-stu-id="81a22-140">Gets the results of the Windows PowerShell background jobs in the current session.</span></span>

[<span data-ttu-id="81a22-141">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="81a22-141">Remove-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

<span data-ttu-id="81a22-142">删除 Windows PowerShell 后台作业。</span><span class="sxs-lookup"><span data-stu-id="81a22-142">Deletes a Windows PowerShell background job.</span></span>

[<span data-ttu-id="81a22-143">Start-Job</span><span class="sxs-lookup"><span data-stu-id="81a22-143">Start-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

<span data-ttu-id="81a22-144">启动 Windows PowerShell 后台作业。</span><span class="sxs-lookup"><span data-stu-id="81a22-144">Starts a Windows PowerShell background job.</span></span>

[<span data-ttu-id="81a22-145">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="81a22-145">Stop-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

<span data-ttu-id="81a22-146">停止 Windows PowerShell 后台作业。</span><span class="sxs-lookup"><span data-stu-id="81a22-146">Stops a Windows PowerShell background job.</span></span>

[<span data-ttu-id="81a22-147">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="81a22-147">Wait-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

<span data-ttu-id="81a22-148">禁止显示命令提示符，直到在会话中运行的一个或全部 Windows PowerShell 后台作业完成。</span><span class="sxs-lookup"><span data-stu-id="81a22-148">Suppresses the command prompt until one or all of the Windows PowerShell background jobs running in the session are complete.</span></span>

## <a name="see-also"></a><span data-ttu-id="81a22-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81a22-149">See Also</span></span>

[<span data-ttu-id="81a22-150">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="81a22-150">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
