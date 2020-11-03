---
external help file: Microsoft.PowerShell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSWorkflowUtility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflowutility/invoke-asworkflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-AsWorkflow
ms.openlocfilehash: b96bce9fe4d574fe2b7e9c7c0f1e05ee0508adce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197769"
---
# Invoke-AsWorkflow

## 摘要
将命令或表达式运行为 Windows PowerShell 工作流。

## SYNTAX

### Command（默认值）

```
Invoke-AsWorkflow [-CommandName <String>] [-Parameter <Hashtable>] [-InputObject <Object>] [<CommonParameters>]
```

### Expression

```
Invoke-AsWorkflow [-Expression <String>] [-InputObject <Object>] [<CommonParameters>]
```

## DESCRIPTION

`Invoke-AsWorkflow`工作流运行任何命令或表达式作为工作流中的内联脚本。
这些工作流使用标准工作流语义、具有所有工作流通用参数，并具有工作流的所有优势，包括停止、继续和恢复功能。

工作流旨在用于可收集关键数据的长时间运行的命令，但可用于运行任何命令。
有关详细信息，请参阅 [about_Workflows](../PSWorkflow/About/about_Workflows.md)。

你还可以将工作流通用参数添加到此命令。
有关工作流通用参数的详细信息，请参阅 [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)

此工作流程是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：以工作流的形式运行 cmdlet

```powershell
Invoke-AsWorkflow -PSComputerName (Get-Content Servers.txt) -CommandName Get-ExecutionPolicy
```

```output
PSComputerName                     PSSourceJobInstanceId                   Value
--------------                     ---------------------                   -----
Server01                           77b1cdf8-8226-4662-9067-cd2fa5c3b711    AllSigned
Server02                           a33542d7-3cdd-4339-ab99-0e7cd8e59462    Unrestricted
Server03                           279bac28-066a-4646-9497-8fcdcfe9757e    AllSigned
localhost                          0d858009-2cc4-47a4-a2e0-da17dc2883d0    RemoteSigned
```

此命令 `Get-ExecutionPolicy` 在数百台计算机上以工作流的形式运行 cmdlet。

该命令使用 **CommandName** 参数来指定在工作流中运行的 cmdlet。
它使用 **PSComputerName** 工作流通用参数来指定运行该命令的计算机。
**PSComputerName** 参数的值是一个 `Get-Content` 命令，该命令从 Servers.txt 文件获取计算机名称的列表。
参数值括在括号中，用于指示 Windows PowerShell 运行命令， `Get-Command` 然后再使用该值。

与所有远程命令一样，如果在本地计算机上运行该命令（如果 PSComputerName 参数的值包括本地计算机），你必须使用“以管理员身份运行”选项启动 Windows PowerShell。

### 示例 2：使用参数运行 cmdlet

```powershell
$s = Import-Csv .\Servers.csv -Header ServerName, ServerID
Invoke-AsWorkflow -CommandName Get-ExecutionPolicy -Parameter @{Scope="Process"} -PSComputerName {$s.ServerName} -PSConnectionRetryCount 5
```

第一个命令使用 `Import-Csv` cmdlet 从 Servers.csv 文件中的内容创建对象。 该命令使用 `Header` 参数为 `ServerName` 包含目标计算机名称（也称为 "远程节点"）的列创建一个属性。 该命令将结果保存在 `$s` 变量中。

第二个命令使用 `Invoke-AsWorkflow` 工作流在 `Get-ExecutionPolicy` Servers.csv 文件中的计算机上运行命令。 该命令使用的 **CommandName** 参数 `Invoke-AsWorkflow`  来指定要在工作流中运行的命令。 它使用的 `Parameter` 参数 `Invoke-AsWorkflow` 来指定 `Scope` `Get-ExecutionPolicy` 具有 **Process** 值的 cmdlet 的参数。该命令还使用 `PSConnectionRetryCount` workflow common 参数将每台计算机上的命令数限制为5次，并使用 `PSComputerName` workflow common 参数指定 (目标计算机) 的远程节点的名称。 参数的值 `PSComputerName` 是一个表达式，用于获取 `ServerName` 变量中每个对象的属性 `$s` 。

这些命令 `Get-ExecutionPolicy` 在数百台计算机上以工作流的形式运行命令。
该命令使用 `Scope` 值为 Process 的 cmdlet 的参数 `Get-ExecutionPolicy` 来获取 **Process** 当前会话中的执行策略。

### 示例 3：以工作流的形式运行表达式

```powershell
Invoke-AsWorkflow -Expression "ipconfig /all" -PSComputerName (Get-Content DomainControllers.txt) -AsJob -JobName IPConfig
```

```output
Id     Name          PSJobTypeName   State         HasMoreData   Location                Command
--     ----          -------------   -----         -----------   --------                -------
2      IpConfig      PSWorkflowJob   Completed     True          Server01, Server01...   Invoke-AsWorkflow
```

此命令使用 `Invoke-AsWorkflow` 工作流运行 Ipconfig 命令，作为 DomainControllers.txt 文件中列出的计算机上的工作流作业。

该命令使用 `Expression` 参数来指定要运行的表达式。
它使用 `PSComputerName` workflow common 参数指定)  (目标计算机的远程节点的名称。

该命令还使用 `AsJob` 和 `JobName` 工作流通用参数，以在具有 "Ipconfig" 作业名称的每台计算机上以后台作业的形式运行工作流。

命令将返回一个 `ContainerParentJob` 对象 (`System.Management.Automation.ContainerParentJob` 包含每台计算机上的工作流作业的) 。

## PARAMETERS

### -CommandName

将指定的 cmdlet 或高级函数运行为工作流。
输入 cmdlet 或函数名称，例如 `Update-Help` 、 `Set-ExecutionPolicy` 或 `Set-NetFirewallRule` 。

```yaml
Type: System.String
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Expression

指定此 cmdlet 作为工作流运行的表达式。
将表达式输入为字符串，如 `"ipconfig /all"` 。
如果表达式中包含空格或特殊字符，请将该表达式括在引号中。

```yaml
Type: System.String
Parameter Sets: Expression
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameter

指定在参数中指定的命令的参数和参数值 `CommandName` 。
输入一个哈希表，其中每个键都是参数名称，其值为参数值，例如 `@{ExecutionPolicy="AllSigned"}` 。

有关哈希表的信息，请参阅 [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)。

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

用于允许管道输入。

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。

### WorkflowCommonParameters

此 cmdlet 还支持特定于工作流的通用参数。
有关信息，请参阅 [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)。

## 输入

### System.Object

可以通过管道将任何对象传递给 `InputObject` 参数。

## 输出

### 无

此命令不生成任何输出。
但是，它将运行可能生成输出的工作流。

## 注释

## 相关链接

[New-PSWorkflowExecutionOption](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[New-PSWorkflowSession](../PSWorkflow/New-PSWorkflowSession.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_Workflow_Common_Parameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)
