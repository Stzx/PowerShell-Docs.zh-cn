---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/update-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-DscConfiguration
ms.openlocfilehash: 13365902ab317a3daa41b9a951d5e2fa6e4f1b37
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197823"
---
# <span data-ttu-id="8b11a-103">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b11a-103">Update-DscConfiguration</span></span>

## <span data-ttu-id="8b11a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="8b11a-104">SYNOPSIS</span></span>
<span data-ttu-id="8b11a-105">检查请求服务器中是否有更新的配置并应用。</span><span class="sxs-lookup"><span data-stu-id="8b11a-105">Checks the pull server for an updated configuration and applies it.</span></span>

## <span data-ttu-id="8b11a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8b11a-106">SYNTAX</span></span>

### <span data-ttu-id="8b11a-107">ComputerNameSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="8b11a-107">ComputerNameSet (Default)</span></span>

```
Update-DscConfiguration [-Wait] [-JobName <String>] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8b11a-108">CimSessionSet</span><span class="sxs-lookup"><span data-stu-id="8b11a-108">CimSessionSet</span></span>

```
Update-DscConfiguration [-Wait] [-JobName <String>] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8b11a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8b11a-109">DESCRIPTION</span></span>
<span data-ttu-id="8b11a-110">`Update-DscConfiguration`Cmdlet 连接到请求服务器，如果配置不同于节点上的当前配置，则下载配置，然后将配置应用到计算机。</span><span class="sxs-lookup"><span data-stu-id="8b11a-110">The `Update-DscConfiguration` cmdlet connects to a pull server, downloads the configuration if it differs from what is current on the node, and then applies the configuration to the computer.</span></span>

