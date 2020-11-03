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
# <span data-ttu-id="9f0af-103">Invoke-AsWorkflow</span><span class="sxs-lookup"><span data-stu-id="9f0af-103">Invoke-AsWorkflow</span></span>

## <span data-ttu-id="9f0af-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9f0af-104">SYNOPSIS</span></span>
<span data-ttu-id="9f0af-105">将命令或表达式运行为 Windows PowerShell 工作流。</span><span class="sxs-lookup"><span data-stu-id="9f0af-105">Runs a command or expression as a Windows PowerShell Workflow.</span></span>

## <span data-ttu-id="9f0af-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f0af-106">SYNTAX</span></span>

### <span data-ttu-id="9f0af-107">Command（默认值）</span><span class="sxs-lookup"><span data-stu-id="9f0af-107">Command (Default)</span></span>

```
Invoke-AsWorkflow [-CommandName <String>] [-Parameter <Hashtable>] [-InputObject <Object>] [<CommonParameters>]
```

### <span data-ttu-id="9f0af-108">Expression</span><span class="sxs-lookup"><span data-stu-id="9f0af-108">Expression</span></span>

```
Invoke-AsWorkflow [-Expression <String>] [-InputObject <Object>] [<CommonParameters>]
```

## <span data-ttu-id="9f0af-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9f0af-109">DESCRIPTION</span></span>

<span data-ttu-id="9f0af-110">`Invoke-AsWorkflow`工作流运行任何命令或表达式作为工作流中的内联脚本。</span><span class="sxs-lookup"><span data-stu-id="9f0af-110">The `Invoke-AsWorkflow` workflow runs any command or expression as an inline script in a workflow.</span></span>
<span data-ttu-id="9f0af-111">这些工作流使用标准工作流语义、具有所有工作流通用参数，并具有工作流的所有优势，包括停止、继续和恢复功能。</span><span class="sxs-lookup"><span data-stu-id="9f0af-111">These workflows use the standard workflow semantics, have all workflow common parameters, and have all benefits of workflows, including the ability to stop, resume, and recover.</span></span>

