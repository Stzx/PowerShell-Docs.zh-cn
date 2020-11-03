---
description: 提供 PowerShell 工作流功能的简短介绍。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Workflows
ms.openlocfilehash: fbd8ee62b1e9c6969d489c5024c33f5cca883dc6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199892"
---
# <a name="about-workflows"></a>关于工作流

## <a name="short-description"></a>简短说明

提供 PowerShell 工作流功能的简短介绍。

## <a name="long-description"></a>长说明

PowerShell 工作流将 [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) 的优点引入到 powershell，并使你能够编写和运行工作流。

Powershell 工作流是在 PowerShell 3.0 中引入的，模块最多可供 PowerShell 5.1 使用。 有关 PowerShell 工作流的详细信息，请参阅 [工作流指南](/previous-versions/powershell/scripting/components/workflows-guide) 和 [编写 Windows PowerShell 工作流](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)。

## <a name="about-workflows"></a>关于工作流

工作流是由一系列有序的相关活动组成的命令。 通常，它们会长时间运行，收集数据并在异类环境中更改数百台计算机。

可以使用 XAML、Windows Workflow Foundation 中使用的语言或 PowerShell 语言编写工作流。 工作流通常打包在模块中，并包含帮助主题。 有关详细信息，请参阅 [XAML 概述 (WPF) ](/dotnet/framework/wpf/advanced/xaml-overview-wpf)。

工作流在 IT 环境中非常重要，因为工作流可以在重新启动后自动重新启动并从常见故障中自动恢复。 你可以从会话和运行工作流的计算机断开连接和重新连接，而不会中断工作流处理，并且可以透明方式暂停和恢复工作流，而不会 可以记录和审核工作流中的每个活动，以供参考。
工作流可作为作业运行，并可使用 PowerShell 的计划作业功能进行计划。

工作流中的状态和数据将保存在工作流的开头和结尾，并保存在指定的点处。 工作流持久性点的工作方式类似于数据库快照或程序检查点，用于保护工作流免受中断和故障的影响。 如果工作流无法从故障中恢复，则可以使用已保存的数据，并从最后一个暂留点恢复，而不是从头开始重新运行大量工作流。

## <a name="workflow-requirements-and-configuration"></a>工作流要求和配置

PowerShell 工作流配置由以下元素组成：

- 运行工作流的客户端计算机。
- 工作流会话（ **PSSession** ），位于客户端计算机或远程计算机上。
- 托管节点，受工作流活动影响的目标计算机。

工作流会话不是必需的，但建议使用。 **Pssession** 可以利用 PowerShell 的强大恢复和断开连接的会话功能来恢复断开连接的工作流会话。 有关详细信息，请参阅 [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)

因为客户端计算机和运行工作流会话的计算机可以是托管节点，所以可以在满足所有角色的单个计算机上运行工作流。

客户端计算机和运行工作流会话的计算机必须运行 PowerShell 3.0。 支持所有合格系统，包括 Windows Server 操作系统的服务器核心安装选项。

若要运行包含 cmdlet 的工作流，托管节点必须具有 Windows PowerShell 2.0 或更高版本。 托管节点不需要 PowerShell，除非工作流包含 cmdlet。 可以在未安装 PowerShell 的计算机上运行包括 WMI) 和通用信息模型 (CIM) 命令 (Windows Management Instrumentation 的工作流。

## <a name="how-to-get-workflows"></a>如何获取工作流

工作流通常打包在模块中。 若要导入包含工作流的模块，请使用模块中的任何命令或使用 `Import-Module` cmdlet。
首次使用模块中的任何命令时，将自动导入模块。

若要在计算机上安装的模块中查找工作流，请使用 `Get-Command` cmdlet 的 **CommandType** 参数。

```powershell
Get-Command -CommandType Workflow
```

## <a name="how-to-run-workflows"></a>如何运行工作流

若要运行工作流，请使用以下过程。

1. 当托管节点为本地计算机时，此步骤不是必需的。
   否则，在客户端计算机上，通过 "以 **管理员身份运行** " 选项启动 PowerShell。

   ```powershell
   Start-Process PowerShell -Verb RunAs
   ```

1. 在运行工作流会话的计算机上以及包含 cmdlet 的工作流所影响的托管节点上启用 PowerShell 远程处理。

   只需在每个参与的计算机上执行一次此步骤。

   仅当运行包含 cmdlet 的工作流时，才需要执行此步骤。 无需在客户端计算机上启用远程处理，除非工作流会话在客户端计算机上运行，或者在运行 PowerShell 3.0 的任何托管节点上运行。

   若要启用远程处理，请使用 `Enable-PSRemoting` cmdlet。

   ```powershell
   Enable-PSRemoting -Force
   ```

   您可以使用 " **打开脚本执行** 组策略" 设置来启用远程处理。 有关详细信息，请参阅 [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) 和 [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)。

1. 使用 `New-PSWorkflowSession` 或 `New-PSSession` cmdlet 创建工作流会话。

   该 `New-PSWorkflowSession` cmdlet 将启动一个会话，该会话使用目标 **Microsoft.PowerShell.Workflow** 计算机上的内置 此会话配置包括脚本、类型和格式设置文件以及为工作流设计的选项。

   或者，使用 `New-PSSession` cmdlet。 使用 **ConfigurationName** 参数来指定 **Microsoft PowerShell** 会话配置。 此命令与使用 `New-PSWorkflowSession` cmdlet 相同。

   一种替代方法是使用 `New-PSSession` cmdlet。 使用 **ConfigurationName** 参数来指定 **Microsoft PowerShell** 会话配置。

   在本地计算机上：

   ```powershell
   $ws = New-PSWorkflowSession
   ```

   在远程计算机上：

   ```powershell
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

   如果你是工作流会话计算机上的管理员，则可以使用 `New-PSWorkflowExecutionOption` cmdlet 来创建工作流会话配置的自定义选项设置。 使用 `Set-PSSessionConfiguration` cmdlet 可更改会话配置。

   ```powershell
   $sto = New-PSWorkflowExecutionOption -MaxConnectedSessions 150
   Invoke-Command -ComputerName Server01 `
   {Set-PSSessionConfiguration Microsoft.PowerShell.Workflow `
   -SessionTypeOption $Using:sto}
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

