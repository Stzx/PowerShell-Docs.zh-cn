---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Module
ms.openlocfilehash: f0fb0847d43a8fa8541ed194e474a1fab1f5ffa9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198685"
---
# <span data-ttu-id="ea28b-103">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="ea28b-103">Remove-Module</span></span>

## <span data-ttu-id="ea28b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ea28b-104">SYNOPSIS</span></span>
<span data-ttu-id="ea28b-105">删除当前会话中的模块。</span><span class="sxs-lookup"><span data-stu-id="ea28b-105">Removes modules from the current session.</span></span>

## <span data-ttu-id="ea28b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ea28b-106">SYNTAX</span></span>

### <span data-ttu-id="ea28b-107">name</span><span class="sxs-lookup"><span data-stu-id="ea28b-107">name</span></span>

```
Remove-Module [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ea28b-108">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ea28b-108">FullyQualifiedName</span></span>

```
Remove-Module [-FullyQualifiedName] <ModuleSpecification[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ea28b-109">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="ea28b-109">ModuleInfo</span></span>

```
Remove-Module [-ModuleInfo] <PSModuleInfo[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ea28b-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ea28b-110">DESCRIPTION</span></span>

<span data-ttu-id="ea28b-111">**Remove-Module** cmdlet 将从当前会话中删除模块的成员，如 cmdlet 和函数。</span><span class="sxs-lookup"><span data-stu-id="ea28b-111">The **Remove-Module** cmdlet removes the members of a module, such as cmdlets and functions, from the current session.</span></span>

<span data-ttu-id="ea28b-112">如果模块包含某个程序集 (.dll)，则将删除由该程序集实现的所有成员，但不会卸载该程序集。</span><span class="sxs-lookup"><span data-stu-id="ea28b-112">If the module includes an assembly (.dll), all members that are implemented by the assembly are removed, but the assembly is not unloaded.</span></span>

<span data-ttu-id="ea28b-113">此 cmdlet 不会将该模块从计算机中卸载或删除。</span><span class="sxs-lookup"><span data-stu-id="ea28b-113">This cmdlet does not uninstall the module or delete it from the computer.</span></span>
<span data-ttu-id="ea28b-114">它仅影响当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="ea28b-114">It affects only the current PowerShell session.</span></span>

## <span data-ttu-id="ea28b-115">示例</span><span class="sxs-lookup"><span data-stu-id="ea28b-115">EXAMPLES</span></span>

### <span data-ttu-id="ea28b-116">示例 1：删除模块</span><span class="sxs-lookup"><span data-stu-id="ea28b-116">Example 1: Remove a module</span></span>

```powershell
Remove-Module -Name "BitsTransfer"
```

<span data-ttu-id="ea28b-117">此命令将从当前会话中删除 BitsTransfer 模块。</span><span class="sxs-lookup"><span data-stu-id="ea28b-117">This command removes the BitsTransfer module from the current session.</span></span>

### <span data-ttu-id="ea28b-118">示例 2：删除所有模块</span><span class="sxs-lookup"><span data-stu-id="ea28b-118">Example 2: Remove all modules</span></span>

```powershell
Get-Module | Remove-Module
```

<span data-ttu-id="ea28b-119">此命令将从当前会话中删除所有模块。</span><span class="sxs-lookup"><span data-stu-id="ea28b-119">This command removes all modules from the current session.</span></span>

### <span data-ttu-id="ea28b-120">示例 3：通过使用管道删除模块</span><span class="sxs-lookup"><span data-stu-id="ea28b-120">Example 3: Remove modules by using the pipeline</span></span>

```powershell
"FileTransfer", "PSDiagnostics" | Remove-Module -Verbose
```

```Output
VERBOSE: Performing operation "Remove-Module" on Target "filetransfer (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\filetransfer\filetransfer.psd1')".
VERBOSE: Performing operation "Remove-Module" on Target "Microsoft.BackgroundIntelligentTransfer.Management (Path: 'C:\Windows\assembly\GAC_MSIL\Microsoft.BackgroundIntelligentTransfer.Management\1.0.0.0__31bf3856ad364e35\Microsoft.BackgroundIntelligentTransfe
r.Management.dll')".
VERBOSE: Performing operation "Remove-Module" on Target "psdiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\psdiagnostics.psd1')".
VERBOSE: Removing imported function 'Start-Trace'.
VERBOSE: Removing imported function 'Stop-Trace'.
VERBOSE: Removing imported function 'Enable-WSManTrace'.
VERBOSE: Removing imported function 'Disable-WSManTrace'.
VERBOSE: Removing imported function 'Enable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Disable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Set-LogProperties'.
VERBOSE: Removing imported function 'Get-LogProperties'.
VERBOSE: Removing imported function 'Enable-PSTrace'.
VERBOSE: Removing imported function 'Disable-PSTrace'.
VERBOSE: Performing operation "Remove-Module" on Target "PSDiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\PSDiagnostics.psm1')".
```

<span data-ttu-id="ea28b-121">此命令将从当前会话中删除 BitsTransfer 和 PSDiagnostics 模块。</span><span class="sxs-lookup"><span data-stu-id="ea28b-121">This command removes the BitsTransfer and PSDiagnostics modules from the current session.</span></span>

<span data-ttu-id="ea28b-122">该命令使用管道运算符 (|) 将模块名称发送到 **Remove-Module** 。</span><span class="sxs-lookup"><span data-stu-id="ea28b-122">The command uses a pipeline operator (|) to send the module names to **Remove-Module** .</span></span>
<span data-ttu-id="ea28b-123">它使用 *Verbose* 通用参数来获取有关要删除的成员的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ea28b-123">It uses the *Verbose* common parameter to get detailed information about the members that are removed.</span></span>

<span data-ttu-id="ea28b-124">Verbose  消息显示所删除的项。</span><span class="sxs-lookup"><span data-stu-id="ea28b-124">The *Verbose* messages show the items that are removed.</span></span>
<span data-ttu-id="ea28b-125">这些消息会有所不同，因为 BitsTransfer 模块包含一个实现其 cmdlet 的程序集，以及一个拥有自己的程序集的嵌套模块。</span><span class="sxs-lookup"><span data-stu-id="ea28b-125">The messages differ because the BitsTransfer module includes an assembly that implements its cmdlets and a nested module with its own assembly.</span></span>
<span data-ttu-id="ea28b-126">PSDiagnostics 模块包含用于导出函数的模块脚本文件 (.psm1)。</span><span class="sxs-lookup"><span data-stu-id="ea28b-126">The PSDiagnostics module includes a module script file (.psm1) that exports functions.</span></span>

### <span data-ttu-id="ea28b-127">示例 4：通过使用 ModuleInfo 删除模块</span><span class="sxs-lookup"><span data-stu-id="ea28b-127">Example 4: Remove a module by using ModuleInfo</span></span>

```powershell
$a = Get-Module BitsTransfer
Remove-Module -ModuleInfo $a
```

<span data-ttu-id="ea28b-128">此命令使用 ModuleInfo  参数删除 BitsTransfer 模块。</span><span class="sxs-lookup"><span data-stu-id="ea28b-128">This command uses the *ModuleInfo* parameter to remove the BitsTransfer module.</span></span>

## <span data-ttu-id="ea28b-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ea28b-129">PARAMETERS</span></span>

### <span data-ttu-id="ea28b-130">-Force</span><span class="sxs-lookup"><span data-stu-id="ea28b-130">-Force</span></span>

<span data-ttu-id="ea28b-131">指示此 cmdlet 将删除只读模块。</span><span class="sxs-lookup"><span data-stu-id="ea28b-131">Indicates that this cmdlet removes read-only modules.</span></span>
<span data-ttu-id="ea28b-132">默认情况下， **Remove-Module** 只删除读写模块。</span><span class="sxs-lookup"><span data-stu-id="ea28b-132">By default, **Remove-Module** removes only read-write modules.</span></span>

<span data-ttu-id="ea28b-133">**ReadOnly** 和 **ReadWrite** 值存储在模块的 **AccessMode** 属性中。</span><span class="sxs-lookup"><span data-stu-id="ea28b-133">The **ReadOnly** and **ReadWrite** values are stored in **AccessMode** property of a module.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea28b-134">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ea28b-134">-FullyQualifiedName</span></span>

<span data-ttu-id="ea28b-135">指定要删除的模块的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="ea28b-135">Specifies the fully qualified names of modules to remove.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ea28b-136">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="ea28b-136">-ModuleInfo</span></span>

<span data-ttu-id="ea28b-137">指定要删除的模块对象。</span><span class="sxs-lookup"><span data-stu-id="ea28b-137">Specifies the module objects to remove.</span></span>
<span data-ttu-id="ea28b-138">输入包含模块对象 ( **PSModuleInfo** ) 的变量，或输入可获取模块对象的命令，如 Get-Module 命令。</span><span class="sxs-lookup"><span data-stu-id="ea28b-138">Enter a variable that contains a module object ( **PSModuleInfo** ) or a command that gets a module object, such as a Get-Module command.</span></span>
<span data-ttu-id="ea28b-139">你还可以通过管道将模块对象传递给 **Remove-Module** 。</span><span class="sxs-lookup"><span data-stu-id="ea28b-139">You can also pipe module objects to **Remove-Module** .</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ea28b-140">-Name</span><span class="sxs-lookup"><span data-stu-id="ea28b-140">-Name</span></span>

<span data-ttu-id="ea28b-141">指定要删除的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="ea28b-141">Specifies the names of modules to remove.</span></span>
<span data-ttu-id="ea28b-142">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ea28b-142">Wildcard characters are permitted.</span></span>
<span data-ttu-id="ea28b-143">还可以通过管道将名称字符串传递给 **Remove-Module** 。</span><span class="sxs-lookup"><span data-stu-id="ea28b-143">You can also pipe name strings to **Remove-Module** .</span></span>

```yaml
Type: System.String[]
Parameter Sets: name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="ea28b-144">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ea28b-144">-Confirm</span></span>

<span data-ttu-id="ea28b-145">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="ea28b-145">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea28b-146">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ea28b-146">-WhatIf</span></span>

<span data-ttu-id="ea28b-147">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="ea28b-147">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ea28b-148">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="ea28b-148">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea28b-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ea28b-149">CommonParameters</span></span>

<span data-ttu-id="ea28b-150">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ea28b-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ea28b-151">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ea28b-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ea28b-152">输入</span><span class="sxs-lookup"><span data-stu-id="ea28b-152">INPUTS</span></span>

### <span data-ttu-id="ea28b-153">System.String, System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="ea28b-153">System.String, System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="ea28b-154">可以通过管道将模块名称和模块对象传递给 **Remove-Module** 。</span><span class="sxs-lookup"><span data-stu-id="ea28b-154">You can pipe module names and module objects to **Remove-Module** .</span></span>

## <span data-ttu-id="ea28b-155">输出</span><span class="sxs-lookup"><span data-stu-id="ea28b-155">OUTPUTS</span></span>

### <span data-ttu-id="ea28b-156">无</span><span class="sxs-lookup"><span data-stu-id="ea28b-156">None</span></span>

<span data-ttu-id="ea28b-157">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="ea28b-157">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ea28b-158">注释</span><span class="sxs-lookup"><span data-stu-id="ea28b-158">NOTES</span></span>

<span data-ttu-id="ea28b-159">删除模块时，将执行的模块上有一个事件。</span><span class="sxs-lookup"><span data-stu-id="ea28b-159">When removing a module, there is an event on the module that will execute.</span></span>
<span data-ttu-id="ea28b-160">此事件允许模块响应被删除并执行一些清理，如释放资源。</span><span class="sxs-lookup"><span data-stu-id="ea28b-160">This event allows a module to react to being removed and perform some cleanup such as freeing up resources.</span></span> <span data-ttu-id="ea28b-161">示例：</span><span class="sxs-lookup"><span data-stu-id="ea28b-161">Example:</span></span>

<span data-ttu-id="ea28b-162">$OnRemoveScript = {</span><span class="sxs-lookup"><span data-stu-id="ea28b-162">$OnRemoveScript = {</span></span>

  <span data-ttu-id="ea28b-163">\# 执行清理</span><span class="sxs-lookup"><span data-stu-id="ea28b-163">\# perform cleanup</span></span>

  <span data-ttu-id="ea28b-164">$cachedSessions |Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="ea28b-164">$cachedSessions | Remove-PSSession</span></span>

<span data-ttu-id="ea28b-165">}</span><span class="sxs-lookup"><span data-stu-id="ea28b-165">}</span></span>

<span data-ttu-id="ea28b-166">SessionState. OnRemove + = $OnRemoveScript $ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="ea28b-166">$ExecutionContext.SessionState.Module.OnRemove += $OnRemoveScript</span></span>

<span data-ttu-id="ea28b-167">为了完全保持一致性，响应 PowerShell 进程的关闭可能也很有用：</span><span class="sxs-lookup"><span data-stu-id="ea28b-167">For full consistency, it might be also useful to react to the closing of the PowerShell process:</span></span>

<span data-ttu-id="ea28b-168">Register-EngineEvent ( [PsEngineEvent]：：正在退出) -操作 $OnRemoveScript</span><span class="sxs-lookup"><span data-stu-id="ea28b-168">Register-EngineEvent -SourceIdentifier ([System.Management.Automation.PsEngineEvent]::Exiting) -Action $OnRemoveScript</span></span>

## <span data-ttu-id="ea28b-169">相关链接</span><span class="sxs-lookup"><span data-stu-id="ea28b-169">RELATED LINKS</span></span>

[<span data-ttu-id="ea28b-170">Get-Module</span><span class="sxs-lookup"><span data-stu-id="ea28b-170">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="ea28b-171">Import-Module</span><span class="sxs-lookup"><span data-stu-id="ea28b-171">Import-Module</span></span>](Import-Module.md)