<span data-ttu-id="9f0af-112">工作流旨在用于可收集关键数据的长时间运行的命令，但可用于运行任何命令。</span><span class="sxs-lookup"><span data-stu-id="9f0af-112">Workflows are designed for long-running commands that collect critical data, but can be used to run any command.</span></span>
<span data-ttu-id="9f0af-113">有关详细信息，请参阅 [about_Workflows](../PSWorkflow/About/about_Workflows.md)。</span><span class="sxs-lookup"><span data-stu-id="9f0af-113">For more information, see [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span></span>

<span data-ttu-id="9f0af-114">你还可以将工作流通用参数添加到此命令。</span><span class="sxs-lookup"><span data-stu-id="9f0af-114">You can also add workflow common parameters to this command.</span></span>
<span data-ttu-id="9f0af-115">有关工作流通用参数的详细信息，请参阅 [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="9f0af-115">For more information about workflow common parameters, see [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)</span></span>

<span data-ttu-id="9f0af-116">此工作流程是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="9f0af-116">This workflow is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="9f0af-117">示例</span><span class="sxs-lookup"><span data-stu-id="9f0af-117">EXAMPLES</span></span>

### <span data-ttu-id="9f0af-118">示例 1：以工作流的形式运行 cmdlet</span><span class="sxs-lookup"><span data-stu-id="9f0af-118">Example 1: Run a cmdlet as a workflow</span></span>

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

<span data-ttu-id="9f0af-119">此命令 `Get-ExecutionPolicy` 在数百台计算机上以工作流的形式运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9f0af-119">This command runs the `Get-ExecutionPolicy` cmdlet as a workflow on hundreds of computers.</span></span>

<span data-ttu-id="9f0af-120">该命令使用 **CommandName** 参数来指定在工作流中运行的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9f0af-120">The command uses the **CommandName** parameter to specify the cmdlet that runs in the workflow.</span></span>
<span data-ttu-id="9f0af-121">它使用 **PSComputerName** 工作流通用参数来指定运行该命令的计算机。</span><span class="sxs-lookup"><span data-stu-id="9f0af-121">It uses the **PSComputerName** workflow common parameter to specify the computers on which the command runs.</span></span>
<span data-ttu-id="9f0af-122">**PSComputerName** 参数的值是一个 `Get-Content` 命令，该命令从 Servers.txt 文件获取计算机名称的列表。</span><span class="sxs-lookup"><span data-stu-id="9f0af-122">The value of the **PSComputerName** parameter is a `Get-Content` command that gets a list of computer names from the Servers.txt file.</span></span>
<span data-ttu-id="9f0af-123">参数值括在括号中，用于指示 Windows PowerShell 运行命令， `Get-Command` 然后再使用该值。</span><span class="sxs-lookup"><span data-stu-id="9f0af-123">The parameter value is enclosed in parentheses to direct Windows PowerShell to run the `Get-Command` command before using the value.</span></span>

<span data-ttu-id="9f0af-124">与所有远程命令一样，如果在本地计算机上运行该命令（如果 PSComputerName 参数的值包括本地计算机），你必须使用“以管理员身份运行”选项启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="9f0af-124">As with all remote commands, if the command runs on the local computer, (if the value of the PSComputerName parameter includes the local computer), you must start Windows PowerShell with the "Run as administrator" option.</span></span>

### <span data-ttu-id="9f0af-125">示例 2：使用参数运行 cmdlet</span><span class="sxs-lookup"><span data-stu-id="9f0af-125">Example 2: Run a cmdlet with parameters</span></span>

```powershell
$s = Import-Csv .\Servers.csv -Header ServerName, ServerID
Invoke-AsWorkflow -CommandName Get-ExecutionPolicy -Parameter @{Scope="Process"} -PSComputerName {$s.ServerName} -PSConnectionRetryCount 5
```

<span data-ttu-id="9f0af-126">第一个命令使用 `Import-Csv` cmdlet 从 Servers.csv 文件中的内容创建对象。</span><span class="sxs-lookup"><span data-stu-id="9f0af-126">The first command uses the `Import-Csv` cmdlet to create an object from the content in the Servers.csv file.</span></span> <span data-ttu-id="9f0af-127">该命令使用 `Header` 参数为 `ServerName` 包含目标计算机名称（也称为 "远程节点"）的列创建一个属性。</span><span class="sxs-lookup"><span data-stu-id="9f0af-127">The command uses the `Header` parameter to create a `ServerName` property for the column that contains the names of the target computers, also known as "remote nodes."</span></span> <span data-ttu-id="9f0af-128">该命令将结果保存在 `$s` 变量中。</span><span class="sxs-lookup"><span data-stu-id="9f0af-128">The command saves the result in the `$s` variable.</span></span>

<span data-ttu-id="9f0af-129">第二个命令使用 `Invoke-AsWorkflow` 工作流在 `Get-ExecutionPolicy` Servers.csv 文件中的计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="9f0af-129">The second command uses the `Invoke-AsWorkflow` workflow to run a `Get-ExecutionPolicy` command on the computers in the Servers.csv file.</span></span> <span data-ttu-id="9f0af-130">该命令使用的 **CommandName** 参数 `Invoke-AsWorkflow`  来指定要在工作流中运行的命令。</span><span class="sxs-lookup"><span data-stu-id="9f0af-130">The command uses the **CommandName** parameter of `Invoke-AsWorkflow`  to specify the command to run in the workflow.</span></span> <span data-ttu-id="9f0af-131">它使用的 `Parameter` 参数 `Invoke-AsWorkflow` 来指定 `Scope` `Get-ExecutionPolicy` 具有 **Process** 值的 cmdlet 的参数。该命令还使用 `PSConnectionRetryCount` workflow common 参数将每台计算机上的命令数限制为5次，并使用 `PSComputerName` workflow common 参数指定 (目标计算机) 的远程节点的名称。</span><span class="sxs-lookup"><span data-stu-id="9f0af-131">It uses the `Parameter` parameter of `Invoke-AsWorkflow` to specify the `Scope` parameter of the `Get-ExecutionPolicy` cmdlet with a value of **Process** .The command also uses the `PSConnectionRetryCount` workflow common parameter to limit the command to five attempts on each computer and the `PSComputerName` workflow common parameter to specify the names of the remote nodes (target computers).</span></span> <span data-ttu-id="9f0af-132">参数的值 `PSComputerName` 是一个表达式，用于获取 `ServerName` 变量中每个对象的属性 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="9f0af-132">The value of the `PSComputerName` parameter is an expression that gets the `ServerName` property of every object in the `$s` variable.</span></span>

<span data-ttu-id="9f0af-133">这些命令 `Get-ExecutionPolicy` 在数百台计算机上以工作流的形式运行命令。</span><span class="sxs-lookup"><span data-stu-id="9f0af-133">These commands run a `Get-ExecutionPolicy` command as a workflow on hundreds of computers.</span></span>
<span data-ttu-id="9f0af-134">该命令使用 `Scope` 值为 Process 的 cmdlet 的参数 `Get-ExecutionPolicy` 来获取 **Process** 当前会话中的执行策略。</span><span class="sxs-lookup"><span data-stu-id="9f0af-134">The command uses the `Scope` parameter of the `Get-ExecutionPolicy` cmdlet with a value of **Process** to get the execution policy in the current session.</span></span>

### <span data-ttu-id="9f0af-135">示例 3：以工作流的形式运行表达式</span><span class="sxs-lookup"><span data-stu-id="9f0af-135">Example 3: Run an expression as a workflow</span></span>

```powershell
Invoke-AsWorkflow -Expression "ipconfig /all" -PSComputerName (Get-Content DomainControllers.txt) -AsJob -JobName IPConfig
```

```output
Id     Name          PSJobTypeName   State         HasMoreData   Location                Command
--     ----          -------------   -----         -----------   --------                -------
2      IpConfig      PSWorkflowJob   Completed     True          Server01, Server01...   Invoke-AsWorkflow
```

<span data-ttu-id="9f0af-136">此命令使用 `Invoke-AsWorkflow` 工作流运行 Ipconfig 命令，作为 DomainControllers.txt 文件中列出的计算机上的工作流作业。</span><span class="sxs-lookup"><span data-stu-id="9f0af-136">This command uses the `Invoke-AsWorkflow` workflow to run an Ipconfig command as a workflow job on the computers listed in the DomainControllers.txt file.</span></span>

<span data-ttu-id="9f0af-137">该命令使用 `Expression` 参数来指定要运行的表达式。</span><span class="sxs-lookup"><span data-stu-id="9f0af-137">The command uses the `Expression` parameter to specify the expression to run.</span></span>
<span data-ttu-id="9f0af-138">它使用 `PSComputerName` workflow common 参数指定)  (目标计算机的远程节点的名称。</span><span class="sxs-lookup"><span data-stu-id="9f0af-138">It uses the `PSComputerName` workflow common parameter to specify the names of the remote nodes (target computers).</span></span>

<span data-ttu-id="9f0af-139">该命令还使用 `AsJob` 和 `JobName` 工作流通用参数，以在具有 "Ipconfig" 作业名称的每台计算机上以后台作业的形式运行工作流。</span><span class="sxs-lookup"><span data-stu-id="9f0af-139">The command also uses the `AsJob` and `JobName` workflow common parameters to run the workflow as a background job on each computer with the "Ipconfig" job name.</span></span>

<span data-ttu-id="9f0af-140">命令将返回一个 `ContainerParentJob` 对象 (`System.Management.Automation.ContainerParentJob` 包含每台计算机上的工作流作业的) 。</span><span class="sxs-lookup"><span data-stu-id="9f0af-140">The command returns a `ContainerParentJob` object (`System.Management.Automation.ContainerParentJob`) that contains the workflow jobs on each computer.</span></span>

## <span data-ttu-id="9f0af-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f0af-141">PARAMETERS</span></span>

### <span data-ttu-id="9f0af-142">-CommandName</span><span class="sxs-lookup"><span data-stu-id="9f0af-142">-CommandName</span></span>

<span data-ttu-id="9f0af-143">将指定的 cmdlet 或高级函数运行为工作流。</span><span class="sxs-lookup"><span data-stu-id="9f0af-143">Runs the specified cmdlet or advanced function as a workflow.</span></span>
<span data-ttu-id="9f0af-144">输入 cmdlet 或函数名称，例如 `Update-Help` 、 `Set-ExecutionPolicy` 或 `Set-NetFirewallRule` 。</span><span class="sxs-lookup"><span data-stu-id="9f0af-144">Enter the cmdlet or function name, such as `Update-Help`, `Set-ExecutionPolicy`, or `Set-NetFirewallRule`.</span></span>

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

### <span data-ttu-id="9f0af-145">-Expression</span><span class="sxs-lookup"><span data-stu-id="9f0af-145">-Expression</span></span>

<span data-ttu-id="9f0af-146">指定此 cmdlet 作为工作流运行的表达式。</span><span class="sxs-lookup"><span data-stu-id="9f0af-146">Specifies the  expression that this cmdlet runs as a workflow.</span></span>
<span data-ttu-id="9f0af-147">将表达式输入为字符串，如 `"ipconfig /all"` 。</span><span class="sxs-lookup"><span data-stu-id="9f0af-147">Enter the expression as a string, such as `"ipconfig /all"`.</span></span>
<span data-ttu-id="9f0af-148">如果表达式中包含空格或特殊字符，请将该表达式括在引号中。</span><span class="sxs-lookup"><span data-stu-id="9f0af-148">If the expression includes spaces or special characters, enclose the expression in quotation marks.</span></span>

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

### <span data-ttu-id="9f0af-149">-Parameter</span><span class="sxs-lookup"><span data-stu-id="9f0af-149">-Parameter</span></span>

<span data-ttu-id="9f0af-150">指定在参数中指定的命令的参数和参数值 `CommandName` 。</span><span class="sxs-lookup"><span data-stu-id="9f0af-150">Specifies the parameters and parameter values of the command that is specified in the `CommandName` parameter.</span></span>
<span data-ttu-id="9f0af-151">输入一个哈希表，其中每个键都是参数名称，其值为参数值，例如 `@{ExecutionPolicy="AllSigned"}` 。</span><span class="sxs-lookup"><span data-stu-id="9f0af-151">Enter a hash table in which each key is a parameter name and its value is the parameter value, such as `@{ExecutionPolicy="AllSigned"}`.</span></span>

<span data-ttu-id="9f0af-152">有关哈希表的信息，请参阅 [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)。</span><span class="sxs-lookup"><span data-stu-id="9f0af-152">For information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

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

### <span data-ttu-id="9f0af-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9f0af-153">-InputObject</span></span>

<span data-ttu-id="9f0af-154">用于允许管道输入。</span><span class="sxs-lookup"><span data-stu-id="9f0af-154">Used to allows pipeline input.</span></span>

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

### <span data-ttu-id="9f0af-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9f0af-155">CommonParameters</span></span>

<span data-ttu-id="9f0af-156">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9f0af-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9f0af-157">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="9f0af-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

### <span data-ttu-id="9f0af-158">WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="9f0af-158">WorkflowCommonParameters</span></span>

<span data-ttu-id="9f0af-159">此 cmdlet 还支持特定于工作流的通用参数。</span><span class="sxs-lookup"><span data-stu-id="9f0af-159">This cmdlet also supports workflow specific common parameters.</span></span>
<span data-ttu-id="9f0af-160">有关信息，请参阅 [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="9f0af-160">For information, see [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md).</span></span>

## <span data-ttu-id="9f0af-161">输入</span><span class="sxs-lookup"><span data-stu-id="9f0af-161">INPUTS</span></span>

### <span data-ttu-id="9f0af-162">System.Object</span><span class="sxs-lookup"><span data-stu-id="9f0af-162">System.Object</span></span>

<span data-ttu-id="9f0af-163">可以通过管道将任何对象传递给 `InputObject` 参数。</span><span class="sxs-lookup"><span data-stu-id="9f0af-163">You can pipe any object to the `InputObject` parameter.</span></span>

## <span data-ttu-id="9f0af-164">输出</span><span class="sxs-lookup"><span data-stu-id="9f0af-164">OUTPUTS</span></span>

### <span data-ttu-id="9f0af-165">无</span><span class="sxs-lookup"><span data-stu-id="9f0af-165">None</span></span>

<span data-ttu-id="9f0af-166">此命令不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="9f0af-166">This command does not generate any output.</span></span>
<span data-ttu-id="9f0af-167">但是，它将运行可能生成输出的工作流。</span><span class="sxs-lookup"><span data-stu-id="9f0af-167">However, it runs the workflow, which might generate output.</span></span>

## <span data-ttu-id="9f0af-168">注释</span><span class="sxs-lookup"><span data-stu-id="9f0af-168">NOTES</span></span>

## <span data-ttu-id="9f0af-169">相关链接</span><span class="sxs-lookup"><span data-stu-id="9f0af-169">RELATED LINKS</span></span>

[<span data-ttu-id="9f0af-170">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="9f0af-170">New-PSWorkflowExecutionOption</span></span>](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[<span data-ttu-id="9f0af-171">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="9f0af-171">New-PSWorkflowSession</span></span>](../PSWorkflow/New-PSWorkflowSession.md)

[<span data-ttu-id="9f0af-172">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="9f0af-172">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="9f0af-173">about_Workflow_Common_Parameters</span><span class="sxs-lookup"><span data-stu-id="9f0af-173">about_Workflow_Common_Parameters</span></span>](../PSWorkflow/About/about_WorkflowCommonParameters.md)
