---
external help file: Disable-DscDebug.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/disable-dscdebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-DscDebug
ms.openlocfilehash: fdaba8358772f559a33117c796a923d774b009cb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198268"
---
# <span data-ttu-id="3dc83-103">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="3dc83-103">Disable-DscDebug</span></span>

## <span data-ttu-id="3dc83-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3dc83-104">SYNOPSIS</span></span>
<span data-ttu-id="3dc83-105">停止调试 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="3dc83-105">Stops debugging of DSC resources.</span></span>

## <span data-ttu-id="3dc83-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3dc83-106">SYNTAX</span></span>

```
Disable-DscDebug [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="3dc83-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3dc83-107">DESCRIPTION</span></span>
<span data-ttu-id="3dc83-108">**Disable-DscDebug** cmdlet 请求 Windows PowerShell Desired State Configuration (DSC) 引擎停止调试 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="3dc83-108">The **Disable-DscDebug** cmdlet requests that the Windows PowerShell Desired State Configuration (DSC) engine stop debugging of DSC resources.</span></span>
<span data-ttu-id="3dc83-109">如果 DSC 引擎当前未在调试模式下，则此 cmdlet 无效。</span><span class="sxs-lookup"><span data-stu-id="3dc83-109">This cmdlet has no effect if the DSC engine is not currently in debugging mode.</span></span>

## <span data-ttu-id="3dc83-110">示例</span><span class="sxs-lookup"><span data-stu-id="3dc83-110">EXAMPLES</span></span>

### <span data-ttu-id="3dc83-111">示例 1：停止资源调试</span><span class="sxs-lookup"><span data-stu-id="3dc83-111">Example 1: Stop resource debugging</span></span>

```
PS C:\> Disable-DscDebug
```

<span data-ttu-id="3dc83-112">此命令指示本地配置管理器 (LCM) 上的 DSC 引擎停止资源调试。</span><span class="sxs-lookup"><span data-stu-id="3dc83-112">This command indicates to the DSC engine on the Local Configuration Manager (LCM) to stop resource debugging.</span></span>

### <span data-ttu-id="3dc83-113">示例 2：检查引擎状态并停止调试</span><span class="sxs-lookup"><span data-stu-id="3dc83-113">Example 2: Check the engine state and stop debugging</span></span>

```
PS C:\> if((Get-DscLocalConfigurationManager).DebugMode -like '*Break*'){Disable-DscDebug}
```

<span data-ttu-id="3dc83-114">此命令检查 DSC 引擎状态，且仅当引擎已在调试模式下时才停止资源调试</span><span class="sxs-lookup"><span data-stu-id="3dc83-114">This command checks the DSC engine state, and stops resource debugging only if it is already in debugging mode</span></span>

## <span data-ttu-id="3dc83-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3dc83-115">PARAMETERS</span></span>

### <span data-ttu-id="3dc83-116">-AsJob</span><span class="sxs-lookup"><span data-stu-id="3dc83-116">-AsJob</span></span>
<span data-ttu-id="3dc83-117">指示此 cmdlet 将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="3dc83-117">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="3dc83-118">-CimSession</span><span class="sxs-lookup"><span data-stu-id="3dc83-118">-CimSession</span></span>
<span data-ttu-id="3dc83-119">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3dc83-119">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="3dc83-120">输入计算机名或会话对象，例如 [CimSession](/powershell/module/cimcmdlets/new-cimsession) 或 [CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet 的输出。</span><span class="sxs-lookup"><span data-stu-id="3dc83-120">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="3dc83-121">默认为本地计算机上的当前会话。</span><span class="sxs-lookup"><span data-stu-id="3dc83-121">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="3dc83-122">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="3dc83-122">-ThrottleLimit</span></span>
<span data-ttu-id="3dc83-123">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="3dc83-123">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="3dc83-124">如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。</span><span class="sxs-lookup"><span data-stu-id="3dc83-124">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="3dc83-125">该限制仅适用于当前 cmdlet，不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="3dc83-125">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="3dc83-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3dc83-126">-Confirm</span></span>
<span data-ttu-id="3dc83-127">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="3dc83-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3dc83-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3dc83-128">-WhatIf</span></span>
<span data-ttu-id="3dc83-129">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="3dc83-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3dc83-130">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="3dc83-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3dc83-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3dc83-131">CommonParameters</span></span>
<span data-ttu-id="3dc83-132">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="3dc83-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3dc83-133">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="3dc83-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3dc83-134">输入</span><span class="sxs-lookup"><span data-stu-id="3dc83-134">INPUTS</span></span>

## <span data-ttu-id="3dc83-135">输出</span><span class="sxs-lookup"><span data-stu-id="3dc83-135">OUTPUTS</span></span>

## <span data-ttu-id="3dc83-136">注释</span><span class="sxs-lookup"><span data-stu-id="3dc83-136">NOTES</span></span>

## <span data-ttu-id="3dc83-137">相关链接</span><span class="sxs-lookup"><span data-stu-id="3dc83-137">RELATED LINKS</span></span>

[<span data-ttu-id="3dc83-138">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="3dc83-138">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="3dc83-139">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="3dc83-139">Enable-DscDebug</span></span>](Enable-DscDebug.md)

[<span data-ttu-id="3dc83-140">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="3dc83-140">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="3dc83-141">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="3dc83-141">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)

[<span data-ttu-id="3dc83-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3dc83-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="3dc83-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3dc83-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="3dc83-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3dc83-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
