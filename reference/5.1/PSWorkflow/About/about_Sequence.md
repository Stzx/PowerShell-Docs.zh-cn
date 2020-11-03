---
description: 描述 `Sequence` 按顺序运行所选活动的关键字。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_sequence?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Sequence
ms.openlocfilehash: a9dd4fb24274fe4e1478ca69c734b43a2f196792
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199901"
---
# <a name="about-sequence"></a><span data-ttu-id="73699-104">关于序列</span><span class="sxs-lookup"><span data-stu-id="73699-104">About Sequence</span></span>

## <a name="short-description"></a><span data-ttu-id="73699-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="73699-105">Short description</span></span>

<span data-ttu-id="73699-106">描述 `Sequence` 按顺序运行所选活动的关键字。</span><span class="sxs-lookup"><span data-stu-id="73699-106">Describes the `Sequence` keyword that runs selected activities sequentially.</span></span>

## <a name="long-description"></a><span data-ttu-id="73699-107">长说明</span><span class="sxs-lookup"><span data-stu-id="73699-107">Long description</span></span>

<span data-ttu-id="73699-108">`Sequence`关键字按顺序运行所选工作流活动。</span><span class="sxs-lookup"><span data-stu-id="73699-108">The `Sequence` keyword runs selected workflow activities sequentially.</span></span> <span data-ttu-id="73699-109">工作流活动将按它们出现的顺序运行，而不会同时运行。</span><span class="sxs-lookup"><span data-stu-id="73699-109">Workflow activities run in the order that they appear and do not run concurrently.</span></span> <span data-ttu-id="73699-110">`Sequence`关键字仅在 PowerShell 工作流中有效。</span><span class="sxs-lookup"><span data-stu-id="73699-110">The `Sequence` keyword is only valid in a PowerShell Workflow.</span></span>

<span data-ttu-id="73699-111">`Sequence`关键字用于在 `Parallel` 脚本块中按顺序运行所选的命令。</span><span class="sxs-lookup"><span data-stu-id="73699-111">The `Sequence` keyword is used in a `Parallel` script block to run selected commands sequentially.</span></span>

<span data-ttu-id="73699-112">由于工作流活动默认按顺序运行，因此 `Sequence` 关键字只在 `Parallel` 脚本块中有效。</span><span class="sxs-lookup"><span data-stu-id="73699-112">Because workflow activities run sequentially by default, the `Sequence` keyword is only effective in a `Parallel` script block.</span></span> <span data-ttu-id="73699-113">如果 `Sequence` 脚本块中未包含关键字 `Parallel` ，则该关键字有效但无效。</span><span class="sxs-lookup"><span data-stu-id="73699-113">If the `Sequence` keyword isn't included in a `Parallel` script block, it's valid but ineffective.</span></span>

<span data-ttu-id="73699-114">脚本块允许你按 `Sequence` 顺序运行多个命令，从而使你能够并行运行更多命令。</span><span class="sxs-lookup"><span data-stu-id="73699-114">The `Sequence` script block lets you run more commands in parallel by allowing you to run dependent commands sequentially.</span></span>

## <a name="syntax"></a><span data-ttu-id="73699-115">语法</span><span class="sxs-lookup"><span data-stu-id="73699-115">Syntax</span></span>

### <a name="workflow-using-sequence"></a><span data-ttu-id="73699-116">使用序列的工作流</span><span class="sxs-lookup"><span data-stu-id="73699-116">Workflow using Sequence</span></span>

```
workflow <Verb-Noun>
{
    Sequence
    {
        [<Activity>]
        [<Activity>]
        # ...
    }
}
```

### <a name="workflow-using-parallel-and-sequence"></a><span data-ttu-id="73699-117">使用并行和序列的工作流</span><span class="sxs-lookup"><span data-stu-id="73699-117">Workflow using Parallel and Sequence</span></span>

```
workflow <Verb-Noun>
{
    Parallel
    {
        [<Activity>]
        Sequence
        {
            [<Activity>]
            [<Activity>]
            # ...
        }
    }
}
```

## <a name="detailed-description"></a><span data-ttu-id="73699-118">详细说明</span><span class="sxs-lookup"><span data-stu-id="73699-118">Detailed description</span></span>

