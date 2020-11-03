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
# <a name="about-parallel"></a>关于并行

## <a name="short-description"></a>简短说明
介绍 Parallel 关键字，该关键字并行运行工作流中的活动。

## <a name="long-description"></a>详细说明

Parallel 关键字并行运行工作流活动。 此关键字仅在 Windows PowerShell 工作流中有效。

### <a name="syntax"></a>SYNTAX

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

## <a name="detailed-description"></a>详细说明

并行脚本块中的命令可以并发运行。 它们运行的顺序不确定。

例如，以下工作流包括运行获取计算机上的进程和服务的活动的并行脚本块。 由于 Get-Process 和 Get-Service 命令彼此独立，因此它们可以按任意顺序同时运行。

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

并行运行命令非常有效，并可减少完成工作流所花的时间。

若要按顺序运行并行脚本块中的选定命令，请使用 Sequence 关键字。 有关详细信息，请参阅 about_Sequence。

若要对集合中的项运行并行脚本块，请使用 ForEach 或 ForEach-Parallel 关键字。

## <a name="see-also"></a>另请参阅

["编写脚本工作流"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[about_ForEach 并行](about_ForEach-Parallel.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Sequence](about_Sequence.md)

[about_Workflows](about_workflows.md)
