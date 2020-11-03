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
# <a name="about-checkpoint-workflow"></a>关于 Checkpoint-Workflow

## <a name="short-description"></a>简短说明
介绍 Checkpoint-Workflow 活动，该活动在工作流中采用检查点。

## <a name="long-description"></a>详细说明

Checkpoint-Workflow 活动采用一个检查点，用于保存工作流中的状态和数据。 如果工作流被挂起或中断，它可以从最新的检查点恢复，而无需重新启动。

Checkpoint-Workflow 活动仅在工作流中有效。

### <a name="syntax"></a>SYNTAX

```
Workflow <Verb-Noun>
{
    Checkpoint-Workflow
}
```

Checkpoint-Workflow 活动不接受任何参数，包括通用参数和工作流通用参数。

可以将 Checkpoint-Activity 检查点放在工作流中 CmdletBinding 或 Param 语句之后的任何位置。 但是，在放置检查点时，请考虑收集数据并将其写入到运行工作流的计算机上的磁盘的性能成本。

请确保中断后重新运行工作流某一部分所需的时间大于将检查点状态和数据写入磁盘所需的时间。

请考虑在关键步骤之后采用检查点，使工作流可以恢复，而不是重新启动。 例如，在不是幂等的命令后生成一个检查点。

### <a name="about-checkpoints"></a>关于检查点

检查点 是工作流当前状态的快照，其中包括变量的当前值以及在该点生成的任何输出，它会将这些信息保存到磁盘。

如果工作流被有意或无意地中断，则 Windows PowerShell 工作流会自动使用最新的检查点中的数据来恢复和恢复工作流。

将工作流作为作业运行时，例如通过使用 AsJob 工作流通用参数，将保留工作流检查点，直到删除作业，例如通过使用 Remove-Job cmdlet。
否则，工作流检查点将在工作流完成时删除。

### <a name="other-checkpointing-techniques"></a>其他检查点技术

除了 Checkpoint-Workflow 活动，Windows PowerShell 工作流还支持其他检查点技术，其中包括：

- PSPersist 工作流通用参数
- PSPersist 活动通用参数
- 工作流中的 PSPersistPreference 变量 () 

有关向工作流添加检查点的详细信息，请参阅 "如何向工作流添加检查点"。

## <a name="examples"></a>示例

以下工作流包括在完成长时间运行的函数后调用 Checkpoint-Workflow 活动，以及一个共享数据的脚本。

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

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell 工作流](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
