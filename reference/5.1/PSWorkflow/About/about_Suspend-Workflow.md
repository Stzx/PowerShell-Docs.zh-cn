---
description: 描述 `Suspend-Workflow` 活动，该活动将挂起活动显示的工作流。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_suspend-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Suspend 工作流
ms.openlocfilehash: cbe5386ae5aa4bd863079fde240ddf2ce5384727
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199896"
---
# <a name="about-suspend-workflow"></a><span data-ttu-id="25d83-104">关于 Suspend-Workflow</span><span class="sxs-lookup"><span data-stu-id="25d83-104">About Suspend-Workflow</span></span>

## <a name="short-description"></a><span data-ttu-id="25d83-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="25d83-105">Short description</span></span>

<span data-ttu-id="25d83-106">描述 `Suspend-Workflow` 活动，该活动将挂起活动显示的工作流。</span><span class="sxs-lookup"><span data-stu-id="25d83-106">Describes the `Suspend-Workflow` activity, which suspends the workflow in which the activity appears.</span></span>

## <a name="long-description"></a><span data-ttu-id="25d83-107">长说明</span><span class="sxs-lookup"><span data-stu-id="25d83-107">Long description</span></span>

<span data-ttu-id="25d83-108">`Suspend-Workflow`活动从工作流中暂时停止工作流处理。</span><span class="sxs-lookup"><span data-stu-id="25d83-108">The `Suspend-Workflow` activity temporarily stops workflow processing from within the workflow.</span></span> <span data-ttu-id="25d83-109">在挂起之前，Windows PowerShell 工作流将采用一个检查点，以便保留工作流的状态和数据，并且工作流可以从挂起点恢复。</span><span class="sxs-lookup"><span data-stu-id="25d83-109">Before suspending, Windows PowerShell Workflow takes a checkpoint so the workflow's state and data are preserved and the workflow can resume from the suspension point.</span></span>

<span data-ttu-id="25d83-110">若要恢复工作流，运行工作流的用户将使用 `Resume-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25d83-110">To resume the workflow, the user running the workflow uses the `Resume-Job` cmdlet.</span></span> <span data-ttu-id="25d83-111">无法从工作流中恢复工作流。</span><span class="sxs-lookup"><span data-stu-id="25d83-111">You can't resume a workflow from within the workflow.</span></span>

## <a name="syntax"></a><span data-ttu-id="25d83-112">语法</span><span class="sxs-lookup"><span data-stu-id="25d83-112">Syntax</span></span>

```
workflow <Verb-Noun>
{
    Suspend-Workflow
}
```

## <a name="detailed-description"></a><span data-ttu-id="25d83-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="25d83-113">Detailed description</span></span>

<span data-ttu-id="25d83-114">`Suspend-Workflow`暂时停止工作流并返回表示工作流作业的作业对象。</span><span class="sxs-lookup"><span data-stu-id="25d83-114">The `Suspend-Workflow` temporarily stops the workflow and returns a job object that represents the workflow job.</span></span> <span data-ttu-id="25d83-115">即使未将工作流作为作业运行，也会返回一个作业对象。</span><span class="sxs-lookup"><span data-stu-id="25d83-115">A job object is returned even if you didn't run the workflow as a job.</span></span> <span data-ttu-id="25d83-116">例如，使用 **AsJob** 工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="25d83-116">For example, such as by using the **AsJob** workflow common parameter.</span></span> <span data-ttu-id="25d83-117">作业状态为 "已 **挂起** "。</span><span class="sxs-lookup"><span data-stu-id="25d83-117">The job state is **Suspended** .</span></span>

<span data-ttu-id="25d83-118">可以使用作业 cmdlet 来管理挂起的工作流作业。</span><span class="sxs-lookup"><span data-stu-id="25d83-118">You can use the job cmdlets to manage the suspended workflow job.</span></span> <span data-ttu-id="25d83-119">若要恢复工作流作业，请使用 `Resume-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25d83-119">To resume the workflow job, use the `Resume-Job` cmdlet.</span></span>

<span data-ttu-id="25d83-120">在恢复工作流作业时，工作流将继续执行活动后面的命令 `Suspend-Workflow` 。</span><span class="sxs-lookup"><span data-stu-id="25d83-120">When you resume the workflow job, the workflow resumes at the command that follows the `Suspend-Workflow` activity.</span></span>

