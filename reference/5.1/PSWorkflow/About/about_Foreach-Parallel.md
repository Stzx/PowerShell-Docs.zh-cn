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
# <a name="about-foreach-parallel"></a>关于 Foreach-Parallel

## <a name="short-description"></a>简短说明
介绍 `ForEach -Parallel` Windows PowerShell 工作流中的语言构造。

## <a name="long-description"></a>详细说明

关键字的 **Parallel** 参数在 `ForEach` `ForEach` 脚本块中对指定集合中的每个项运行命令一次。

集合中的项（如磁盘集合中的磁盘）将并行处理。 脚本块中的命令按顺序对集合中的每个项运行。

`ForEach -Parallel` 仅在 Windows PowerShell 工作流中有效。

### <a name="syntax"></a>SYNTAX

```
ForEach -Parallel ($<item> in $<collection>)
{
    [<Activity1>]
    [<Activity2>]
    ...
}
```

### <a name="detailed-description"></a>详细说明

与 Windows PowerShell 中的 ForEach 语句一样，包含集合的变量 `$<collection>` 必须在语句之前定义 `ForEach -Parallel` ，但表示当前项的变量 `$<item>` 在语句中定义 `ForEach -Parallel` 。

`ForEach -Parallel`构造不同于 `ForEach` 关键字和 **并行** 参数。 `ForEach`关键字按顺序处理集合中的项。 **并行** 参数并行运行脚本块中的命令。 可以在脚本块中包含并行脚本块 `ForEach -Parallel` 。

工作流中的目标计算机（如由 **PSComputerName** 工作流通用参数指定的计算机）始终会并行处理。
无需指定 `ForEach -Parallel` 关键字即可实现此目的。

### <a name="examples"></a>示例

下面的工作流包含 `ForEach -Parallel` 处理活动获取的磁盘的语句 `Get-Disk` 。 脚本块中的命令 `ForEach -Parallel` 按顺序运行，但它们在磁盘上并行运行。 磁盘可能以任意顺序同时进行处理。

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

## <a name="see-also"></a>另请参阅

[Writing a Script Workflow](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_ForEach.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Parallel](about_Parallel.md)

[about_Workflows](about_Workflows.md)