1. 在工作流会话中运行工作流。 若要指定托管节点（目标计算机）的名称，请使用 **PSComputerName** 工作流通用参数。

   下面的示例运行名为 **Test-workflow** 的工作流。

   其中，托管节点是托管工作流会话的计算机：

   ```powershell
   Invoke-Command -Session $ws {Test-Workflow}
   ```

   其中托管节点是远程计算机。

   ```powershell
   Invoke-Command -Session $ws{
   Test-Workflow -PSComputerName Server01, Server02 }
   ```

   下面的示例在数百台计算机上运行 **测试工作流** 。 该 `Get-Content` cmdlet 将从文本文件中获取计算机名称，并将它们保存在 `$Servers` 本地计算机上的变量中。

   `Invoke-Command` 使用 `$Using` 范围修饰符来定义 `$Servers` 本地会话中的变量。 有关 `$Using` 作用域修饰符的详细信息，请参阅 [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)。

   ```powershell
   $Servers = Get-Content Servers.txt
   Invoke-Command -Session $ws {Test-Workflow -PSComputerName $Using:Servers }
   ```

## <a name="using-workflow-common-parameters"></a>使用工作流通用参数

工作流通用参数是 PowerShell 自动添加到所有工作流的一组参数。 PowerShell 会将 cmdlet 通用参数添加到所有工作流，即使工作流不使用 **CmdletBinding** 属性。

例如，以下工作流不定义任何参数。 但是，当你运行工作流时，它同时具有 **CommonParameters** 和 **WorkflowCommonParameters** 。

```powershell
workflow Test-Workflow {Get-Process}
Get-Command Test-Workflow -Syntax
```

```powershell
Test-Workflow [<WorkflowCommonParameters>] [<CommonParameters>]
```

工作流通用参数包含多个运行工作流所必需的参数。 例如， **PSComputerName** common 参数指定工作流影响的托管节点。

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02
}
```

**PSPersist** 工作流通用参数确定何时保存工作流数据。 利用此功能，您可以将活动之间的暂留点添加到未定义持久性点的工作流。

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPersist:$True
}
```

其他工作流通用参数可用于指定与托管节点的远程连接的特征。 它们的名称和功能类似于远程处理 cmdlet 的参数，其中包括 `Invoke-Command` 。

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPort 443
}
```

请注意，将为工作流会话定义连接的远程处理参数从用于定义与托管节点的连接的 **PS-前缀** 的工作流通用参数区分开来。

```powershell
$ws = New-PSSession -ComputerName Server01 -ConfigurationName Microsoft.PowerShell.Workflow

Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSConfigurationName Microsoft.PowerShell.Workflow
}
```

某些工作流通用参数对于工作流是唯一的，例如，可让你为不同的远程节点指定不同的工作流通用参数值的 **PSParameterCollection** 参数。 有关工作流通用参数的列表和说明，请参阅 [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)。

## <a name="see-also"></a>另请参阅

[Invoke-AsWorkflow](xref:PSWorkflowUtility.Invoke-AsWorkflow)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[PSWorkflow](xref:PSWorkflow) cmdlet

[工作流指南](/previous-versions/powershell/scripting/components/workflows-guide)

[编写 Windows PowerShell 工作流](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
