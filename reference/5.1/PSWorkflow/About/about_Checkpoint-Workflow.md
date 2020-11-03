---
description: 介绍 Checkpoint-Workflow 活动，该活动在工作流中采用检查点。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_checkpoint-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Checkpoint 工作流
ms.openlocfilehash: 223deb07ff6ed387cf04736116ea0ce3f998bb59
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199908"
---
# <a name="about-checkpoint-workflow"></a><span data-ttu-id="5f697-104">关于 Checkpoint-Workflow</span><span class="sxs-lookup"><span data-stu-id="5f697-104">About Checkpoint-Workflow</span></span>

## <a name="short-description"></a><span data-ttu-id="5f697-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="5f697-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="5f697-106">介绍 Checkpoint-Workflow 活动，该活动在工作流中采用检查点。</span><span class="sxs-lookup"><span data-stu-id="5f697-106">Describes the Checkpoint-Workflow activity, which takes a checkpoint in a workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="5f697-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="5f697-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="5f697-108">Checkpoint-Workflow 活动采用一个检查点，用于保存工作流中的状态和数据。</span><span class="sxs-lookup"><span data-stu-id="5f697-108">The Checkpoint-Workflow activity takes a checkpoint, which saves state and data in the workflow.</span></span> <span data-ttu-id="5f697-109">如果工作流被挂起或中断，它可以从最新的检查点恢复，而无需重新启动。</span><span class="sxs-lookup"><span data-stu-id="5f697-109">If the workflow is suspended or interrupted, it can be resumed from the most recent checkpoint, rather than having to be restarted.</span></span>

<span data-ttu-id="5f697-110">Checkpoint-Workflow 活动仅在工作流中有效。</span><span class="sxs-lookup"><span data-stu-id="5f697-110">The Checkpoint-Workflow activity is valid only in a workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="5f697-111">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5f697-111">SYNTAX</span></span>

```
Workflow <Verb-Noun>
{
    Checkpoint-Workflow
}
```

<span data-ttu-id="5f697-112">Checkpoint-Workflow 活动不接受任何参数，包括通用参数和工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5f697-112">The Checkpoint-Workflow activity does not accept any parameters, including common parameters and workflow common parameters.</span></span>

<span data-ttu-id="5f697-113">可以将 Checkpoint-Activity 检查点放在工作流中 CmdletBinding 或 Param 语句之后的任何位置。</span><span class="sxs-lookup"><span data-stu-id="5f697-113">You can place the Checkpoint-Activity checkpoint anywhere in a workflow after the CmdletBinding or Param statement.</span></span> <span data-ttu-id="5f697-114">但是，在放置检查点时，请考虑收集数据并将其写入到运行工作流的计算机上的磁盘的性能成本。</span><span class="sxs-lookup"><span data-stu-id="5f697-114">However, when placing checkpoints, consider the performance cost of collecting the data and writing it to disk on the computer that is running the workflow.</span></span>

<span data-ttu-id="5f697-115">请确保中断后重新运行工作流某一部分所需的时间大于将检查点状态和数据写入磁盘所需的时间。</span><span class="sxs-lookup"><span data-stu-id="5f697-115">Be sure that the time it takes to rerun a section of the workflow if it is interrupted is greater than the time it takes to write the checkpoint state and data to disk.</span></span>

<span data-ttu-id="5f697-116">请考虑在关键步骤之后采用检查点，使工作流可以恢复，而不是重新启动。</span><span class="sxs-lookup"><span data-stu-id="5f697-116">Consider taking checkpoints after critical steps so the workflow can be resumed rather than restarted.</span></span> <span data-ttu-id="5f697-117">例如，在不是幂等的命令后生成一个检查点。</span><span class="sxs-lookup"><span data-stu-id="5f697-117">For example, take a checkpoint after commands that are not idempotent.</span></span>

### <a name="about-checkpoints"></a><span data-ttu-id="5f697-118">关于检查点</span><span class="sxs-lookup"><span data-stu-id="5f697-118">ABOUT CHECKPOINTS</span></span>

