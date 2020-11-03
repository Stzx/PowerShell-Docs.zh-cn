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
# <a name="about-sequence"></a>关于序列

## <a name="short-description"></a>简短说明

描述 `Sequence` 按顺序运行所选活动的关键字。

## <a name="long-description"></a>长说明

`Sequence`关键字按顺序运行所选工作流活动。 工作流活动将按它们出现的顺序运行，而不会同时运行。 `Sequence`关键字仅在 PowerShell 工作流中有效。

`Sequence`关键字用于在 `Parallel` 脚本块中按顺序运行所选的命令。

由于工作流活动默认按顺序运行，因此 `Sequence` 关键字只在 `Parallel` 脚本块中有效。 如果 `Sequence` 脚本块中未包含关键字 `Parallel` ，则该关键字有效但无效。

脚本块允许你按 `Sequence` 顺序运行多个命令，从而使你能够并行运行更多命令。

## <a name="syntax"></a>语法

### <a name="workflow-using-sequence"></a>使用序列的工作流

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

### <a name="workflow-using-parallel-and-sequence"></a>使用并行和序列的工作流

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

## <a name="detailed-description"></a>详细说明

`Parallel` 脚本块中的命令可以并发运行。 它们运行的顺序不确定。 此功能可提高脚本工作流的性能。

您可以使用 `Sequence` 脚本块按顺序运行所选的活动，即使活动出现在 `Parallel` 脚本块中。

脚本块中的活动 `Sequence` 会按它们列出的顺序连续运行。 脚本块中的活动 `Sequence` 仅在上一个活动完成后开始。

但是，当脚本块 `Sequence` 出现在 `Parallel` 脚本块中时， `Sequence` 脚本块运行的顺序并不确定。 它可能会在脚本块中的其他活动之前、之后或并发运行 `Parallel` 。

例如，以下工作流包括 `Parallel` 运行获取计算机上的进程和服务的活动的脚本块。 `Parallel`脚本块包含一个 `Sequence` 脚本块，该脚本块从文件中获取信息并使用该信息作为脚本的输入。

`Get-Process`、 `Get-Service` 和与修补程序相关的命令彼此独立。 命令可以同时或按任何顺序运行。 但是，获取修补程序信息的命令必须在使用该信息的命令之前运行。

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

## <a name="see-also"></a>另请参阅

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[about_ForEach 并行](about_ForEach-Parallel.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Parallel](about_Parallel.md)

[about_Workflows](about_Workflows.md)

[使用 Windows PowerShell 脚本创建工作流](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)
