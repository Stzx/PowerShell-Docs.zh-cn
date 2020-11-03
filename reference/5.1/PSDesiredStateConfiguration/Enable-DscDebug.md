---
external help file: Enable-DscDebug.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/enable-dscdebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-DscDebug
ms.openlocfilehash: 136481c5a1945c3d5cbd1ca7fc8ce5f580c39b0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198270"
---
# <span data-ttu-id="87f02-103">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="87f02-103">Enable-DscDebug</span></span>

## <span data-ttu-id="87f02-104">摘要</span><span class="sxs-lookup"><span data-stu-id="87f02-104">SYNOPSIS</span></span>
<span data-ttu-id="87f02-105">开始调试所有 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="87f02-105">Starts debugging of all DSC resources.</span></span>

## <span data-ttu-id="87f02-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="87f02-106">SYNTAX</span></span>

```
Enable-DscDebug [-BreakAll] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="87f02-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="87f02-107">DESCRIPTION</span></span>
<span data-ttu-id="87f02-108">**Enable-dscdebug** CMDLET 通过 dsc 引擎启用 Windows PowerShell Desired State CONFIGURATION (dsc) 资源调试，这也称为本地 CONFIGURATION MANAGER (LCM) 。</span><span class="sxs-lookup"><span data-stu-id="87f02-108">The **Enable-DscDebug** cmdlet enables Windows PowerShell Desired State Configuration (DSC) resource debugging by the DSC engine, which is also known as the Local Configuration Manager (LCM).</span></span>
<span data-ttu-id="87f02-109">默认情况下，所有资源实例都将进入调试器。</span><span class="sxs-lookup"><span data-stu-id="87f02-109">By default, all resource instances break into the debugger.</span></span>

## <span data-ttu-id="87f02-110">示例</span><span class="sxs-lookup"><span data-stu-id="87f02-110">EXAMPLES</span></span>

### <span data-ttu-id="87f02-111">示例1：启动调试</span><span class="sxs-lookup"><span data-stu-id="87f02-111">Example 1: Start debugging</span></span>

```
PS C:\> Enable-DscDebug -BreakAll
```

<span data-ttu-id="87f02-112">此命令向 DSC 引擎或 LCM 指示开始资源调试。</span><span class="sxs-lookup"><span data-stu-id="87f02-112">This command indicates to the DSC engine or LCM to start resource debugging.</span></span>
<span data-ttu-id="87f02-113">下一次运行配置时，进程将进入调试器。</span><span class="sxs-lookup"><span data-stu-id="87f02-113">The next time the configuration is run, the process enters the debugger.</span></span>

### <span data-ttu-id="87f02-114">示例2：启动远程调试</span><span class="sxs-lookup"><span data-stu-id="87f02-114">Example 2: Start remote debugging</span></span>

```
PS C:\> Enable-DscDebug -BreakAll -CimSession DeploymentServer
```

<span data-ttu-id="87f02-115">此命令向远程计算机的 DSC 引擎指示开始资源调试。</span><span class="sxs-lookup"><span data-stu-id="87f02-115">This command indicates to the DSC engine of the remote computer to start resource debugging.</span></span>

## <span data-ttu-id="87f02-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="87f02-116">PARAMETERS</span></span>

### <span data-ttu-id="87f02-117">-AsJob</span><span class="sxs-lookup"><span data-stu-id="87f02-117">-AsJob</span></span>
<span data-ttu-id="87f02-118">指示此 cmdlet 将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="87f02-118">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="87f02-119">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="87f02-119">-BreakAll</span></span>
<span data-ttu-id="87f02-120">指示在运行配置时所有资源都进入调试器。</span><span class="sxs-lookup"><span data-stu-id="87f02-120">Indicates that all resources enter the debugger when a configuration runs.</span></span>

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

### <span data-ttu-id="87f02-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="87f02-121">-CimSession</span></span>
<span data-ttu-id="87f02-122">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="87f02-122">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="87f02-123">输入计算机名或会话对象，例如 [CimSession](/powershell/module/cimcmdlets/new-cimsession) 或 [CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet 的输出。</span><span class="sxs-lookup"><span data-stu-id="87f02-123">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="87f02-124">默认为本地计算机上的当前会话。</span><span class="sxs-lookup"><span data-stu-id="87f02-124">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87f02-125">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="87f02-125">-ThrottleLimit</span></span>
<span data-ttu-id="87f02-126">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="87f02-126">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="87f02-127">如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。</span><span class="sxs-lookup"><span data-stu-id="87f02-127">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="87f02-128">该限制仅适用于当前 cmdlet，不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="87f02-128">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87f02-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="87f02-129">-Confirm</span></span>
<span data-ttu-id="87f02-130">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="87f02-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="87f02-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="87f02-131">-WhatIf</span></span>
<span data-ttu-id="87f02-132">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="87f02-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="87f02-133">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="87f02-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="87f02-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="87f02-134">CommonParameters</span></span>
<span data-ttu-id="87f02-135">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="87f02-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="87f02-136">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="87f02-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="87f02-137">输入</span><span class="sxs-lookup"><span data-stu-id="87f02-137">INPUTS</span></span>

## <span data-ttu-id="87f02-138">输出</span><span class="sxs-lookup"><span data-stu-id="87f02-138">OUTPUTS</span></span>

## <span data-ttu-id="87f02-139">注释</span><span class="sxs-lookup"><span data-stu-id="87f02-139">NOTES</span></span>

## <span data-ttu-id="87f02-140">相关链接</span><span class="sxs-lookup"><span data-stu-id="87f02-140">RELATED LINKS</span></span>

[<span data-ttu-id="87f02-141">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="87f02-141">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="87f02-142">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="87f02-142">Disable-DscDebug</span></span>](Disable-DscDebug.md)

[<span data-ttu-id="87f02-143">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="87f02-143">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="87f02-144">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="87f02-144">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="87f02-145">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="87f02-145">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="87f02-146">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="87f02-146">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="87f02-147">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="87f02-147">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