<span data-ttu-id="73699-119">`Parallel` 脚本块中的命令可以并发运行。</span><span class="sxs-lookup"><span data-stu-id="73699-119">The commands in a `Parallel` script block can run concurrently.</span></span> <span data-ttu-id="73699-120">它们运行的顺序不确定。</span><span class="sxs-lookup"><span data-stu-id="73699-120">The order in which they run is not determined.</span></span> <span data-ttu-id="73699-121">此功能可提高脚本工作流的性能。</span><span class="sxs-lookup"><span data-stu-id="73699-121">This feature improves the performance of a script workflow.</span></span>

<span data-ttu-id="73699-122">您可以使用 `Sequence` 脚本块按顺序运行所选的活动，即使活动出现在 `Parallel` 脚本块中。</span><span class="sxs-lookup"><span data-stu-id="73699-122">You can use a `Sequence` script block to run selected activities sequentially, even though the activities appear in a `Parallel` script block.</span></span>

<span data-ttu-id="73699-123">脚本块中的活动 `Sequence` 会按它们列出的顺序连续运行。</span><span class="sxs-lookup"><span data-stu-id="73699-123">The activities in a `Sequence` script block run consecutively in the order that they are listed.</span></span> <span data-ttu-id="73699-124">脚本块中的活动 `Sequence` 仅在上一个活动完成后开始。</span><span class="sxs-lookup"><span data-stu-id="73699-124">An activity in a `Sequence` script block starts only after the previous activity completes.</span></span>

<span data-ttu-id="73699-125">但是，当脚本块 `Sequence` 出现在 `Parallel` 脚本块中时， `Sequence` 脚本块运行的顺序并不确定。</span><span class="sxs-lookup"><span data-stu-id="73699-125">However, when the `Sequence` script block appears in a `Parallel` script block, the order in which the `Sequence` script block runs isn't determined.</span></span> <span data-ttu-id="73699-126">它可能会在脚本块中的其他活动之前、之后或并发运行 `Parallel` 。</span><span class="sxs-lookup"><span data-stu-id="73699-126">It might run before, after, or concurrent with other activities in the `Parallel` script block.</span></span>

<span data-ttu-id="73699-127">例如，以下工作流包括 `Parallel` 运行获取计算机上的进程和服务的活动的脚本块。</span><span class="sxs-lookup"><span data-stu-id="73699-127">For example, the following workflow includes a `Parallel` script block that runs activities that get processes and services on the computer.</span></span> <span data-ttu-id="73699-128">`Parallel`脚本块包含一个 `Sequence` 脚本块，该脚本块从文件中获取信息并使用该信息作为脚本的输入。</span><span class="sxs-lookup"><span data-stu-id="73699-128">The `Parallel` script block contains a `Sequence` script block that gets information from a file and uses the information as input to a script.</span></span>

<span data-ttu-id="73699-129">`Get-Process`、 `Get-Service` 和与修补程序相关的命令彼此独立。</span><span class="sxs-lookup"><span data-stu-id="73699-129">The `Get-Process`, `Get-Service`, and hotfix-related commands are independent of each other.</span></span> <span data-ttu-id="73699-130">命令可以同时或按任何顺序运行。</span><span class="sxs-lookup"><span data-stu-id="73699-130">The commands can run concurrently or in any order.</span></span> <span data-ttu-id="73699-131">但是，获取修补程序信息的命令必须在使用该信息的命令之前运行。</span><span class="sxs-lookup"><span data-stu-id="73699-131">But, the command that gets the hotfix information must run before the command that uses it.</span></span>

```powershell
workflow Test-Workflow
{
    Parallel
    {
    Get-Process
    Get-Service

    Sequence
    {
        $Hotfix = Get-Content 'D:\HotFixes\Required.txt'
        Foreach ($h in $Hotfix) {'D:\Scripts\Verify-Hotfix' -Hotfix $h}
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="73699-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73699-132">See also</span></span>

[<span data-ttu-id="73699-133">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="73699-133">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[<span data-ttu-id="73699-134">about_ForEach 并行</span><span class="sxs-lookup"><span data-stu-id="73699-134">about_ForEach-Parallel</span></span>](about_ForEach-Parallel.md)

[<span data-ttu-id="73699-135">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="73699-135">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="73699-136">about_Parallel</span><span class="sxs-lookup"><span data-stu-id="73699-136">about_Parallel</span></span>](about_Parallel.md)

[<span data-ttu-id="73699-137">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="73699-137">about_Workflows</span></span>](about_Workflows.md)

[<span data-ttu-id="73699-138">使用 Windows PowerShell 脚本创建工作流</span><span class="sxs-lookup"><span data-stu-id="73699-138">Creating a Workflow by Using a Windows PowerShell Script</span></span>](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)
