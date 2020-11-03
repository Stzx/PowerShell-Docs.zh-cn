---
description: 介绍 `ForEach -Parallel` Windows PowerShell 工作流中的语言构造。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_foreach-parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach 并行
ms.openlocfilehash: 1012b45396b65d424dacac067c2af8d3b6823f92
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199907"
---
# <a name="about-foreach-parallel"></a><span data-ttu-id="6abe8-104">关于 Foreach-Parallel</span><span class="sxs-lookup"><span data-stu-id="6abe8-104">About Foreach-Parallel</span></span>

## <a name="short-description"></a><span data-ttu-id="6abe8-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="6abe8-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="6abe8-106">介绍 `ForEach -Parallel` Windows PowerShell 工作流中的语言构造。</span><span class="sxs-lookup"><span data-stu-id="6abe8-106">Describes the `ForEach -Parallel` language construct in Windows PowerShell Workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="6abe8-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="6abe8-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="6abe8-108">关键字的 **Parallel** 参数在 `ForEach` `ForEach` 脚本块中对指定集合中的每个项运行命令一次。</span><span class="sxs-lookup"><span data-stu-id="6abe8-108">The **Parallel** parameter of the `ForEach` keyword runs the commands in a `ForEach` script block once for each item in a specified collection.</span></span>

<span data-ttu-id="6abe8-109">集合中的项（如磁盘集合中的磁盘）将并行处理。</span><span class="sxs-lookup"><span data-stu-id="6abe8-109">The items in the collection, such as a disk in a collection of disks, are processed in parallel.</span></span> <span data-ttu-id="6abe8-110">脚本块中的命令按顺序对集合中的每个项运行。</span><span class="sxs-lookup"><span data-stu-id="6abe8-110">The commands in the script block run sequentially on each item in the collection.</span></span>

<span data-ttu-id="6abe8-111">`ForEach -Parallel` 仅在 Windows PowerShell 工作流中有效。</span><span class="sxs-lookup"><span data-stu-id="6abe8-111">`ForEach -Parallel` is valid only in a Windows PowerShell Workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="6abe8-112">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6abe8-112">SYNTAX</span></span>

```
ForEach -Parallel ($<item> in $<collection>)
{
    [<Activity1>]
    [<Activity2>]
    ...
}
```

### <a name="detailed-description"></a><span data-ttu-id="6abe8-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="6abe8-113">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="6abe8-114">与 Windows PowerShell 中的 ForEach 语句一样，包含集合的变量 `$<collection>` 必须在语句之前定义 `ForEach -Parallel` ，但表示当前项的变量 `$<item>` 在语句中定义 `ForEach -Parallel` 。</span><span class="sxs-lookup"><span data-stu-id="6abe8-114">Like the ForEach statement in Windows PowerShell, the variable that contains collection `$<collection>` must be defined before the `ForEach -Parallel` statement, but the variable that represents the current item `$<item>` is defined in the `ForEach -Parallel` statement.</span></span>

<span data-ttu-id="6abe8-115">`ForEach -Parallel`构造不同于 `ForEach` 关键字和 **并行** 参数。</span><span class="sxs-lookup"><span data-stu-id="6abe8-115">The `ForEach -Parallel` construct is different from the `ForEach` keyword and the **Parallel** parameter.</span></span> <span data-ttu-id="6abe8-116">`ForEach`关键字按顺序处理集合中的项。</span><span class="sxs-lookup"><span data-stu-id="6abe8-116">The `ForEach` keyword processes the items in the collection in sequence.</span></span> <span data-ttu-id="6abe8-117">**并行** 参数并行运行脚本块中的命令。</span><span class="sxs-lookup"><span data-stu-id="6abe8-117">The **Parallel** parameter runs commands in a script block in parallel.</span></span> <span data-ttu-id="6abe8-118">可以在脚本块中包含并行脚本块 `ForEach -Parallel` 。</span><span class="sxs-lookup"><span data-stu-id="6abe8-118">You can enclose a Parallel script block in a `ForEach -Parallel` script block.</span></span>

<span data-ttu-id="6abe8-119">工作流中的目标计算机（如由 **PSComputerName** 工作流通用参数指定的计算机）始终会并行处理。</span><span class="sxs-lookup"><span data-stu-id="6abe8-119">The target computers in a workflow, such as those specified by the **PSComputerName** workflow common parameter, are always processed in parallel.</span></span>
<span data-ttu-id="6abe8-120">无需指定 `ForEach -Parallel` 关键字即可实现此目的。</span><span class="sxs-lookup"><span data-stu-id="6abe8-120">You do not need to specify the `ForEach -Parallel` keyword for this purpose.</span></span>

### <a name="examples"></a><span data-ttu-id="6abe8-121">示例</span><span class="sxs-lookup"><span data-stu-id="6abe8-121">EXAMPLES</span></span>

<span data-ttu-id="6abe8-122">下面的工作流包含 `ForEach -Parallel` 处理活动获取的磁盘的语句 `Get-Disk` 。</span><span class="sxs-lookup"><span data-stu-id="6abe8-122">The following workflow contains a `ForEach -Parallel` statement that processes the disks that the `Get-Disk` activity gets.</span></span> <span data-ttu-id="6abe8-123">脚本块中的命令 `ForEach -Parallel` 按顺序运行，但它们在磁盘上并行运行。</span><span class="sxs-lookup"><span data-stu-id="6abe8-123">The commands in the `ForEach -Parallel` script block run sequentially, but they run on the disks in parallel.</span></span> <span data-ttu-id="6abe8-124">磁盘可能以任意顺序同时进行处理。</span><span class="sxs-lookup"><span data-stu-id="6abe8-124">The disks might be processed concurrently and in any order.</span></span>

```powershell
workflow Test-Workflow
{
    $Disks = Get-Disk

    # The disks are processed in parallel.
    ForEach -Parallel ($Disk in $Disks)
    {
        # The commands run sequentially on each disk.
        $DiskPath = $Disk.Path
        $Disk | Initialize-Disk
        Set-Disk -Path $DiskPath
    }
}

workflow Test-Workflow
{
    #Run commands in parallel.
    Parallel
    {
        Get-Process
        Get-Service
    }

   $Disks = Get-Disk

   # The disks are processed in parallel.
   ForEach -Parallel ($Disk in $Disks)
   {
       # The commands run in parallel on each disk.
       Parallel
       {
           Initialize-Disk
           InlineScript {.\Get-DiskInventory}
       }
   }
}
```

## <a name="see-also"></a><span data-ttu-id="6abe8-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6abe8-125">SEE ALSO</span></span>

[<span data-ttu-id="6abe8-126">Writing a Script Workflow</span><span class="sxs-lookup"><span data-stu-id="6abe8-126">Writing a Script Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)

[<span data-ttu-id="6abe8-127">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="6abe8-127">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_ForEach.md)

[<span data-ttu-id="6abe8-128">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="6abe8-128">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="6abe8-129">about_Parallel</span><span class="sxs-lookup"><span data-stu-id="6abe8-129">about_Parallel</span></span>](about_Parallel.md)

[<span data-ttu-id="6abe8-130">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="6abe8-130">about_Workflows</span></span>](about_Workflows.md)