<span data-ttu-id="8b11a-111">此 cmdlet 仅在 [WINDOWS RT 8.1、Windows 8.1 和 Windows Server 2012 R2 的2014年11月的更新汇总](https://support.microsoft.com/kb/3000850) 中提供，Microsoft 支持部门库中。</span><span class="sxs-lookup"><span data-stu-id="8b11a-111">This cmdlet is available only as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span>

## <span data-ttu-id="8b11a-112">示例</span><span class="sxs-lookup"><span data-stu-id="8b11a-112">EXAMPLES</span></span>

### <span data-ttu-id="8b11a-113">示例1：更新配置</span><span class="sxs-lookup"><span data-stu-id="8b11a-113">Example 1: Update a configuration</span></span>

```
PS C:\> Update-DscConfiguration -Wait -Verbose
```

<span data-ttu-id="8b11a-114">运行此命令后，服务器将连接到注册的请求服务，下载最新分配的配置，然后应用该配置。</span><span class="sxs-lookup"><span data-stu-id="8b11a-114">After running this command, the server will connect to the registered pull service, download the latest assigned configuration, and then apply it.</span></span>
<span data-ttu-id="8b11a-115">-Wait 和-Verbose 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="8b11a-115">The -Wait and -Verbose parameters are optional.</span></span>
<span data-ttu-id="8b11a-116">当交互工作时，这些参数结合使用，可在应用配置时实现有关进度、成功或失败的实时反馈。</span><span class="sxs-lookup"><span data-stu-id="8b11a-116">When working interactively, these parameters combined enable real-time feedback about progress and success or failure when applying the configuration.</span></span>

### <span data-ttu-id="8b11a-117">示例2：通过在 CIM 会话上连接来更新配置</span><span class="sxs-lookup"><span data-stu-id="8b11a-117">Example 2: Update a configuration by connecting over a CIM session</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Update-DscConfiguration -CimSession $Session -Wait
```

<span data-ttu-id="8b11a-118">第一个命令通过使用 **New-CimSession** cmdlet 创建 CIM 会话，然后将 **CimSession** 对象存储在 $Session 变量中。</span><span class="sxs-lookup"><span data-stu-id="8b11a-118">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="8b11a-119">该命令会提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="8b11a-119">The command prompts you for a password.</span></span>
<span data-ttu-id="8b11a-120">要了解详情，请键入 `Get-Help New-CimSession`。</span><span class="sxs-lookup"><span data-stu-id="8b11a-120">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="8b11a-121">第二个命令更新 $Session 中存储的 **CimSession** 中指定的计算机。</span><span class="sxs-lookup"><span data-stu-id="8b11a-121">The second command updates the computer specified in the **CimSession** stored in $Session.</span></span>
<span data-ttu-id="8b11a-122">命令指定 *Wait* 参数。</span><span class="sxs-lookup"><span data-stu-id="8b11a-122">The command specifies the *Wait* parameter.</span></span>
<span data-ttu-id="8b11a-123">在当前命令完成之前，控制台不接受其他命令。</span><span class="sxs-lookup"><span data-stu-id="8b11a-123">The console does not accept additional commands until the current command finishes.</span></span>

## <span data-ttu-id="8b11a-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8b11a-124">PARAMETERS</span></span>

### <span data-ttu-id="8b11a-125">-CimSession</span><span class="sxs-lookup"><span data-stu-id="8b11a-125">-CimSession</span></span>
<span data-ttu-id="8b11a-126">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8b11a-126">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="8b11a-127">输入计算机名或会话对象，例如 [CimSession](/powershell/module/cimcmdlets/new-cimsession) 或 [CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet 的输出。</span><span class="sxs-lookup"><span data-stu-id="8b11a-127">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="8b11a-128">默认为本地计算机上的当前会话。</span><span class="sxs-lookup"><span data-stu-id="8b11a-128">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8b11a-129">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="8b11a-129">-ComputerName</span></span>
<span data-ttu-id="8b11a-130">指定一个计算机名称数组。</span><span class="sxs-lookup"><span data-stu-id="8b11a-130">Specifies an array of computer names.</span></span>
<span data-ttu-id="8b11a-131">Cmdlet 可将配置设置应用于此参数指定的计算机。</span><span class="sxs-lookup"><span data-stu-id="8b11a-131">The cmdlet applies the configuration settings to the computers that this parameter specifies.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8b11a-132">-Credential</span><span class="sxs-lookup"><span data-stu-id="8b11a-132">-Credential</span></span>
<span data-ttu-id="8b11a-133">针对目标计算机，指定用户名和密码作为 **PSCredential** 对象。</span><span class="sxs-lookup"><span data-stu-id="8b11a-133">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="8b11a-134">若要获取 **PSCredential** 对象，请使用 Get-Credential cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8b11a-134">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="8b11a-135">要了解详情，请键入 `Get-Help Get-Credential`。</span><span class="sxs-lookup"><span data-stu-id="8b11a-135">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8b11a-136">-JobName</span><span class="sxs-lookup"><span data-stu-id="8b11a-136">-JobName</span></span>
<span data-ttu-id="8b11a-137">为作业指定一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="8b11a-137">Specifies a friendly name for a job.</span></span>
<span data-ttu-id="8b11a-138">如果指定此参数，则 cmdlet 将作为作业运行，并且它将返回 **Job** 对象。</span><span class="sxs-lookup"><span data-stu-id="8b11a-138">If you specify this parameter, the cmdlet runs as a job, and it returns a **Job** object.</span></span>

<span data-ttu-id="8b11a-139">默认情况下，Windows PowerShell 将名称 JobN，其中 N 为整数。</span><span class="sxs-lookup"><span data-stu-id="8b11a-139">By default, Windows PowerShell assigns the name JobN where N is an integer.</span></span>

<span data-ttu-id="8b11a-140">如果指定 *Wait* 参数，则不指定此参数。</span><span class="sxs-lookup"><span data-stu-id="8b11a-140">If you specify the *Wait* parameter, do not specify this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8b11a-141">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="8b11a-141">-ThrottleLimit</span></span>
<span data-ttu-id="8b11a-142">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="8b11a-142">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="8b11a-143">如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。</span><span class="sxs-lookup"><span data-stu-id="8b11a-143">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="8b11a-144">该限制仅适用于当前 cmdlet，不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="8b11a-144">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="8b11a-145">-Wait</span><span class="sxs-lookup"><span data-stu-id="8b11a-145">-Wait</span></span>
<span data-ttu-id="8b11a-146">指示该 cmdlet 将阻止控制台，直到它完成所有的配置任务。</span><span class="sxs-lookup"><span data-stu-id="8b11a-146">Indicates that the cmdlet blocks the console until it finishes all configuration tasks.</span></span>

<span data-ttu-id="8b11a-147">如果指定此参数，则不指定 *JobName* 参数。</span><span class="sxs-lookup"><span data-stu-id="8b11a-147">If you specify this parameter, do not specify the *JobName* parameter.</span></span>

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

### <span data-ttu-id="8b11a-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8b11a-148">-Confirm</span></span>
<span data-ttu-id="8b11a-149">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="8b11a-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8b11a-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8b11a-150">-WhatIf</span></span>
<span data-ttu-id="8b11a-151">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="8b11a-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8b11a-152">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="8b11a-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8b11a-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8b11a-153">CommonParameters</span></span>
<span data-ttu-id="8b11a-154">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="8b11a-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8b11a-155">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="8b11a-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8b11a-156">输入</span><span class="sxs-lookup"><span data-stu-id="8b11a-156">INPUTS</span></span>

## <span data-ttu-id="8b11a-157">输出</span><span class="sxs-lookup"><span data-stu-id="8b11a-157">OUTPUTS</span></span>

## <span data-ttu-id="8b11a-158">注释</span><span class="sxs-lookup"><span data-stu-id="8b11a-158">NOTES</span></span>

## <span data-ttu-id="8b11a-159">相关链接</span><span class="sxs-lookup"><span data-stu-id="8b11a-159">RELATED LINKS</span></span>

[<span data-ttu-id="8b11a-160">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="8b11a-160">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="8b11a-161">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b11a-161">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="8b11a-162">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="8b11a-162">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="8b11a-163">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b11a-163">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="8b11a-164">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b11a-164">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="8b11a-165">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b11a-165">Stop-DscConfiguration</span></span>](Stop-DscConfiguration.md)

[<span data-ttu-id="8b11a-166">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b11a-166">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
