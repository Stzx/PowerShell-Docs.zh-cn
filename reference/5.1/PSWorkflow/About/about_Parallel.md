---
description: 介绍 Parallel 关键字，该关键字并行运行工作流中的活动。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parallel
ms.openlocfilehash: 402e93672bbea4ec9b6bfda8d608f266f6c40a21
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199903"
---
# <a name="about-parallel"></a><span data-ttu-id="c0b65-104">关于并行</span><span class="sxs-lookup"><span data-stu-id="c0b65-104">About Parallel</span></span>

## <a name="short-description"></a><span data-ttu-id="c0b65-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="c0b65-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="c0b65-106">介绍 Parallel 关键字，该关键字并行运行工作流中的活动。</span><span class="sxs-lookup"><span data-stu-id="c0b65-106">Describes the Parallel keyword, which runs the activities in a workflow in parallel.</span></span>

## <a name="long-description"></a><span data-ttu-id="c0b65-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="c0b65-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="c0b65-108">Parallel 关键字并行运行工作流活动。</span><span class="sxs-lookup"><span data-stu-id="c0b65-108">The Parallel keyword runs workflow activities in parallel.</span></span> <span data-ttu-id="c0b65-109">此关键字仅在 Windows PowerShell 工作流中有效。</span><span class="sxs-lookup"><span data-stu-id="c0b65-109">This keyword is valid only in  Windows PowerShell  Workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="c0b65-110">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c0b65-110">SYNTAX</span></span>

```
workflow <Verb-Noun>
{
     Parallel
     {
          [<Activity>]
          [<Activity>]
        ...
     }
 }
```

## <a name="detailed-description"></a><span data-ttu-id="c0b65-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="c0b65-111">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="c0b65-112">并行脚本块中的命令可以并发运行。</span><span class="sxs-lookup"><span data-stu-id="c0b65-112">The commands in a Parallel script block can run concurrently.</span></span> <span data-ttu-id="c0b65-113">它们运行的顺序不确定。</span><span class="sxs-lookup"><span data-stu-id="c0b65-113">The order in which they run is not determined.</span></span>

<span data-ttu-id="c0b65-114">例如，以下工作流包括运行获取计算机上的进程和服务的活动的并行脚本块。</span><span class="sxs-lookup"><span data-stu-id="c0b65-114">For example, the following workflow includes a Parallel script block that runs activities that get processes and services on the computer.</span></span> <span data-ttu-id="c0b65-115">由于 Get-Process 和 Get-Service 命令彼此独立，因此它们可以按任意顺序同时运行。</span><span class="sxs-lookup"><span data-stu-id="c0b65-115">Because the Get-Process and Get-Service commands are independent of each other, they can run concurrently and in any order.</span></span>

```powershell
workflow Test-Workflow
{
    Parallel
    {
         Get-Process
         Get-Service
    }
}
```

<span data-ttu-id="c0b65-116">并行运行命令非常有效，并可减少完成工作流所花的时间。</span><span class="sxs-lookup"><span data-stu-id="c0b65-116">Running commands in parallel is very efficient and reduces the time it takes to complete a workflow significantly.</span></span>

<span data-ttu-id="c0b65-117">若要按顺序运行并行脚本块中的选定命令，请使用 Sequence 关键字。</span><span class="sxs-lookup"><span data-stu-id="c0b65-117">To run selected commands in a Parallel script block in sequential order, use the Sequence keyword.</span></span> <span data-ttu-id="c0b65-118">有关详细信息，请参阅 about_Sequence。</span><span class="sxs-lookup"><span data-stu-id="c0b65-118">For more information, see about_Sequence.</span></span>

<span data-ttu-id="c0b65-119">若要对集合中的项运行并行脚本块，请使用 ForEach 或 ForEach-Parallel 关键字。</span><span class="sxs-lookup"><span data-stu-id="c0b65-119">To run a Parallel script block on items in a collection, use the ForEach or ForEach -Parallel keywords.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0b65-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0b65-120">SEE ALSO</span></span>

<span data-ttu-id="c0b65-121">["编写脚本工作流"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="c0b65-121">["Writing a Script Workflow"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))</span></span>

[<span data-ttu-id="c0b65-122">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="c0b65-122">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[<span data-ttu-id="c0b65-123">about_ForEach 并行</span><span class="sxs-lookup"><span data-stu-id="c0b65-123">about_ForEach-Parallel</span></span>](about_ForEach-Parallel.md)

[<span data-ttu-id="c0b65-124">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="c0b65-124">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="c0b65-125">about_Sequence</span><span class="sxs-lookup"><span data-stu-id="c0b65-125">about_Sequence</span></span>](about_Sequence.md)

[<span data-ttu-id="c0b65-126">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="c0b65-126">about_Workflows</span></span>](about_workflows.md)
