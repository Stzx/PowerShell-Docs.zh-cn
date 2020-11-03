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
# <a name="about-workflows"></a><span data-ttu-id="72f92-104">关于工作流</span><span class="sxs-lookup"><span data-stu-id="72f92-104">About Workflows</span></span>

## <a name="short-description"></a><span data-ttu-id="72f92-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="72f92-105">Short description</span></span>

<span data-ttu-id="72f92-106">提供 PowerShell 工作流功能的简短介绍。</span><span class="sxs-lookup"><span data-stu-id="72f92-106">Provides a brief introduction to the PowerShell Workflow feature.</span></span>

## <a name="long-description"></a><span data-ttu-id="72f92-107">长说明</span><span class="sxs-lookup"><span data-stu-id="72f92-107">Long description</span></span>

<span data-ttu-id="72f92-108">PowerShell 工作流将 [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) 的优点引入到 powershell，并使你能够编写和运行工作流。</span><span class="sxs-lookup"><span data-stu-id="72f92-108">PowerShell Workflow brings the benefits of the [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) to PowerShell and enables you to write and run workflows.</span></span>

<span data-ttu-id="72f92-109">Powershell 工作流是在 PowerShell 3.0 中引入的，模块最多可供 PowerShell 5.1 使用。</span><span class="sxs-lookup"><span data-stu-id="72f92-109">PowerShell Workflow was introduced in PowerShell 3.0 and the module is available up to PowerShell 5.1.</span></span> <span data-ttu-id="72f92-110">有关 PowerShell 工作流的详细信息，请参阅 [工作流指南](/previous-versions/powershell/scripting/components/workflows-guide) 和 [编写 Windows PowerShell 工作流](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)。</span><span class="sxs-lookup"><span data-stu-id="72f92-110">For more information about PowerShell Workflow, see the [Workflows Guide](/previous-versions/powershell/scripting/components/workflows-guide) and [Writing a Windows PowerShell Workflow](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow).</span></span>

## <a name="about-workflows"></a><span data-ttu-id="72f92-111">关于工作流</span><span class="sxs-lookup"><span data-stu-id="72f92-111">About workflows</span></span>

<span data-ttu-id="72f92-112">工作流是由一系列有序的相关活动组成的命令。</span><span class="sxs-lookup"><span data-stu-id="72f92-112">Workflows are commands that consist of an ordered sequence of related activities.</span></span> <span data-ttu-id="72f92-113">通常，它们会长时间运行，收集数据并在异类环境中更改数百台计算机。</span><span class="sxs-lookup"><span data-stu-id="72f92-113">Typically, they run for an extended period of time, gathering data from and making changes to hundreds of computers, often in heterogeneous environments.</span></span>

