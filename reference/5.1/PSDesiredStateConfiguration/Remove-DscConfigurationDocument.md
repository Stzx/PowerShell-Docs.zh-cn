---
external help file: Remove-DscConfigurationDocument.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DscConfigurationDocument
ms.openlocfilehash: d3e9b15dfeea94921503247adc08b291eed9d7d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198255"
---
# <span data-ttu-id="a46b9-103">Remove-DscConfigurationDocument</span><span class="sxs-lookup"><span data-stu-id="a46b9-103">Remove-DscConfigurationDocument</span></span>

## <span data-ttu-id="a46b9-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a46b9-104">SYNOPSIS</span></span>
<span data-ttu-id="a46b9-105">从 DSC 配置存储中删除配置文档。</span><span class="sxs-lookup"><span data-stu-id="a46b9-105">Removes a configuration document from the DSC configuration store.</span></span>

## <span data-ttu-id="a46b9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a46b9-106">SYNTAX</span></span>

```
Remove-DscConfigurationDocument -Stage <Stage> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a46b9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a46b9-107">DESCRIPTION</span></span>
<span data-ttu-id="a46b9-108">`Remove-DscConfigurationDocument`Cmdlet 从 Windows PowerShell Desired State configuration (DSC) 配置存储中删除配置文档 ( 的 mof 文件) 。</span><span class="sxs-lookup"><span data-stu-id="a46b9-108">The `Remove-DscConfigurationDocument` cmdlet removes a configuration document (.mof file) from the Windows PowerShell Desired State Configuration (DSC) configuration store.</span></span>
<span data-ttu-id="a46b9-109">在配置过程中，该 `Start-DscConfiguration` cmdlet 会将一个 mof 文件复制到目标计算机上的一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a46b9-109">During configuration, the `Start-DscConfiguration` cmdlet copies a .mof file to a folder on the target computer.</span></span>
<span data-ttu-id="a46b9-110">此 cmdlet 会删除该配置文档，并执行其他清理。</span><span class="sxs-lookup"><span data-stu-id="a46b9-110">This cmdlet removes that configuration document and does additional cleanup.</span></span>

<span data-ttu-id="a46b9-111">此 cmdlet 仅在 [WINDOWS RT 8.1、Windows 8.1 和 Windows Server 2012 R2 的2014年11月的更新汇总](https://support.microsoft.com/kb/3000850) 中提供，Microsoft 支持部门库中。</span><span class="sxs-lookup"><span data-stu-id="a46b9-111">This cmdlet is available only as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span>

## <span data-ttu-id="a46b9-112">示例</span><span class="sxs-lookup"><span data-stu-id="a46b9-112">EXAMPLES</span></span>

### <span data-ttu-id="a46b9-113">示例 1：删除当前配置文档</span><span class="sxs-lookup"><span data-stu-id="a46b9-113">Example 1: Remove the current configuration document</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Remove-DscConfigurationDocument -Stage Current -CimSession $Session
```

<span data-ttu-id="a46b9-114">第一个命令通过使用 **New-CimSession** cmdlet 创建 CIM 会话，然后将 **CimSession** 对象存储在 $Session 变量中。</span><span class="sxs-lookup"><span data-stu-id="a46b9-114">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="a46b9-115">该命令会提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="a46b9-115">The command prompts you for a password.</span></span>
<span data-ttu-id="a46b9-116">要了解详情，请键入 `Get-Help New-CimSession`。</span><span class="sxs-lookup"><span data-stu-id="a46b9-116">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="a46b9-117">第二个命令针对 $Session 中存储的 **CimSession** 中指定的计算机删除当前配置文档。</span><span class="sxs-lookup"><span data-stu-id="a46b9-117">The second command removes the current configuration document for the computer specified in the **CimSession** stored in $Session.</span></span>

## <span data-ttu-id="a46b9-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a46b9-118">PARAMETERS</span></span>

### <span data-ttu-id="a46b9-119">-AsJob</span><span class="sxs-lookup"><span data-stu-id="a46b9-119">-AsJob</span></span>
<span data-ttu-id="a46b9-120">指示此 cmdlet 将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="a46b9-120">Indicates that this cmdlet runs the command as a background job.</span></span>

