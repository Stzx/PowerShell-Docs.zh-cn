---
external help file: Stop-DscConfiguration.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/19/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/stop-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-DscConfiguration
ms.openlocfilehash: 93c8585ae948dfa360a2ae8e2563670de8fd6e93
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197830"
---
# <span data-ttu-id="8d35c-103">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d35c-103">Stop-DscConfiguration</span></span>

## <span data-ttu-id="8d35c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="8d35c-104">SYNOPSIS</span></span>
<span data-ttu-id="8d35c-105">停止正在运行的配置作业。</span><span class="sxs-lookup"><span data-stu-id="8d35c-105">Stops a configuration job that is running.</span></span>

## <span data-ttu-id="8d35c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8d35c-106">SYNTAX</span></span>

### <span data-ttu-id="8d35c-107">全部</span><span class="sxs-lookup"><span data-stu-id="8d35c-107">All</span></span>

```
Stop-DscConfiguration [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8d35c-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8d35c-108">DESCRIPTION</span></span>

<span data-ttu-id="8d35c-109">`Stop-DscConfiguration`Cmdlet 可停止正在运行的配置作业。</span><span class="sxs-lookup"><span data-stu-id="8d35c-109">The `Stop-DscConfiguration` cmdlet stops a configuration job that is running.</span></span> <span data-ttu-id="8d35c-110">使用通用信息模型 (CIM) 会话指定应用此 cmdlet 的计算机。</span><span class="sxs-lookup"><span data-stu-id="8d35c-110">Specify which computers this cmdlet applies to by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="8d35c-111">如果没有正在运行的配置作业，则此 cmdlet 将返回一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="8d35c-111">If there's no configuration job running, this cmdlet returns a warning message.</span></span>

<span data-ttu-id="8d35c-112">`Stop-DscConfiguration` 仅可作为 Microsoft 支持部门库中的 [WINDOWS RT 8.1、Windows 8.1 和 Windows Server 2012 R2 的2014年11月更新汇总](https://support.microsoft.com/kb/3000850) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="8d35c-112">`Stop-DscConfiguration` is only available as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span> <span data-ttu-id="8d35c-113">使用此 cmdlet 之前，请查看[Windows PowerShell 5.0 的新增功能](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)中的信息</span><span class="sxs-lookup"><span data-stu-id="8d35c-113">Before you use this cmdlet, review the information in [What's New in Windows PowerShell 5.0](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)</span></span>

## <span data-ttu-id="8d35c-114">示例</span><span class="sxs-lookup"><span data-stu-id="8d35c-114">EXAMPLES</span></span>

### <span data-ttu-id="8d35c-115">示例 1：停止配置作业</span><span class="sxs-lookup"><span data-stu-id="8d35c-115">Example 1: Stop a configuration job</span></span>

<span data-ttu-id="8d35c-116">在此示例中，使用 cmdlet 创建 CIM 会话 `New-CimSession` 。</span><span class="sxs-lookup"><span data-stu-id="8d35c-116">In this example, a CIM session is created using the `New-CimSession` cmdlet.</span></span> <span data-ttu-id="8d35c-117">**CimSession** 对象用于停止正在运行的配置作业。</span><span class="sxs-lookup"><span data-stu-id="8d35c-117">The **CimSession** object is used to stop a running configuration job.</span></span>

```powershell
$Session = New-CimSession -ComputerName Server01 -Credential ACCOUNTS\User01
Stop-DscConfiguration -CimSession $Session
```

<span data-ttu-id="8d35c-118">`New-CimSession` 使用 **ComputerName** 参数指定 Server01 计算机。</span><span class="sxs-lookup"><span data-stu-id="8d35c-118">`New-CimSession` uses the **ComputerName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="8d35c-119">**Credential** 参数指定用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8d35c-119">The **Credential** parameter specifies the user account.</span></span> <span data-ttu-id="8d35c-120">**CimSession** 对象存储在 `$Session` 变量中。</span><span class="sxs-lookup"><span data-stu-id="8d35c-120">The **CimSession** object is stored in the `$Session` variable.</span></span> <span data-ttu-id="8d35c-121">运行该命令时，系统将提示你输入用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="8d35c-121">When the command is run, you're prompted for the user account's password.</span></span>

<span data-ttu-id="8d35c-122">`Stop-DscConfiguration` 使用 **CimSession** 参数和存储在中的对象 `$Session` 停止配置作业。</span><span class="sxs-lookup"><span data-stu-id="8d35c-122">`Stop-DscConfiguration` uses the **CimSession** parameter and the object stored in `$Session` to stop the configuration job.</span></span>

## <span data-ttu-id="8d35c-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8d35c-123">PARAMETERS</span></span>

### <span data-ttu-id="8d35c-124">-AsJob</span><span class="sxs-lookup"><span data-stu-id="8d35c-124">-AsJob</span></span>

<span data-ttu-id="8d35c-125">指示此 cmdlet 将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="8d35c-125">Indicates that this cmdlet runs the command as a background job.</span></span> <span data-ttu-id="8d35c-126">有关 PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 和 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="8d35c-126">For more information about PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="8d35c-127">若要使用 **AsJob** 参数，必须为本地计算机和远程计算机配置远程处理。</span><span class="sxs-lookup"><span data-stu-id="8d35c-127">To use the **AsJob** parameter, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="8d35c-128">在 Windows Vista 和更高版本的 Windows 操作系统上，你必须通过 "以 **管理员身份运行** " 选项打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8d35c-128">On Windows Vista and later versions of the Windows operating system, you must open PowerShell with the **Run as administrator** option.</span></span> <span data-ttu-id="8d35c-129">有关详细信息，请参阅 [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d35c-129">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d35c-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="8d35c-130">-CimSession</span></span>

<span data-ttu-id="8d35c-131">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8d35c-131">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="8d35c-132">输入计算机名或会话对象，如或的输出 `New-CimSession` `Get-CimSession` 。</span><span class="sxs-lookup"><span data-stu-id="8d35c-132">Enter a computer name or a session object, such as the output from `New-CimSession` or `Get-CimSession`.</span></span>

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

### <span data-ttu-id="8d35c-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8d35c-133">-Confirm</span></span>

<span data-ttu-id="8d35c-134">`Stop-DscConfiguration` 不支持 **Confirm** 参数。</span><span class="sxs-lookup"><span data-stu-id="8d35c-134">`Stop-DscConfiguration` doesn't support the **Confirm** parameter.</span></span> <span data-ttu-id="8d35c-135">如果使用 **Confirm** 参数，则会显示错误。</span><span class="sxs-lookup"><span data-stu-id="8d35c-135">If the **Confirm** parameter is used, an error is displayed.</span></span>

<span data-ttu-id="8d35c-136">对于支持 **确认** 的 PowerShell cmdlet，使用参数会提示你在运行命令前进行验证。</span><span class="sxs-lookup"><span data-stu-id="8d35c-136">For PowerShell cmdlets that support **Confirm** , using the parameter prompts you for verification before a command is run.</span></span>

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

### <span data-ttu-id="8d35c-137">-Force</span><span class="sxs-lookup"><span data-stu-id="8d35c-137">-Force</span></span>

<span data-ttu-id="8d35c-138">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="8d35c-138">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d35c-139">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="8d35c-139">-ThrottleLimit</span></span>

<span data-ttu-id="8d35c-140">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="8d35c-140">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

<span data-ttu-id="8d35c-141">如果省略此参数或输入的值 `0` ，则 PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算最佳限制。</span><span class="sxs-lookup"><span data-stu-id="8d35c-141">If this parameter is omitted or a value of `0` is entered, PowerShell calculates an optimum throttle limit based on the number of CIM cmdlets that are running on the computer.</span></span> <span data-ttu-id="8d35c-142">该限制仅适用于当前 cmdlet，不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="8d35c-142">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="8d35c-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8d35c-143">-WhatIf</span></span>

<span data-ttu-id="8d35c-144">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="8d35c-144">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="8d35c-145">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="8d35c-145">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="8d35c-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8d35c-146">CommonParameters</span></span>

<span data-ttu-id="8d35c-147">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="8d35c-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8d35c-148">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="8d35c-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8d35c-149">输入</span><span class="sxs-lookup"><span data-stu-id="8d35c-149">INPUTS</span></span>

### <span data-ttu-id="8d35c-150">无</span><span class="sxs-lookup"><span data-stu-id="8d35c-150">None</span></span>

## <span data-ttu-id="8d35c-151">输出</span><span class="sxs-lookup"><span data-stu-id="8d35c-151">OUTPUTS</span></span>

### <span data-ttu-id="8d35c-152">无</span><span class="sxs-lookup"><span data-stu-id="8d35c-152">None</span></span>

## <span data-ttu-id="8d35c-153">注释</span><span class="sxs-lookup"><span data-stu-id="8d35c-153">NOTES</span></span>

## <span data-ttu-id="8d35c-154">相关链接</span><span class="sxs-lookup"><span data-stu-id="8d35c-154">RELATED LINKS</span></span>

[<span data-ttu-id="8d35c-155">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="8d35c-155">Get-CimSession</span></span>](../CimCmdlets/Get-CimSession.md)

[<span data-ttu-id="8d35c-156">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d35c-156">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="8d35c-157">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="8d35c-157">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="8d35c-158">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="8d35c-158">New-CimSession</span></span>](../CimCmdlets/New-CimSession.md)

[<span data-ttu-id="8d35c-159">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d35c-159">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="8d35c-160">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d35c-160">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="8d35c-161">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d35c-161">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)

[<span data-ttu-id="8d35c-162">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d35c-162">Update-DscConfiguration</span></span>](Update-DscConfiguration.md)

[<span data-ttu-id="8d35c-163">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="8d35c-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)