<span data-ttu-id="72f92-114">可以使用 XAML、Windows Workflow Foundation 中使用的语言或 PowerShell 语言编写工作流。</span><span class="sxs-lookup"><span data-stu-id="72f92-114">Workflows can be written in XAML, the language used in Windows Workflow Foundation, or in the PowerShell language.</span></span> <span data-ttu-id="72f92-115">工作流通常打包在模块中，并包含帮助主题。</span><span class="sxs-lookup"><span data-stu-id="72f92-115">Workflows are typically packaged in modules and include help topics.</span></span> <span data-ttu-id="72f92-116">有关详细信息，请参阅 [XAML 概述 (WPF) ](/dotnet/framework/wpf/advanced/xaml-overview-wpf)。</span><span class="sxs-lookup"><span data-stu-id="72f92-116">For more information, see [XAML Overview (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf).</span></span>

<span data-ttu-id="72f92-117">工作流在 IT 环境中非常重要，因为工作流可以在重新启动后自动重新启动并从常见故障中自动恢复。</span><span class="sxs-lookup"><span data-stu-id="72f92-117">Workflows are critical in an IT environment because they can survive reboots and recover automatically from common failures.</span></span> <span data-ttu-id="72f92-118">你可以从会话和运行工作流的计算机断开连接和重新连接，而不会中断工作流处理，并且可以透明方式暂停和恢复工作流，而不会</span><span class="sxs-lookup"><span data-stu-id="72f92-118">You can disconnect and reconnect from sessions and computers running workflows without interrupting workflow processing, and suspend and resume workflows transparently without data loss.</span></span> <span data-ttu-id="72f92-119">可以记录和审核工作流中的每个活动，以供参考。</span><span class="sxs-lookup"><span data-stu-id="72f92-119">Each activity in a workflow can be logged and audited for reference.</span></span>
<span data-ttu-id="72f92-120">工作流可作为作业运行，并可使用 PowerShell 的计划作业功能进行计划。</span><span class="sxs-lookup"><span data-stu-id="72f92-120">Workflows can run as jobs and can be scheduled by using the Scheduled Jobs feature of PowerShell.</span></span>

<span data-ttu-id="72f92-121">工作流中的状态和数据将保存在工作流的开头和结尾，并保存在指定的点处。</span><span class="sxs-lookup"><span data-stu-id="72f92-121">The state and data in a workflow is saved or persisted at the beginning and end of the workflow and at points that you specify.</span></span> <span data-ttu-id="72f92-122">工作流持久性点的工作方式类似于数据库快照或程序检查点，用于保护工作流免受中断和故障的影响。</span><span class="sxs-lookup"><span data-stu-id="72f92-122">Workflow persistence points work like database snapshots or program checkpoints to protect the workflow from the effects of interruptions and failures.</span></span> <span data-ttu-id="72f92-123">如果工作流无法从故障中恢复，则可以使用已保存的数据，并从最后一个暂留点恢复，而不是从头开始重新运行大量工作流。</span><span class="sxs-lookup"><span data-stu-id="72f92-123">If the workflow is unable to recover from a failure, you can use the persisted data and resume from the last persistence point, instead of rerunning an extensive workflow from the beginning.</span></span>

## <a name="workflow-requirements-and-configuration"></a><span data-ttu-id="72f92-124">工作流要求和配置</span><span class="sxs-lookup"><span data-stu-id="72f92-124">Workflow requirements and configuration</span></span>

<span data-ttu-id="72f92-125">PowerShell 工作流配置由以下元素组成：</span><span class="sxs-lookup"><span data-stu-id="72f92-125">A PowerShell Workflow configuration consists of the following elements:</span></span>

- <span data-ttu-id="72f92-126">运行工作流的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="72f92-126">A client computer, which runs the workflow.</span></span>
- <span data-ttu-id="72f92-127">工作流会话（ **PSSession** ），位于客户端计算机或远程计算机上。</span><span class="sxs-lookup"><span data-stu-id="72f92-127">A workflow session, **PSSession** , on the client computer or on a remote computer.</span></span>
- <span data-ttu-id="72f92-128">托管节点，受工作流活动影响的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="72f92-128">Managed nodes, the target computers that are affected by the workflow activities.</span></span>

<span data-ttu-id="72f92-129">工作流会话不是必需的，但建议使用。</span><span class="sxs-lookup"><span data-stu-id="72f92-129">The workflow session isn't required, but is recommended.</span></span> <span data-ttu-id="72f92-130">**Pssession** 可以利用 PowerShell 的强大恢复和断开连接的会话功能来恢复断开连接的工作流会话。</span><span class="sxs-lookup"><span data-stu-id="72f92-130">**PSSessions** can take advantage of the robust recovery and Disconnected Sessions features of PowerShell to recover disconnected workflow sessions.</span></span> <span data-ttu-id="72f92-131">有关详细信息，请参阅 [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)</span><span class="sxs-lookup"><span data-stu-id="72f92-131">For more information, see [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)</span></span>

<span data-ttu-id="72f92-132">因为客户端计算机和运行工作流会话的计算机可以是托管节点，所以可以在满足所有角色的单个计算机上运行工作流。</span><span class="sxs-lookup"><span data-stu-id="72f92-132">Because the client computer and the computer on which the workflow session runs can be managed nodes, you can run a workflow on a single computer that fulfills all roles.</span></span>

<span data-ttu-id="72f92-133">客户端计算机和运行工作流会话的计算机必须运行 PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="72f92-133">The client computer and the computer on which the workflow session runs must be running PowerShell 3.0.</span></span> <span data-ttu-id="72f92-134">支持所有合格系统，包括 Windows Server 操作系统的服务器核心安装选项。</span><span class="sxs-lookup"><span data-stu-id="72f92-134">All eligible systems are supported, including the Server Core installation options of Windows Server operating systems.</span></span>

<span data-ttu-id="72f92-135">若要运行包含 cmdlet 的工作流，托管节点必须具有 Windows PowerShell 2.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="72f92-135">To run workflows that include cmdlets, the managed nodes must have Windows PowerShell 2.0 or later.</span></span> <span data-ttu-id="72f92-136">托管节点不需要 PowerShell，除非工作流包含 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="72f92-136">Managed nodes don't require PowerShell unless the workflow includes cmdlets.</span></span> <span data-ttu-id="72f92-137">可以在未安装 PowerShell 的计算机上运行包括 WMI) 和通用信息模型 (CIM) 命令 (Windows Management Instrumentation 的工作流。</span><span class="sxs-lookup"><span data-stu-id="72f92-137">You can run workflows that include Windows Management Instrumentation (WMI) and Common Information Model (CIM) commands on computers that don't have PowerShell.</span></span>

## <a name="how-to-get-workflows"></a><span data-ttu-id="72f92-138">如何获取工作流</span><span class="sxs-lookup"><span data-stu-id="72f92-138">How to get workflows</span></span>

<span data-ttu-id="72f92-139">工作流通常打包在模块中。</span><span class="sxs-lookup"><span data-stu-id="72f92-139">Workflows are typically packaged in modules.</span></span> <span data-ttu-id="72f92-140">若要导入包含工作流的模块，请使用模块中的任何命令或使用 `Import-Module` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="72f92-140">To import the module that includes a workflow, use any command in the module or use the `Import-Module` cmdlet.</span></span>
<span data-ttu-id="72f92-141">首次使用模块中的任何命令时，将自动导入模块。</span><span class="sxs-lookup"><span data-stu-id="72f92-141">Modules are imported automatically on first use of any command in the module.</span></span>

<span data-ttu-id="72f92-142">若要在计算机上安装的模块中查找工作流，请使用 `Get-Command` cmdlet 的 **CommandType** 参数。</span><span class="sxs-lookup"><span data-stu-id="72f92-142">To find the workflows in modules installed on your computer, use the `Get-Command` cmdlet's **CommandType** parameter.</span></span>

```powershell
Get-Command -CommandType Workflow
```

## <a name="how-to-run-workflows"></a><span data-ttu-id="72f92-143">如何运行工作流</span><span class="sxs-lookup"><span data-stu-id="72f92-143">How to run workflows</span></span>

<span data-ttu-id="72f92-144">若要运行工作流，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="72f92-144">To run a workflow, use the following procedure.</span></span>

1. <span data-ttu-id="72f92-145">当托管节点为本地计算机时，此步骤不是必需的。</span><span class="sxs-lookup"><span data-stu-id="72f92-145">When the managed node is the local computer, this step isn't required.</span></span>
   <span data-ttu-id="72f92-146">否则，在客户端计算机上，通过 "以 **管理员身份运行** " 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="72f92-146">Otherwise, on the client computer, start PowerShell with the **Run as administrator** option.</span></span>

   ```powershell
   Start-Process PowerShell -Verb RunAs
   ```

1. <span data-ttu-id="72f92-147">在运行工作流会话的计算机上以及包含 cmdlet 的工作流所影响的托管节点上启用 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="72f92-147">Enable PowerShell remoting on the computer that runs the workflow session and on managed nodes affected by workflows that include cmdlets.</span></span>

   <span data-ttu-id="72f92-148">只需在每个参与的计算机上执行一次此步骤。</span><span class="sxs-lookup"><span data-stu-id="72f92-148">You only need to do this step once on each participating computer.</span></span>

   <span data-ttu-id="72f92-149">仅当运行包含 cmdlet 的工作流时，才需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="72f92-149">This step is required only when running workflows that include cmdlets.</span></span> <span data-ttu-id="72f92-150">无需在客户端计算机上启用远程处理，除非工作流会话在客户端计算机上运行，或者在运行 PowerShell 3.0 的任何托管节点上运行。</span><span class="sxs-lookup"><span data-stu-id="72f92-150">You don't need to enable remoting on the client computer, unless the workflows session runs on the client computer, or on any managed nodes that are running PowerShell 3.0.</span></span>

   <span data-ttu-id="72f92-151">若要启用远程处理，请使用 `Enable-PSRemoting` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="72f92-151">To enable remoting, use the `Enable-PSRemoting` cmdlet.</span></span>

   ```powershell
   Enable-PSRemoting -Force
   ```

   <span data-ttu-id="72f92-152">您可以使用 " **打开脚本执行** 组策略" 设置来启用远程处理。</span><span class="sxs-lookup"><span data-stu-id="72f92-152">You can enable remoting by using the **Turn on Script Execution** Group Policy setting.</span></span> <span data-ttu-id="72f92-153">有关详细信息，请参阅 [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) 和 [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="72f92-153">For more information, see [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) and [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

1. <span data-ttu-id="72f92-154">使用 `New-PSWorkflowSession` 或 `New-PSSession` cmdlet 创建工作流会话。</span><span class="sxs-lookup"><span data-stu-id="72f92-154">Use the `New-PSWorkflowSession` or `New-PSSession` cmdlets to create the workflow session.</span></span>

   <span data-ttu-id="72f92-155">该 `New-PSWorkflowSession` cmdlet 将启动一个会话，该会话使用目标 **Microsoft.PowerShell.Workflow** 计算机上的内置</span><span class="sxs-lookup"><span data-stu-id="72f92-155">The `New-PSWorkflowSession` cmdlet starts a session that uses the built-in **Microsoft.PowerShell.Workflow** session configuration on the destination computer.</span></span> <span data-ttu-id="72f92-156">此会话配置包括脚本、类型和格式设置文件以及为工作流设计的选项。</span><span class="sxs-lookup"><span data-stu-id="72f92-156">This session configuration includes scripts, type and formatting files, and options that are designed for workflows.</span></span>

   <span data-ttu-id="72f92-157">或者，使用 `New-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="72f92-157">Or, use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="72f92-158">使用 **ConfigurationName** 参数来指定 **Microsoft PowerShell** 会话配置。</span><span class="sxs-lookup"><span data-stu-id="72f92-158">Use the **ConfigurationName** parameter to specify the **Microsoft.PowerShell.Workflow** session configuration.</span></span> <span data-ttu-id="72f92-159">此命令与使用 `New-PSWorkflowSession` cmdlet 相同。</span><span class="sxs-lookup"><span data-stu-id="72f92-159">This command is the same as using the `New-PSWorkflowSession` cmdlet.</span></span>

   <span data-ttu-id="72f92-160">一种替代方法是使用 `New-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="72f92-160">An alternative is to use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="72f92-161">使用 **ConfigurationName** 参数来指定 **Microsoft PowerShell** 会话配置。</span><span class="sxs-lookup"><span data-stu-id="72f92-161">Use the **ConfigurationName** parameter to specify the **Microsoft.PowerShell.Workflow** session configuration.</span></span>

   <span data-ttu-id="72f92-162">在本地计算机上：</span><span class="sxs-lookup"><span data-stu-id="72f92-162">On the local computer:</span></span>

   ```powershell
   $ws = New-PSWorkflowSession
   ```

   <span data-ttu-id="72f92-163">在远程计算机上：</span><span class="sxs-lookup"><span data-stu-id="72f92-163">On a remote computer:</span></span>

   ```powershell
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

   <span data-ttu-id="72f92-164">如果你是工作流会话计算机上的管理员，则可以使用 `New-PSWorkflowExecutionOption` cmdlet 来创建工作流会话配置的自定义选项设置。</span><span class="sxs-lookup"><span data-stu-id="72f92-164">If you are an Administrator on the workflow session computer, you can use the `New-PSWorkflowExecutionOption` cmdlet to create custom option settings for the workflow session configuration.</span></span> <span data-ttu-id="72f92-165">使用 `Set-PSSessionConfiguration` cmdlet 可更改会话配置。</span><span class="sxs-lookup"><span data-stu-id="72f92-165">And, use the `Set-PSSessionConfiguration` cmdlet to change the session configuration.</span></span>

   ```powershell
   $sto = New-PSWorkflowExecutionOption -MaxConnectedSessions 150
   Invoke-Command -ComputerName Server01 `
   {Set-PSSessionConfiguration Microsoft.PowerShell.Workflow `
   -SessionTypeOption $Using:sto}
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

1. <span data-ttu-id="72f92-166">在工作流会话中运行工作流。</span><span class="sxs-lookup"><span data-stu-id="72f92-166">Run the workflow in the workflow session.</span></span> <span data-ttu-id="72f92-167">若要指定托管节点（目标计算机）的名称，请使用 **PSComputerName** 工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="72f92-167">To specify the names of the managed nodes, target computers, use the **PSComputerName** workflow common parameter.</span></span>

   <span data-ttu-id="72f92-168">下面的示例运行名为 **Test-workflow** 的工作流。</span><span class="sxs-lookup"><span data-stu-id="72f92-168">The following examples run the workflow named **Test-Workflow** .</span></span>

   <span data-ttu-id="72f92-169">其中，托管节点是托管工作流会话的计算机：</span><span class="sxs-lookup"><span data-stu-id="72f92-169">Where the managed node is the computer that hosts the workflow session:</span></span>

   ```powershell
   Invoke-Command -Session $ws {Test-Workflow}
   ```

   <span data-ttu-id="72f92-170">其中托管节点是远程计算机。</span><span class="sxs-lookup"><span data-stu-id="72f92-170">Where the managed nodes are remote computers.</span></span>

   ```powershell
   Invoke-Command -Session $ws{
   Test-Workflow -PSComputerName Server01, Server02 }
   ```

   <span data-ttu-id="72f92-171">下面的示例在数百台计算机上运行 **测试工作流** 。</span><span class="sxs-lookup"><span data-stu-id="72f92-171">The following example runs the **Test-Workflow** on hundreds of computers.</span></span> <span data-ttu-id="72f92-172">该 `Get-Content` cmdlet 将从文本文件中获取计算机名称，并将它们保存在 `$Servers` 本地计算机上的变量中。</span><span class="sxs-lookup"><span data-stu-id="72f92-172">The `Get-Content` cmdlet gets the computer names from a text file and saves them in the `$Servers` variable on the local computer.</span></span>

   <span data-ttu-id="72f92-173">`Invoke-Command` 使用 `$Using` 范围修饰符来定义 `$Servers` 本地会话中的变量。</span><span class="sxs-lookup"><span data-stu-id="72f92-173">`Invoke-Command` uses the `$Using` scope modifier to define the `$Servers` variable in the local session.</span></span> <span data-ttu-id="72f92-174">有关 `$Using` 作用域修饰符的详细信息，请参阅 [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="72f92-174">For more information about the `$Using` scope modifier, see [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span></span>

   ```powershell
   $Servers = Get-Content Servers.txt
   Invoke-Command -Session $ws {Test-Workflow -PSComputerName $Using:Servers }
   ```

## <a name="using-workflow-common-parameters"></a><span data-ttu-id="72f92-175">使用工作流通用参数</span><span class="sxs-lookup"><span data-stu-id="72f92-175">Using workflow common parameters</span></span>

<span data-ttu-id="72f92-176">工作流通用参数是 PowerShell 自动添加到所有工作流的一组参数。</span><span class="sxs-lookup"><span data-stu-id="72f92-176">The workflow common parameters are a set of parameters that PowerShell adds automatically to all workflows.</span></span> <span data-ttu-id="72f92-177">PowerShell 会将 cmdlet 通用参数添加到所有工作流，即使工作流不使用 **CmdletBinding** 属性。</span><span class="sxs-lookup"><span data-stu-id="72f92-177">PowerShell adds the cmdlet common parameters to all workflows, even if the workflow doesn't use the **CmdletBinding** attribute.</span></span>

<span data-ttu-id="72f92-178">例如，以下工作流不定义任何参数。</span><span class="sxs-lookup"><span data-stu-id="72f92-178">For example, the following workflow defines no parameters.</span></span> <span data-ttu-id="72f92-179">但是，当你运行工作流时，它同时具有 **CommonParameters** 和 **WorkflowCommonParameters** 。</span><span class="sxs-lookup"><span data-stu-id="72f92-179">However, when you run the workflow, it has both the **CommonParameters** and **WorkflowCommonParameters** .</span></span>

```powershell
workflow Test-Workflow {Get-Process}
Get-Command Test-Workflow -Syntax
```

```powershell
Test-Workflow [<WorkflowCommonParameters>] [<CommonParameters>]
```

<span data-ttu-id="72f92-180">工作流通用参数包含多个运行工作流所必需的参数。</span><span class="sxs-lookup"><span data-stu-id="72f92-180">The workflow common parameters include several parameters that are essential to running workflows.</span></span> <span data-ttu-id="72f92-181">例如， **PSComputerName** common 参数指定工作流影响的托管节点。</span><span class="sxs-lookup"><span data-stu-id="72f92-181">For example, the **PSComputerName** common parameter specifies the managed nodes that the workflow affects.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02
}
```

<span data-ttu-id="72f92-182">**PSPersist** 工作流通用参数确定何时保存工作流数据。</span><span class="sxs-lookup"><span data-stu-id="72f92-182">The **PSPersist** workflow common parameter determines when workflow data is persisted.</span></span> <span data-ttu-id="72f92-183">利用此功能，您可以将活动之间的暂留点添加到未定义持久性点的工作流。</span><span class="sxs-lookup"><span data-stu-id="72f92-183">It enables you to add persistence point between activities to workflows that don't define persistence points.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPersist:$True
}
```

<span data-ttu-id="72f92-184">其他工作流通用参数可用于指定与托管节点的远程连接的特征。</span><span class="sxs-lookup"><span data-stu-id="72f92-184">Other workflow common parameters let you specify the characteristics of the remote connection to the managed nodes.</span></span> <span data-ttu-id="72f92-185">它们的名称和功能类似于远程处理 cmdlet 的参数，其中包括 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="72f92-185">Their names and functionality are similar to the parameters of remoting cmdlets, including `Invoke-Command`.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPort 443
}
```

<span data-ttu-id="72f92-186">请注意，将为工作流会话定义连接的远程处理参数从用于定义与托管节点的连接的 **PS-前缀** 的工作流通用参数区分开来。</span><span class="sxs-lookup"><span data-stu-id="72f92-186">Take care to distinguish the remoting parameters that define the connection for the workflow session from the **PS-prefixed** workflow common parameters that define the connection to the managed nodes.</span></span>

```powershell
$ws = New-PSSession -ComputerName Server01 -ConfigurationName Microsoft.PowerShell.Workflow

Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSConfigurationName Microsoft.PowerShell.Workflow
}
```

<span data-ttu-id="72f92-187">某些工作流通用参数对于工作流是唯一的，例如，可让你为不同的远程节点指定不同的工作流通用参数值的 **PSParameterCollection** 参数。</span><span class="sxs-lookup"><span data-stu-id="72f92-187">Some workflow common parameters are unique to workflows, such as the **PSParameterCollection** parameter that lets you specify different workflow common parameter values for different remote nodes.</span></span> <span data-ttu-id="72f92-188">有关工作流通用参数的列表和说明，请参阅 [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="72f92-188">For a list and description of the workflow common parameters, see [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="72f92-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72f92-189">See also</span></span>

[<span data-ttu-id="72f92-190">Invoke-AsWorkflow</span><span class="sxs-lookup"><span data-stu-id="72f92-190">Invoke-AsWorkflow</span></span>](xref:PSWorkflowUtility.Invoke-AsWorkflow)

[<span data-ttu-id="72f92-191">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="72f92-191">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

<span data-ttu-id="72f92-192">[PSWorkflow](xref:PSWorkflow) cmdlet</span><span class="sxs-lookup"><span data-stu-id="72f92-192">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="72f92-193">工作流指南</span><span class="sxs-lookup"><span data-stu-id="72f92-193">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="72f92-194">编写 Windows PowerShell 工作流</span><span class="sxs-lookup"><span data-stu-id="72f92-194">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