<span data-ttu-id="25d83-121">例如，以下工作流包括 `Suspend-Workflow` 活动。</span><span class="sxs-lookup"><span data-stu-id="25d83-121">For example, the following workflow includes the `Suspend-Workflow` activity.</span></span>
<span data-ttu-id="25d83-122">运行工作流时，它会运行该 `Get-Date` 活动，将其输出保存到 `$a` 变量中，然后挂起工作流，并返回一个作业对象，该对象表示挂起的工作流。</span><span class="sxs-lookup"><span data-stu-id="25d83-122">When you run the workflow, it runs the `Get-Date` activity, saves its output in the `$a` variable, and then suspends the workflow, and returns a job object that represents the suspended workflow.</span></span> <span data-ttu-id="25d83-123">作业类型为 **PSWorkflowJob** 。</span><span class="sxs-lookup"><span data-stu-id="25d83-123">The job type is **PSWorkflowJob** .</span></span>

<span data-ttu-id="25d83-124">可以使用作业 cmdlet （如 `Get-Job` ）来管理工作流作业。</span><span class="sxs-lookup"><span data-stu-id="25d83-124">You can use the job cmdlets, such as `Get-Job`, to manage the workflow job.</span></span>

```powershell
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

Test-Suspend
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Suspended  True         localhost Test-Suspend
```

## <a name="resuming-a-workflow-job"></a><span data-ttu-id="25d83-125">恢复工作流作业</span><span class="sxs-lookup"><span data-stu-id="25d83-125">Resuming a workflow job</span></span>

<span data-ttu-id="25d83-126">若要恢复工作流作业，请使用 `Resume-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25d83-126">To resume the workflow job, use the `Resume-Job` cmdlet.</span></span> <span data-ttu-id="25d83-127">`Resume-Job` cmdlet 会立即返回工作流作业对象（即使它可能尚未恢复）。</span><span class="sxs-lookup"><span data-stu-id="25d83-127">The `Resume-Job` cmdlet returns the workflow job object immediately, even though it might not yet be resumed.</span></span> <span data-ttu-id="25d83-128">要等待作业恢复，请使用 **wait** 参数，或使用 `Get-Job` cmdlet 获取当前作业对象。</span><span class="sxs-lookup"><span data-stu-id="25d83-128">To wait for the job to be resumed, use the **Wait** parameter, or use the `Get-Job` cmdlet to get the current job object.</span></span>

```powershell
Resume-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State    HasMoreData  Location  Command
--  ----  -------------  -----    -----------  --------  -------
8   Job8  PSWorkflowJob  Running  True         localhost Test-Suspend
```

```powershell
Get-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Completed  True         localhost Test-Suspend
```

## <a name="getting-the-output-of-a-workflow-job"></a><span data-ttu-id="25d83-129">获取工作流作业的输出</span><span class="sxs-lookup"><span data-stu-id="25d83-129">Getting the output of a workflow job</span></span>

<span data-ttu-id="25d83-130">若要获取工作流作业的输出，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25d83-130">To get the output of a workflow job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="25d83-131">输出显示工作流已在遵循 cmdlet 的命令处恢复 `Suspend-Workflow` 。</span><span class="sxs-lookup"><span data-stu-id="25d83-131">The output shows that the workflow resumed at the command that followed the `Suspend-Workflow` cmdlet.</span></span> <span data-ttu-id="25d83-132">在 `$a` 挂起之前填充的变量的值可在工作流恢复时使用。</span><span class="sxs-lookup"><span data-stu-id="25d83-132">The value of the `$a` variable, which was populated before the suspension, is available to the workflow when it resumes.</span></span>

```powershell
Get-Job -Name Job8 | Receive-Job
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 19
Milliseconds      : 823
Ticks             : 198230041
TotalDays         : 0.000229432917824074
TotalHours        : 0.00550639002777778
TotalMinutes      : 0.330383401666667
TotalSeconds      : 19.8230041
TotalMilliseconds : 19823.0041
PSComputerName    : localhost
```

## <a name="see-also"></a><span data-ttu-id="25d83-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25d83-133">See also</span></span>

[<span data-ttu-id="25d83-134">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="25d83-134">about_Workflows</span></span>](about_Workflows.md)

[<span data-ttu-id="25d83-135">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="25d83-135">about_WorkflowCommonParameters</span></span>](about_WorkflowCommonParameters.md)

<span data-ttu-id="25d83-136">[PSWorkflow](xref:PSWorkflow) cmdlet</span><span class="sxs-lookup"><span data-stu-id="25d83-136">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="25d83-137">工作流指南</span><span class="sxs-lookup"><span data-stu-id="25d83-137">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="25d83-138">编写 Windows PowerShell 工作流</span><span class="sxs-lookup"><span data-stu-id="25d83-138">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