<span data-ttu-id="a46b9-121">如果指定 AsJob  参数，该命令将返回表示作业的对象，然后显示命令提示符。</span><span class="sxs-lookup"><span data-stu-id="a46b9-121">If you specify the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span>
<span data-ttu-id="a46b9-122">作业完成前，可以继续在此会话中工作。</span><span class="sxs-lookup"><span data-stu-id="a46b9-122">You can continue to work in the session until the job finishes.</span></span>
<span data-ttu-id="a46b9-123">作业在本地计算机上创建，并且来自远程计算机的结果将自动返回本地计算机。</span><span class="sxs-lookup"><span data-stu-id="a46b9-123">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="a46b9-124">若要管理作业，请使用 Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a46b9-124">To manage the job, use the Job cmdlets.</span></span>
<span data-ttu-id="a46b9-125">若要获取作业结果，请使用 Receive-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a46b9-125">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="a46b9-126">若要使用此参数，必须为本地计算机和远程计算机配置远程处理，并且在 Windows Vista 以及更高版本的 Windows 操作系统上，还必须使用“以管理员身份运行”选项打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a46b9-126">To use this parameter, the local and remote computers must be configured for remoting, and on Windows Vista and later versions of the Windows operating system, you must open Windows PowerShell with the Run as administrator option.</span></span>
<span data-ttu-id="a46b9-127">有关详细信息，请参阅 [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a46b9-127">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="a46b9-128">有关 Windows PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 和 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="a46b9-128">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="a46b9-129">-CimSession</span><span class="sxs-lookup"><span data-stu-id="a46b9-129">-CimSession</span></span>
<span data-ttu-id="a46b9-130">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a46b9-130">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="a46b9-131">输入计算机名或会话对象，例如 **CimSession** 或 **CimSession** cmdlet 的输出。</span><span class="sxs-lookup"><span data-stu-id="a46b9-131">Enter a computer name or a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet.</span></span>

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

### <span data-ttu-id="a46b9-132">-Force</span><span class="sxs-lookup"><span data-stu-id="a46b9-132">-Force</span></span>
<span data-ttu-id="a46b9-133">指示此 cmdlet 在删除配置文档之前停止正在运行的配置作业。</span><span class="sxs-lookup"><span data-stu-id="a46b9-133">Indicates that this cmdlet stops the running configuration job before it removes the configuration document.</span></span>
<span data-ttu-id="a46b9-134">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="a46b9-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="a46b9-135">-Stage</span><span class="sxs-lookup"><span data-stu-id="a46b9-135">-Stage</span></span>
<span data-ttu-id="a46b9-136">指定要删除的配置文档。</span><span class="sxs-lookup"><span data-stu-id="a46b9-136">Specifies which configuration document to remove.</span></span>
<span data-ttu-id="a46b9-137">可以指定多个文档。</span><span class="sxs-lookup"><span data-stu-id="a46b9-137">You can specify multiple documents.</span></span>
<span data-ttu-id="a46b9-138">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="a46b9-138">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a46b9-139">Current。</span><span class="sxs-lookup"><span data-stu-id="a46b9-139">Current.</span></span>
<span data-ttu-id="a46b9-140">删除描述系统当前状态的配置文档。</span><span class="sxs-lookup"><span data-stu-id="a46b9-140">Remove the configuration document that describes the current state of the system.</span></span>
- <span data-ttu-id="a46b9-141">Pending。</span><span class="sxs-lookup"><span data-stu-id="a46b9-141">Pending.</span></span>
<span data-ttu-id="a46b9-142">删除描述系统挂起状态的配置文档。</span><span class="sxs-lookup"><span data-stu-id="a46b9-142">Remove the configuration document that describes the pending state of the system.</span></span>
- <span data-ttu-id="a46b9-143">Previous。</span><span class="sxs-lookup"><span data-stu-id="a46b9-143">Previous.</span></span>
<span data-ttu-id="a46b9-144">删除描述系统上一个状态的配置文档。</span><span class="sxs-lookup"><span data-stu-id="a46b9-144">Remove the configuration document that describes the previous state of the system.</span></span>

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoveDscConfigurationDocument.Stage
Parameter Sets: (All)
Aliases:
Accepted values: Current, Pending, Previous

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a46b9-145">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="a46b9-145">-ThrottleLimit</span></span>
<span data-ttu-id="a46b9-146">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="a46b9-146">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="a46b9-147">如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。</span><span class="sxs-lookup"><span data-stu-id="a46b9-147">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="a46b9-148">该限制仅适用于当前 cmdlet，不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="a46b9-148">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="a46b9-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a46b9-149">-Confirm</span></span>
<span data-ttu-id="a46b9-150">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="a46b9-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a46b9-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a46b9-151">-WhatIf</span></span>
<span data-ttu-id="a46b9-152">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="a46b9-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a46b9-153">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="a46b9-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a46b9-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a46b9-154">CommonParameters</span></span>
<span data-ttu-id="a46b9-155">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a46b9-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a46b9-156">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a46b9-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a46b9-157">输入</span><span class="sxs-lookup"><span data-stu-id="a46b9-157">INPUTS</span></span>

### <span data-ttu-id="a46b9-158">无</span><span class="sxs-lookup"><span data-stu-id="a46b9-158">None</span></span>

## <span data-ttu-id="a46b9-159">输出</span><span class="sxs-lookup"><span data-stu-id="a46b9-159">OUTPUTS</span></span>

### <span data-ttu-id="a46b9-160">无</span><span class="sxs-lookup"><span data-stu-id="a46b9-160">None</span></span>

## <span data-ttu-id="a46b9-161">注释</span><span class="sxs-lookup"><span data-stu-id="a46b9-161">NOTES</span></span>

## <span data-ttu-id="a46b9-162">相关链接</span><span class="sxs-lookup"><span data-stu-id="a46b9-162">RELATED LINKS</span></span>

[<span data-ttu-id="a46b9-163">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="a46b9-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="a46b9-164">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a46b9-164">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="a46b9-165">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="a46b9-165">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)