<span data-ttu-id="5f697-119">检查点 是工作流当前状态的快照，其中包括变量的当前值以及在该点生成的任何输出，它会将这些信息保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="5f697-119">A checkpoint is a snapshot of the current state of the workflow, including the current values of variables, and any output generated up to that point, and it saves it to disk.</span></span>

<span data-ttu-id="5f697-120">如果工作流被有意或无意地中断，则 Windows PowerShell 工作流会自动使用最新的检查点中的数据来恢复和恢复工作流。</span><span class="sxs-lookup"><span data-stu-id="5f697-120">If a workflow is interrupted, intentionally or unintentionally, Windows PowerShell Workflow automatically uses the data in newest checkpoint to recover and resume the workflow.</span></span>

<span data-ttu-id="5f697-121">将工作流作为作业运行时，例如通过使用 AsJob 工作流通用参数，将保留工作流检查点，直到删除作业，例如通过使用 Remove-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5f697-121">When you run the workflow as a job, such as by using the AsJob workflow common parameter, the workflow checkpoints are retained until you delete the job, such as by using the Remove-Job cmdlet.</span></span>
<span data-ttu-id="5f697-122">否则，工作流检查点将在工作流完成时删除。</span><span class="sxs-lookup"><span data-stu-id="5f697-122">Otherwise, workflow checkpoints are deleted when the workflow completes.</span></span>

### <a name="other-checkpointing-techniques"></a><span data-ttu-id="5f697-123">其他检查点技术</span><span class="sxs-lookup"><span data-stu-id="5f697-123">OTHER CHECKPOINTING TECHNIQUES</span></span>

<span data-ttu-id="5f697-124">除了 Checkpoint-Workflow 活动，Windows PowerShell 工作流还支持其他检查点技术，其中包括：</span><span class="sxs-lookup"><span data-stu-id="5f697-124">In addition to the Checkpoint-Workflow activity, Windows PowerShell Workflow supports other checkpointing techniques, including the following:</span></span>

- <span data-ttu-id="5f697-125">PSPersist 工作流通用参数</span><span class="sxs-lookup"><span data-stu-id="5f697-125">PSPersist workflow common parameter</span></span>
- <span data-ttu-id="5f697-126">PSPersist 活动通用参数</span><span class="sxs-lookup"><span data-stu-id="5f697-126">PSPersist activity common parameter</span></span>
- <span data-ttu-id="5f697-127">工作流中的 PSPersistPreference 变量 () </span><span class="sxs-lookup"><span data-stu-id="5f697-127">PSPersistPreference variable (in a workflow)</span></span>

<span data-ttu-id="5f697-128">有关向工作流添加检查点的详细信息，请参阅 "如何向工作流添加检查点"。</span><span class="sxs-lookup"><span data-stu-id="5f697-128">For more information about adding a checkpoint to a workflow, see "How to Add Checkpoints to a Workflow."</span></span>

## <a name="examples"></a><span data-ttu-id="5f697-129">示例</span><span class="sxs-lookup"><span data-stu-id="5f697-129">EXAMPLES</span></span>

<span data-ttu-id="5f697-130">以下工作流包括在完成长时间运行的函数后调用 Checkpoint-Workflow 活动，以及一个共享数据的脚本。</span><span class="sxs-lookup"><span data-stu-id="5f697-130">The following workflow includes a call to the Checkpoint-Workflow activity after completing a long-running function and a script that share data.</span></span>

```powershell
Workflow Test-Workflow
{
    $a = Invoke-LongRunningFunction
    InlineScript { \\Server\Share\Get-DataPacks.ps1 $Using:a}
    Checkpoint-Workflow

    Invoke-LongRunningFunction
    {
        ...
    }
}
```

## <a name="see-also"></a><span data-ttu-id="5f697-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f697-131">SEE ALSO</span></span>

[<span data-ttu-id="5f697-132">编写 Windows PowerShell 工作流</span><span class="sxs-lookup"><span data-stu-id="5f697-132">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
